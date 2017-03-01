---
title: "컴파일러 경고 (수준 2) C4412 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4412
dev_langs:
- C++
helpviewer_keywords:
- C4412
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 92aa12514088d0fbffbe826a495d76b49ab311d1
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-2-c4412"></a>컴파일러 경고(수준 2) C4412
'function': 함수 시그니처에 ' type '; C + + 개체에는 순수 코드 간에 전달 하는 안전 하지 않은 혼합형 / 네이티브는입니다.  
  
 **/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않습니다.  
  
 컴파일러에서 런타임 오류가 발생할 수 있는 잠재적으로 위험한 상황을 발견 했습니다:에서 호출이 수행 되는 한 **/clr: 순수** dllimport 및 함수 시그니처를 통해 가져온 함수에 대 한 컴파일 대상에 안전 하지 않은 형식이 포함 되어 있습니다. 멤버 함수를 포함 하거나 데이터 멤버는 안전 하지 않은 형식이 나 안전 하지 않은 형식에 대 한 간접 참조를 보유 하는 경우에 형식이 안전 하지 않습니다.  
  
 이 기본 호출 규칙 순수 및 네이티브 코드 간의 차이 때문에 안전 하지 않습니다 (또는 혼합 네이티브 및 관리). 가져올 때 (통해 `dllimport`)에 함수는 **/clr: 순수** 컴파일 대상 서명에 있는 각 형식의 선언 함수 내보내는 (특히 암시적 호출 규칙의 차이에 주의) 컴파일 대상의 것과 동일 인지 확인 합니다.  
  
 가상 멤버 함수는 예기치 않은 결과가 발생할 특히 쉽습니다.  그러나 올바른 결과 얻을 수 있도록 하려면 심지어 비가상 함수를 테스트 해야 합니다. 올바른 결과 가져오는지 확인 인 경우이 경고를 무시할 수 있습니다.  
  
 대 한 자세한 내용은 **/clr: pure**, 참조 [하는 방법: /clr으로 마이그레이션: 순수 (C + + CLI)](../../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)합니다.  
  
 C4412는 기본적으로 해제 되어 있습니다. 참조 [기본적으로 해제 되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 및 [dllexport, dllimport](../../cpp/dllexport-dllimport.md) 에 대 한 자세한 내용은 합니다.  
  
 이 경고를 해결 하려면 형식에서 모든 기능을 제거 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 c4412 오류가 발생 합니다.  
  
```  
// C4412.cpp  
// compile with: /c /W2 /clr:pure  
#pragma warning (default : 4412)  
  
struct Unsafe {  
   virtual void __cdecl Test();  
};  
  
struct Safe {  
   int i;  
};  
  
__declspec(dllimport) Unsafe * __cdecl func();  
__declspec(dllimport) Safe * __cdecl func2();  
  
int main() {  
   Unsafe *pUnsafe = func();   // C4412  
   // pUnsafe->Test();  
  
   Safe *pSafe = func2();   // OK  
}  
```  
  
## <a name="example"></a>예제  
 다음 샘플은 두 개의 형식을 선언 하는 헤더 파일입니다. `Unsafe` 멤버 함수를 포함 하기 때문에 형식은 안전 하지 않습니다.  
  
```  
// C4412.h  
struct Unsafe {  
   // will be __clrcall if #included in pure compilation  
   // defaults to __cdecl in native or mixed mode compilation  
   virtual void Test(int * pi);  
  
   // try the following line instead  
   // virtual void __cdecl Test(int * pi);  
};  
  
struct Safe {  
   int i;  
};  
```  
  
## <a name="example"></a>예제  
 이 샘플에서는 헤더 파일에 정의 된 형식에서 함수를 내보냅니다.  
  
```  
// C4412_2.cpp  
// compile with: /LD  
#include "C4412.h"  
  
void Unsafe::Test(int * pi) {  
   *pi++;  
}  
  
__declspec(dllexport) Unsafe * __cdecl func() { return new Unsafe; }  
__declspec(dllexport) Safe * __cdecl func2() { return new Safe; }  
```  
  
## <a name="example"></a>예제  
 기본 호출 규칙는 **/clr: 순수** 컴파일은 네이티브 컴파일 다릅니다.  C4412.h 포함 되 면 `Test` 기본값으로 `__clrcall`합니다. 컴파일하고이 프로그램을 실행 하는 경우 (사용 하지 않는 **/c**), 프로그램에 예외가 throw 됩니다.  
  
 다음 샘플에서는 c4412 오류가 발생 합니다.  
  
```  
// C4412_3.cpp  
// compile with: /W2 /clr:pure /c /link C4412_2.lib  
#pragma warning (default : 4412)  
#include "C4412.h"  
  
__declspec(dllimport) Unsafe * __cdecl func();  
__declspec(dllimport) Safe * __cdecl func2();  
  
int main() {  
   int n = 7;  
   Unsafe *pUnsafe = func();   // C4412  
   pUnsafe->Test(&n);  
  
   Safe *pSafe = func2();   // OK  
}  
```
