---
title: 이중 썽킹 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- double thunks
- interop [C++], double thunking
- mixed assemblies [C++], double thunking
- /clr compiler option [C++], double thunking
- interoperability [C++], double thunking
ms.assetid: a85090b2-dc3c-498a-b40c-340db229dd6f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 47d5bbbecc8e1b9743c543a503df1a0afa0dc0ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111210"
---
# <a name="double-thunking-c"></a>이중 썽킹(C++)
이중 썽킹 Visual c + + 관리 되는 함수는 프로그램 실행 하 고 관리 되는 컨텍스트 호출에 함수 호출 함수의 네이티브 진입점을 관리 되는 함수를 호출 하려면 호출할 때 발생할 수 있는 성능 저하를 가리킵니다. 이 항목에서는 이중 썽킹 발생 하는 위치 및 성능을 향상 시키기 위해를 방지 하는 방법을 설명 합니다.  
  
## <a name="remarks"></a>설명  
 기본적으로 사용 하 여 컴파일할 때 **/clr**, 관리 되는 함수 정의 컴파일러 기본 진입점 및 관리 되는 진입점을 생성 하도록 합니다. 따라서 관리 되는 함수를 네이티브 모듈과 관리 호출 사이트에서 호출할 수 있습니다. 그러나 네이티브 진입점이 있으면이 함수에 대 한 모든 호출에 대 한 진입점을 수 있습니다. 호출 함수의 경우 관리 되는 경우 네이티브 진입점 관리 되는 진입점 다음 호출 합니다. 두 번 호출 함수를 호출 하는 데 필요한 실제로 (하므로 이중 썽킹). 예를 들어 가상 함수는 항상 네이티브 진입점을 통해 호출 됩니다.  
  
 하나의 해결책은 함수는만 호출할 것으로 관리 되는 컨텍스트를 사용 하 여를 관리 되는 함수에 대 한 네이티브 진입점을 생성 하지 않도록 컴파일러에 지시 하는 [__clrcall](../cpp/clrcall.md) 호출 규칙입니다.  
  
 마찬가지로, 내보내면 ([dllexport, dllimport](../cpp/dllexport-dllimport.md)) 관리 되는 함수 네이티브 진입점이 생성 되 고 네이티브 진입점을 통해 가져오고 해당 함수를 호출 하는 모든 함수를 호출 합니다. 이 경우 이중 썽킹를 방지 하려면 기본 내보내기/가져오기 의미 체계;을 사용 하지 마십시오 통해 메타 데이터를 단순히 참조 `#using` (참조 [#using 지시문](../preprocessor/hash-using-directive-cpp.md)).  
  
 이중 썽킹 불필요 한 줄이기 위해 컴파일러 업데이트 되었습니다. 로 모든 함수는 시그니처 (반환 형식 포함)에서 관리 되는 유형으로 암시적으로 표시 됩니다 예를 들어 `__clrcall`합니다. 이중 썽크 제거에 대 한 자세한 내용은 참조 하십시오. [ http://msdn.microsoft.com/msdnmag/issues/05/01/COptimizations/default.aspx ](http://msdn.microsoft.com/msdnmag/issues/05/01/COptimizations/default.aspx)합니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서는 이중 썽킹 네이티브 컴파일하면 (없이 **/clr**)의 가상 함수에 대 한 호출 `main` 를 한 번 호출 생성 `T`의 복사 생성자와 소멸자를 한 번 호출 합니다. 가상 함수가 선언 되는 경우 비슷한 동작이 이루어집니다 **/clr** 및 `__clrcall`합니다. 그러나으로 컴파일하는 경우 **/clr**, 함수 호출에서 복사 생성자를 호출 하지만 네이티브-관리 되는 썽크 인해 복사 생성자에 대 한 호출이 있습니다.  
  
### <a name="code"></a>코드  
  
```  
// double_thunking.cpp  
// compile with: /clr  
#include <stdio.h>  
struct T {  
   T() {  
      puts(__FUNCSIG__);  
   }  
  
   T(const T&) {  
      puts(__FUNCSIG__);  
   }  
  
   ~T() {  
      puts(__FUNCSIG__);  
   }  
  
   T& operator=(const T&) {  
      puts(__FUNCSIG__);  
      return *this;  
   }  
};  
  
struct S {  
   virtual void /* __clrcall */ f(T t) {};  
} s;  
  
int main() {  
   S* pS = &s;  
   T t;  
  
   printf("calling struct S\n");  
   pS->f(t);  
   printf("after calling struct S\n");  
}  
```  
  
### <a name="sample-output"></a>샘플 출력  
  
```  
__thiscall T::T(void)  
calling struct S  
__thiscall T::T(const struct T &)  
__thiscall T::T(const struct T &)  
__thiscall T::~T(void)  
__thiscall T::~T(void)  
after calling struct S  
__thiscall T::~T(void)  
```  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 앞의 예제에는 이중 썽킹 있는지 보여 줍니다. 이 샘플의 효과 보여 줍니다. `for` 루프 가상 함수를 호출 하는 프로그램은 실행 시간을 보고 합니다. 실행 시간이 가장 느린 프로그램으로 컴파일될 때 보고 됩니다 **/clr**합니다. 시간이 가장 빠른 없이 컴파일하는 경우 보고 **/clr** 사용 가상 함수를 선언 하는 경우 또는 `__clrcall`합니다.  
  
### <a name="code"></a>코드  
  
```  
// double_thunking_2.cpp  
// compile with: /clr  
#include <time.h>  
#include <stdio.h>   
  
#pragma unmanaged  
struct T {  
   T() {}  
   T(const T&) {}  
   ~T() {}  
   T& operator=(const T&) { return *this; }  
};  
  
struct S {  
   virtual void /* __clrcall */ f(T t) {};  
} s;  
  
int main() {  
   S* pS = &s;  
   T t;  
   clock_t start, finish;  
   double  duration;  
   start = clock();  
  
   for ( int i = 0 ; i < 1000000 ; i++ )  
      pS->f(t);  
  
   finish = clock();  
   duration = (double)(finish - start) / (CLOCKS_PER_SEC);  
   printf( "%2.1f seconds\n", duration );  
   printf("after calling struct S\n");  
}  
```  
  
### <a name="sample-output"></a>샘플 출력  
  
```  
4.2 seconds  
after calling struct S  
```  
  
## <a name="see-also"></a>참고 항목  
 [혼합형(네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)