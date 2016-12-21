---
title: "_com_error::WCodeToHRESULT | Microsoft Docs"
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
  - "_com_error::WCodeToHRESULT"
  - "_com_error.WCodeToHRESULT"
  - "WCodeToHRESULT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WCodeToHRESULT 메서드"
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::WCodeToHRESULT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 16비트 `wCode`를 32비트 `HRESULT`로 매핑합니다.  
  
## 구문  
  
```  
  
      static HRESULT WCodeToHRESULT(  
   WORD wCode   
) throw( );  
```  
  
#### 매개 변수  
 `wCode`  
 32비트 `HRESULT`로 매핑될 `wCode` 16비트입니다.  
  
## 반환 값  
 16비트 `wCode`에서 매핑된 32비트 `HRESULT`입니다.  
  
## 설명  
 [WCode](../cpp/com-error-wcode.md) 멤버 함수를 참조하십시오.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_error::WCode](../cpp/com-error-wcode.md)   
 [\_com\_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [\_com\_error 클래스](../cpp/com-error-class.md)