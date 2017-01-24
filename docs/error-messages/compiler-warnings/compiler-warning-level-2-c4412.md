---
title: "컴파일러 경고 (수준 2) C4412 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4412"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4412"
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 2) C4412
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 함수 시그니처에 'type' 형식이 있습니다. 순수형 코드와 혼합형\/네이티브 코드 간에 C\+\+ 개체를 전달하는 것은 안전하지 않습니다.  
  
 런타임 오류가 발생할 가능성이 있는 안전하지 않은 상황을 컴파일러가 발견했습니다. dllimport를 통해 가져온 함수를 **\/clr:pure** 컴파일 대상이 호출하고 있으며 이 함수의 시그니처에 포함된 형식이 안전하지 않습니다.  형식에 멤버 함수가 포함되어 있거나 안전하지 않은 형식의 데이터 멤버 또는 안전하지 않은 형식을 간접 참조하는 데이터 멤버가 있는 경우 이 형식은 안전하지 않습니다.  
  
 이러한 형식이 안전하지 않은 이유는 순수 코드와 네이티브 코드\(또는 혼합 네이티브 코드와 관리 코드\) 사이의 기본 호출 규칙이 서로 다르기 때문입니다.  `dllimport`를 통해 함수를 **\/clr:pure** 컴파일 대상으로 가져오는 경우 시그니처에서 각 형식의 선언이 함수를 내보내는 컴파일 대상의 선언과 동일한지 확인해야 합니다. 이때 암시적 호출 규칙의 차이에 특히 주의해야 합니다.  
  
 가상 멤버 함수에서 특히 예기치 않은 결과가 발생하기 쉽습니다.  그러나 비가상 함수라 해도 올바른 결과를 얻을 수 있는지 테스트해야 합니다.  결과가 올바른 것으로 확인되면 이 경고를 무시해도 됩니다.  
  
 **\/clr:pure**에 대한 자세한 내용은 [방법: \/clr:pure로 마이그레이션](../../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)을 참조하십시오.  
  
 C4412는 기본적으로 표시되지 않습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 및 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)를 참조하십시오.  
  
 이 경고를 해결하려면 형식에서 함수를 모두 제거하십시오.  
  
## 예제  
 다음 샘플에서는 C4412 오류가 발생하는 경우를 보여 줍니다.  
  
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
  
## 예제  
 다음 샘플은 두 개의 형식을 선언하는 헤더 파일입니다.  `Unsafe` 형식에는 멤버 함수가 있으므로 이 형식은 안전하지 않습니다.  
  
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
  
## 예제  
 이 샘플은 헤더 파일에서 정의된 형식으로 함수를 내보냅니다.  
  
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
  
## 예제  
 **\/clr:pure** 컴파일의 기본 호출 규칙이 네이티브 컴파일의 경우와 다릅니다.  C4412.h가 포함되는 경우 `Test`는 `__clrcall`로 기본 설정됩니다.  **\/c**를 사용하지 않고 이 프로그램을 컴파일하여 실행하면 프로그램에서 예외가 throw됩니다.  
  
 다음 샘플에서는 C4412 오류가 발생하는 경우를 보여 줍니다.  
  
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