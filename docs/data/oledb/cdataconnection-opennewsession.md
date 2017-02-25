---
title: "CDataConnection::OpenNewSession | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataConnection.OpenNewSession"
  - "ATL.CDataConnection.OpenNewSession"
  - "ATL::CDataConnection::OpenNewSession"
  - "OpenNewSession"
  - "CDataConnection::OpenNewSession"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OpenNewSession 메서드"
ms.assetid: 0a70e573-9498-4ca7-b524-45666dc7b0a3
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDataConnection::OpenNewSession
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 연결 개체 데이터 소스를 사용 하여 새 세션을 엽니다.  
  
## 구문  
  
```  
  
      HRESULT OpenNewSession(   
   CSession & session    
) throw( );  
```  
  
#### 매개 변수  
 `session`  
 \[in\/out\] 새 세션 개체에 대한 참조입니다.  
  
 **설명**  
 새 세션은 현재 연결 개체가 포함 된 데이터 소스 개체를 사용 하고 모두 같은 데이터 원본의 정보에 액세스할 수 있습니다.  
  
## 반환 값  
 표준 `HRESULT`입니다.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDataConnection 클래스](../../data/oledb/cdataconnection-class.md)