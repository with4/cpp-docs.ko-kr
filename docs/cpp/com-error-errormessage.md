---
title: "_com_error::ErrorMessage | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error::ErrorMessage"
  - "_com_error.ErrorMessage"
  - "ErrorMessage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ErrorMessage 메서드"
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::ErrorMessage
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 `_com_error` 개체에 저장된 `HRESULT`에 대한 문자열 메시지를 검색합니다.  
  
## 구문  
  
```  
  
const TCHAR * ErrorMessage( ) const throw( );  
  
```  
  
## 반환 값  
 `_com_error` 개체 내에 기록된 `HRESULT`에 대한 문자열 메시지를 반환합니다.  `HRESULT`가 매핑된 16비트 [wCode](../cpp/com-error-wcode.md)인 경우, 일반 메시지 "`IDispatch error #<wCode>`"가 반환됩니다.  메시지가 발견되지 않으면 일반 메시지 "`Unknown error #<hresult>`"가 반환됩니다.  반환된 문자열은 **\_UNICODE** 매크로의 상태에 따라 유니코드이거나 멀티바이트 문자열입니다.  
  
## 설명  
 `_com_error` 개체 내에 기록된 `HRESULT`에 대한 적절한 시스템 메시지 텍스트를 검색합니다.  시스템 메시지 텍스트는 Win32 [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) 함수를 호출하여 가져옵니다.  반환된 문자열은 `FormatMessage` API에 의해 할당되고, `_com_error` 개체가 소멸될 때 해제됩니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_error 클래스](../cpp/com-error-class.md)