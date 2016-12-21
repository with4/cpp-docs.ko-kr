---
title: "ComPtr::operator Microsoft::WRL::Details::BoolType 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: cfba6521-fb30-4fb8-afb2-cfab1cb5e0b8
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::operator Microsoft::WRL::Details::BoolType 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ComPtr 인터페이스의 개체 수명을 관리 여부를 나타냅니다.  
  
## 구문  
  
```  
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;  
```  
  
## 반환 값  
 인터페이스는이 ComPtr 연결하는 경우, [BoolStruct::Member](../windows/boolstruct-member-data-member.md) 데이터 멤버의 주소, 그렇지 않으면 `nullptr` 입니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)   
 [ComPtr::Get 메서드](../windows/comptr-get-method.md)