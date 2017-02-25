---
title: "_com_ptr_t Extractors | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::operatorInterface&"
  - "operatorInterface*"
  - "operatorInterface&"
  - "_com_ptr_t::operatorbool"
  - "_com_ptr_t.operator->"
  - "_com_ptr_t.operator*"
  - "_com_ptr_t::operator->"
  - "_com_ptr_t::operator*"
  - "_com_ptr_t.operatorInterface&"
  - "_com_ptr_t.operatorbool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& 연산자, 특정 개체와 사용"
  - "* 연산자, 특정 개체와 사용"
  - "-> 연산자, 특정 개체와 사용"
  - "추출기"
  - "추출기, _com_ptr_t 클래스"
  - "operator *"
  - "operator bool"
  - "operator Interface&"
  - "operator Interface*"
  - "operator&"
  - "operator*"
  - "operator->"
ms.assetid: 194b9e0e-123c-49ff-a187-0a7fcd68145a
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_ptr_t Extractors
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 캡슐화된 COM 인터페이스 포인터를 추출합니다.  
  
## 구문  
  
```  
  
      operator Interface*( ) const throw( );   
operator Interface&( ) const;   
Interface& operator*( ) const;   
Interface* operator->( ) const;   
Interface** operator&( ) throw( );   
operator bool( ) const throw( );  
```  
  
## 설명  
  
-   **연산자 인터페이스\* NULL**일 수 있는 캡슐화된 인터페이스 포인터를 반환합니다.  
  
-   **연산자 인터페이스&** 캡슐화된 인터페이스 포인터에 대한 참조를 반환하고 포인터가 **NULL**일 경우 오류를 생성합니다.  
  
-   **연산자\*** 스마트 포인터 개체가 역참조 시 실제로 캡슐화된 인터페이스인 것처럼 작동하도록 합니다.  
  
-   **연산자\-\>** 스마트 포인터 개체가 역참조 시 실제로 캡슐화된 인터페이스인 것처럼 작동하도록 합니다.  
  
-   **operator&** 캡슐화된 인터페이스 포인터를 모두 해제하고 **NULL**로 교체한 다음 캡슐화된 포인터의 주소를 반환합니다.  이를 통해 스마트 포인터는 인터페이스 포인터를 반환하는 **out** 매개 변수를 보유한 함수 주소에 의해 전달됩니다.  
  
-   **연산자 bool** 스마트 포인터 개체를 조건식에 사용할 수 있습니다.  이 연산자는 포인터가 **NULL**이 아닌 경우 **true**를 반환합니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_ptr\_t 클래스](../cpp/com-ptr-t-class.md)