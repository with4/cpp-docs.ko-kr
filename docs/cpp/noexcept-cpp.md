---
title: "noexcept(C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "noexcept_cpp"
dev_langs: 
  - "C++"
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# noexcept(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+11:** 함수가 예외를 발생시킬 수 있는지 여부를 지정합니다.  
  
## 구문  
  
```vb  
ReturnType FunctionName(params) noexcept;  
ReturnType FunctionName(params) noexcept(noexcept(expression);  
```  
  
#### 매개 변수  
 식  
 true 또는 false로 평가되는 상수 식입니다.  비조건부 버전은 noexcept\(true\)와 같습니다.  
  
## 설명  
 `noexcept`\(및 해당 동의어 `noecept(true)`\)는 함수가 예외를 발생시키거나 직접 또는 간접적으로 호출하는 다른 함수에서 예외가 전파되는 것을 허용하지 않도록 지정합니다.  보다 구체적으로, `noexcept`는 함수가 호출하는 모든 함수도 noexcept 또는 const이고, 런타임 검사가 필요한 잠재적으로 계산된 동적 캐스트, 해당 형식이 다형 클래스 형식인 glvalue 식에 적용되는 typeid 식 또는 throw 식이 없는 경우에만 함수가 `noexcept`임을 의미합니다.  그러나 컴파일러는 `noexcept` 함수에 생성될 수 있는 예외에 대해 모든 코드 경로를 검사하지는 않습니다.  예외가 `noexcept`로 표시된 함수에 도달하면 [std::terminate](../Topic/terminate%20\(%3Cexception%3E\).md)가 즉시 호출되고 범위 내 개체의 소멸자가 호출된다는 보장이 없습니다.  
  
 noexcept\(false\)로 평가되는 조건부 noexcept를 사용하여 선언된 함수는 예외가 전파되는 것을 허용하지 않도록 지정합니다.  예를 들어 해당 인수를 복사하는 함수가 복사 중인 개체가 POD\(일반 이전 데이터 형식\)인 조건에서 noexcept로 선언될 수 있습니다.  이러한 함수는 다음과 같이 선언될 수 있습니다.  
  
```  
#include <type_traits>  
  
template <typename T>  
T copy_object(T& obj) noexcept(std::is_pod<T>)  
{  
 //. . .   
}  
  
```  
  
 C\+\+11 이상 버전에서 사용되지 않는 예외 지정자 `throw` 대신 `noexcept`를 사용합니다.  예외가 호출 스택으로 전파되는 것을 허용하지 않도록 하려는 경우 함수에 `noexcept`를 적용하는 것이 좋습니다.  `noexcept`를 사용하여 선언된 함수는 컴파일러가 다양한 컨텍스트에서 보다 효율적인 코드를 생성할 수 있게 합니다.  
  
## 참고 항목  
 [C\+\+ 예외 처리](../cpp/cpp-exception-handling.md)