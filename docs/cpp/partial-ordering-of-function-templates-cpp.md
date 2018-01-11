---
title: "(C + +) 함수 템플릿의 부분 순서 지정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: partial ordering of function templates
ms.assetid: 0c17347d-0e80-47ad-b5ac-046462d9dc73
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cddc0f1680a3354276a2135dd28c31a2037a8202
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="partial-ordering-of-function-templates-c"></a>함수 템플릿의 부분 순서 지정 (C++)

함수 호출의 인수 목록과 일치하는 다양한 함수 템플릿을 사용할 수 있습니다. C++에서는 호출해야 하는 함수를 지정하는 함수 템플릿의 부분 정렬을 정의합니다. 정렬이 부분적인 이유는 동일하게 특수화된 것으로 간주되는 일부 템플릿이 있을 수 있기 때문입니다.

컴파일러는 가능한 일치 함수 템플릿 중에서 가장 특수화된 것을 선택합니다. 예를 들어, 형식이 사용 하는 함수 템플릿을 __T__, 및 다른 함수 템플릿에서도 __T\*__  를 사용할 수는 __T\*__  버전 이라고 특수 및 제네릭 보다 선호 됩니다 되도록 __T__ 버전 인수 포인터 형식, 허용 가능한 일치 항목 간주 합니다.

더욱 특수화된 함수 템플릿 후보를 확인하려면 다음 프로세스를 사용합니다.

1. 두 함수 템플릿 T1과 T2를 살펴보십시오.

2. T1의 매개 변수를 가상의 고유 형식 X로 대체합니다.

3. T1의 매개 변수 목록을 이용하여 T2가 그 매개 변수 목록에 대해 유효한 템플릿인지 확인합니다. 암시적 변환을 무시합니다.

4. T1과 T2를 반대로 바꿔 동일한 프로세스를 반복합니다.

5. 한 템플릿은 다른 템플릿에 대해 유효한 템플릿 인수 목록이지만 반대는 그렇지 않은 경우, 유효한 템플릿이 다른 템플릿보다 덜 특수화된 것으로 간주됩니다. 모호한 호출이 발생 하 고 두 템플릿이 서로 대해 이전 단계 양식 유효한 인수를 사용 하 여, 다음 속성으로 간주 됩니다 동일 하 게 특수화 될 때 사용 하려고 하면 해당 합니다.

6. 다음의 규칙을 사용합니다.

     1. 특정 형식으로 특수화된 템플릿은 제네릭 형식 인수를 사용한 템플릿보다 특수화됩니다.

     2. 만 템플릿에서도 __T\*__  은 하나의 라인만 보다 더 특수 한 __T__가상 입력 하기 때문에, __X\*__  에 대 한 인수는 유효한는 __T__ 템플릿 인수에 있지만 __X__ 이 대 한 올바른 인수가 아닙니다는 __T\*__  템플릿 인수를 사용 합니다.

     3. __const T__ 은 보다 더 특수 한 __T__때문에, __const X__ 에 대 한 인수는 유효한는 __T__ 템플릿 인수에 있지만 __X__ 이 대 한 올바른 인수가 아닙니다는 __const T__ 템플릿 인수를 사용 합니다.

     4. __const T\*__  은 보다 더 특수 한 __T\*__때문에, __const X\*__  에 대 한 유효한 인수는 __T\*__  템플릿 인수에 있지만 __X\*__  이 대 한 올바른 인수가 아닙니다는 __const T\*__  템플릿 인수를 사용 합니다.

## <a name="example"></a>예

다음 샘플은 표준에 지정 된 대로 작동합니다.

```cpp
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
  
### <a name="output"></a>출력  
  
```  
Less specialized function called  
More specialized function called  
Even more specialized function for const T*  
```  
  
## <a name="see-also"></a>참고 항목

[함수 템플릿](../cpp/function-templates.md)
