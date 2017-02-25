---
title: "_com_error::HRESULTToWCode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "HRESULTToWCode"
  - "_com_error.HRESULTToWCode"
  - "_com_error::HRESULTToWCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HRESULTToWCode 메서드"
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::HRESULTToWCode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 32비트 `HRESULT`를 16비트 `wCode`에 매핑합니다.  
  
## 구문  
  
```  
  
      static WORD HRESULTToWCode(  
   HRESULT hr   
) throw( );  
```  
  
#### 매개 변수  
 `hr`  
 16비트 `wCode`에 매핑할 32비트 `HRESULT`입니다.  
  
## 반환 값  
 32비트 `HRESULT`에서 매핑된 16비트 `wCode`입니다.  
  
## 설명  
 자세한 내용은 [\_com\_error::WCode](../cpp/com-error-wcode.md)를 참조하십시오.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_error::WCode](../cpp/com-error-wcode.md)   
 [\_com\_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [\_com\_error 클래스](../cpp/com-error-class.md)