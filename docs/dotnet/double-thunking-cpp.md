---
title: "이중 썽킹(C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr 컴파일러 옵션[C++], 이중 썽킹"
  - "이중 썽크"
  - "interop[C++], 이중 썽킹"
  - "상호 운용성[C++], 이중 썽킹"
  - "혼합형 어셈블리[C++], 이중 썽킹"
ms.assetid: a85090b2-dc3c-498a-b40c-340db229dd6f
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 이중 썽킹(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이중 썽킹은 관리되는 컨텍스트의 함수 호출로 Visual C\+\+ 관리되는 함수를 호출할 때 관리되는 함수를 호출하기 위해 함수의 네이티브 진입점을 호출하는 프로그램 실행에서 발생할 수 있는 성능 저하를 가리킵니다.  이 항목에서는 이중 썽킹이 발생하는 위치와 이를 방지하여 성능을 향상시키는 방법에 대해 설명합니다.  
  
## 설명  
 기본적으로 **\/clr:pure**가 아닌 **\/clr**를 사용하여 컴파일하는 경우 관리되는 함수의 정의로 인해 컴파일러에서 관리되는 진입점과 네이티브 진입점이 생성됩니다.  이 경우 네이티브 및 관리되는 호출 사이트에서 관리되는 함수를 호출할 수 있습니다.  그러나 네이티브 진입점이 있는 경우 이는 함수에 대한 모든 호출의 진입점으로 사용될 수 있습니다.  호출 함수가 관리되는 경우 네이티브 진입점은 관리되는 진입점을 호출합니다.  실제로 함수를 호출하려면 두 호출이 모두 필요하므로 이중 썽킹이 발생합니다.  예를 들어, 가상 함수는 항상 네이티브 진입점을 통해 호출됩니다.  
  
 이를 해결하는 한 가지 방법은 [\_\_clrcall](../cpp/clrcall.md) 호출 규칙을 사용하여 함수가 관리되는 컨텍스트에서만 호출되고 관리되는 함수의 네이티브 진입점을 생성하지 않도록 컴파일러에 지시하는 것입니다.  
  
 마찬가지로, 관리되는 함수를 내보내는 경우\([dllexport, dllimport](../cpp/dllexport-dllimport.md)\) 네이티브 진입점이 생성되고 해당 함수를 가져오고 호출하는 모든 함수가 네이티브 진입점을 통해 호출합니다.  이 상황에서 이중 썽킹이 발생하지 않도록 하려면 네이티브 내보내기\/가져오기 의미를 사용하지 말고 `#using`을 통해 메타데이터를 참조해야 합니다. 자세한 내용은 [\#using 지시문](../preprocessor/hash-using-directive-cpp.md)를 참조하십시오.  
  
 불필요한 이중 썽킹을 줄이기 위해 컴파일러가 업데이트되었습니다.  예를 들어, 반환 형식을 비롯하여 시그니처에 관리되는 형식이 있는 함수는 모두 암시적으로 `__clrcall`로 표시됩니다.  For more information on double thunk elimination, see [http:\/\/msdn.microsoft.com\/msdnmag\/issues\/05\/01\/COptimizations\/default.aspx](http://msdn.microsoft.com/msdnmag/issues/05/01/COptimizations/default.aspx).  
  
## 예제  
  
### 설명  
 다음 샘플에서는 이중 썽킹을 보여 줍니다.  **\/clr**를 사용하지 않고 네이티브로 컴파일하면 `main`의 가상 함수에 대한 호출을 통해 `T`의 복사 생성자에 대한 호출 하나와 소멸자에 대한 호출 하나가 생성됩니다.  **\/clr** 및 `__clrcall`을 사용하여 가상 함수를 선언하는 경우에도 비슷한 결과가 발생합니다.  그러나 **\/clr**를 사용하여 컴파일하는 경우 함수를 호출하면 복사 생성자에 대한 호출이 생성될 뿐만 아니라 네이티브에서 관리되는 형식으로의 썽크로 인해 복사 생성자에 대한 호출이 하나 더 생성됩니다.  
  
### 코드  
  
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
  
### 샘플 출력  
  
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
  
## 예제  
  
### 설명  
 위 예제에서는 이중 썽킹이 발생하는 경우를 보여 주었습니다.  이 샘플에서는 이중 썽킹의 영향을 보여 줍니다.  `for` 루프에서는 가상 함수를 호출하고 프로그램은 실행 시간을 보고합니다.  **\/clr**를 사용하여 프로그램을 컴파일한 경우 실행 시간이 가장 느린 것으로 보고됩니다.  반면, **\/clr**를 사용하지 않고 컴파일하거나 `__clrcall`을 사용하여 가상 함수를 호출한 경우에 실행 시간이 가장 빠른 것으로 보고됩니다.  
  
### 코드  
  
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
  
### 샘플 출력  
  
```  
4.2 seconds  
after calling struct S  
```  
  
## 참고 항목  
 [혼합형\(네이티브 및 관리\) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)