---
title: "SafeNotEquals | Microsoft Docs"
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
  - "SafeNotEquals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeNotEquals 함수"
ms.assetid: 032e45a8-4159-4b55-b7cc-ecd27f4e4788
caps.latest.revision: 6
caps.handback.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeNotEquals
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Determines if two numbers are not equal.  
  
## 구문  
  
```  
template<typename T, typename U>  
inline bool SafeNotEquals (  
   const T t,  
   const U u  
) throw ();  
```  
  
#### 매개 변수  
 \[in\] `t`  
 비교할 첫 번째 숫자입니다.  이 형식은 T문자열이어야 합니다.  
  
 \[in\] `u`  
 비교할 두 번째 숫자입니다.  이 형식은 U문자열이어야 합니다.  
  
## 반환 값  
 `t`와 `u`가 같지 않으면 `true`이고, 같으면 `false`입니다.  
  
## 설명  
 메서드가 향상  `!=`  때문에  `SafeNotEquals`  두 가지 숫자를 비교할 수 있습니다.  
  
 이 메서드는 부분 [SafeInt 라이브러리](../windows/safeint-library.md) 의 인스턴스를 만들지 않고도 단일 비교 작업을 위해 설계되었습니다 [SafeInt 클래스](../windows/safeint-class.md).  
  
> [!NOTE]
>  단일 수치 연산을 보호 해야 하는 경우에이 메서드를 사용 합니다.  작업을 여러 개 있는 경우 사용 해야 있는  `SafeInt`  개별 독립 실행형 함수를 호출 하는 대신 클래스입니다.  
  
 이 템플릿 형식에 대한 자세한 내용은 [SafeInt 함수](../windows/safeint-functions.md)을 참조하십시오.  
  
## 요구 사항  
 **헤더:** safeint.h  
  
 **네임 스페이스:** Microsoft::Utilities  
  
## 참고 항목  
 [SafeInt 함수](../windows/safeint-functions.md)   
 [SafeInt 라이브러리](../windows/safeint-library.md)   
 [SafeInt 클래스](../windows/safeint-class.md)   
 [SafeEquals](../windows/safeequals.md)