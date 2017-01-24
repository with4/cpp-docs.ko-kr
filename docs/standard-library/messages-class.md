---
title: "messages 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "messages"
  - "xlocmes/std::messages"
  - "std.messages"
  - "std::messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "messages 클래스"
ms.assetid: c4c71f40-4f24-48ab-9f7c-daccd8d5bd83
caps.latest.revision: 18
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# messages 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 로캘에 대한 국제화된 메시지의 카탈로그에서 지역화된 메시지를 검색하기 위해 로캘 패싯으로 사용할 수 있는 개체에 대해 설명하는 템플릿 클래스입니다.  
  
 현재 메시지 클래스가 구현되는 동안 메시지가 없습니다.  
  
## 구문  
  
```  
template <class CharType>  
   class messages : public messages_base;  
```  
  
#### 매개 변수  
 `CharType`  
 로캘의 문자를 인코딩하기 위해 프로그램 내 사용하는 형식입니다.  
  
## 설명  
 모든 로캘 패싯과 마찬가지로, 고정 개체 ID에는 초기값 0이 저장되어 있습니다. 에 고유한 양수 값을 저장 하는 저장된 된 값에 액세스 하려고 하는 첫 번째 **id입니다.**  
  
 이 패싯은 기본적으로 기본 클래스 messages\_base에 정의된 메시지의 카탈로그를 열고, 필요한 정보를 검색하며, 카탈로그를 닫습니다.  
  
### 생성자  
  
|||  
|-|-|  
|[메시지](../Topic/messages::messages.md)|메시지 패싯 생성자 함수입니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/messages::char_type.md)|메시지를 표시하는 데 사용하는 문자 형식입니다.|  
|[string\_type](../Topic/messages::string_type.md)|`basic_string` 형식의 문자가 포함된 `CharType` 형식의 문자열을 설명하는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[닫기](../Topic/messages::close.md)|메시지 카탈로그를 닫습니다.|  
|[do\_close](../Topic/messages::do_close.md)|메시지 카탈로그를 닫기 위해 호출하는 가상 함수입니다.|  
|[do\_get](../Topic/messages::do_get.md)|메시지 카탈로그를 검색하기 위해 호출하는 가상 함수입니다.|  
|[do\_open](../Topic/messages::do_open.md)|메시지 카탈로그를 열기 위해 호출하는 가상 함수입니다.|  
|[Get](../Topic/messages::get.md)|메시지 카탈로그를 불러옵니다.|  
|[열기](../Topic/messages::open.md)|메시지 카탈로그를 엽니다.|  
  
## 요구 사항  
 **헤더:** \<locale\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<locale\>](../standard-library/locale.md)   
 [messages\_base 클래스](../standard-library/messages-base-class.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)