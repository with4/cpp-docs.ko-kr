---
title: "_com_error::WCode | Microsoft Docs"
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
  - "_com_error.WCode"
  - "_com_error::WCode"
  - "WCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WCode 메서드"
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::WCode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 캡슐화된 `HRESULT`에 매핑되는 16비트 오류 코드를 검색합니다.  
  
## 구문  
  
```  
  
WORD WCode ( ) const throw( );  
  
```  
  
## 반환 값  
 `HRESULT`의 범위가 0x80040200 ~ 0x8004FFFF이면 **WCode** 메서드는 `HRESULT`에서 0x80040200을 뺀 값을 반환하고, 그렇지 않으면 0을 반환합니다.  
  
## 설명  
 **WCode** 메서드는 COM 지원 코드에서 발생하는 매핑을 실행 취소하는 데 사용됩니다.  **dispinterface** 속성 또는 메서드에 대한 래퍼는 인수를 패키징하고 **IDispatch::Invoke**를 호출하는 지원 루틴을 호출합니다.  반환 시 `DISP_E_EXCEPTION`의 `HRESULT` 오류가 반환되면 **IDispatch::Invoke**에 전달된 **EXCEPINFO** 구조체에서 오류 정보가 검색됩니다.  오류 코드는 **EXCEPINFO** 구조체의 `wCode` 멤버에 저장된 16비트 값이거나 **EXCEPINFO** 구조체의 **scode** 멤버에 저장된 전체 32비트 값일 수 있습니다.  16비트 `wCode`가 반환되면 먼저 32비트 오류 `HRESULT`에 매핑되어야 합니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [\_com\_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [\_com\_error 클래스](../cpp/com-error-class.md)