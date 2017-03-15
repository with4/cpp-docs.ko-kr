---
title: "함수 템플릿의 부분 순서 지정 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "함수 템플릿의 부분 순서 지정"
ms.assetid: 0c17347d-0e80-47ad-b5ac-046462d9dc73
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 함수 템플릿의 부분 순서 지정 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

함수 호출의 인수 목록과 일치하는 다양한 함수 템플릿을 사용할 수 있습니다.  C\+\+에서는 호출해야 하는 함수를 지정하는 함수 템플릿의 부분 정렬을 정의합니다.  정렬이 부분적인 이유는 동일하게 특수화된 것으로 간주되는 일부 템플릿이 있을 수 있기 때문입니다.  
  
 컴파일러는 가능한 일치 함수 템플릿 중에서 가장 특수화된 것을 선택합니다.  예를 들어, 한 함수 템플릿에서 **T** 형식을 사용하고 다른 함수 템플릿에서도 **T\***를 사용하는 경우 **T\*** 버전은 더욱 특수화된 것으로 간주되며 인수가 포인터 형식일 때 동일하게 사용할 수 있는 제네릭 **T** 버전보다 선호됩니다.  
  
 더욱 특수화된 함수 템플릿 후보를 확인하려면 다음 프로세스를 사용합니다.  
  
1.  두 함수 템플릿 T1과 T2를 살펴보십시오.  
  
2.  T1의 매개 변수를 가상의 고유 형식 X로 대체합니다.  
  
3.  T1의 매개 변수 목록을 이용하여 T2가 그 매개 변수 목록에 대해 유효한 템플릿인지 확인합니다.  암시적 변환을 무시합니다.  
  
4.  T1과 T2를 반대로 바꿔 동일한 프로세스를 반복합니다.  
  
5.  한 템플릿은 다른 템플릿에 대해 유효한 템플릿 인수 목록이지만 반대는 그렇지 않은 경우, 유효한 템플릿이 다른 템플릿보다 덜 특수화된 것으로 간주됩니다.  두 템플릿이 서로에 대해 유효한 인수 목록을 구성할 경우, 둘 다 동일하게 특수화된 것으로 간주되기 때문에 두 템플릿을 사용하려 할 때 모호한 호출이 발생합니다.  
  
6.  다음의 규칙을 사용합니다.  
  
    1.  특정 형식으로 특수화된 템플릿은 제네릭 형식 인수를 사용한 템플릿보다 특수화됩니다.  
  
    2.  가상 형식 **X\***는 **T** 템플릿 인수에 유효한 인수이지만 **X**는 **T\*** 템플릿 인수에 유효한 인수가 아니므로 **T\***만 있는 템플릿은 **T**만 있는 템플릿보다 더 특수한 템플릿입니다.  
  
    3.  **const X**는 **T** 템플릿 인수에 유효한 인수이지만 **X**는 **const T** 템플릿 인수에 유효한 인수가 아니므로 **const T**는 **T**보다 더 특수한 템플릿입니다.  
  
    4.  **const X\***는 **T\*** 템플릿 인수에 유효한 인수이지만 **X\***는 **const T\*** 템플릿 인수에 유효한 인수가 아니므로 **const T\***는 **T\***보다 더 특수한 템플릿입니다.  
  
7.  다음 샘플은 표준에 지정된 대로 Visual C\+\+ .NET 2003에서 작동합니다.  
  
```  
// partial_ordering_of_function_templates.cpp  
// compile with: /EHsc  
#include <iostream>  
  
extern "C" int printf(const char*,...);  
template <class T> void f(T) {  
   printf_s("Less specialized function called\n");  
}  
  
template <class T> void f(T*) {  
   printf_s("More specialized function called\n");  
}  
  
template <class T> void f(const T*) {  
   printf_s("Even more specialized function for const T*\n");  
}  
  
int main() {  
   int i =0;  
   const int j = 0;  
   int *pi = &i;  
   const int *cpi = &j;  
  
   f(i);   // Calls less specialized function.  
   f(pi);  // Calls more specialized function.  
   f(cpi); // Calls even more specialized function.  
   // Without partial ordering, these calls would be ambiguous.  
}  
```  
  
### Output  
  
```  
Less specialized function called  
More specialized function called  
Even more specialized function for const T*  
```  
  
## 참고 항목  
 [함수 템플릿](../cpp/function-templates.md)