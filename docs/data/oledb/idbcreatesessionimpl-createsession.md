---
title: "IDBCreateSessionImpl::CreateSession | Microsoft Docs"
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
  - "IDBCreateSessionImpl::CreateSession"
  - "IDBCreateSessionImpl.CreateSession"
  - "CreateSession"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateSession 메서드"
ms.assetid: 035e5ddb-56e6-43b1-874d-89c0e40b103b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBCreateSessionImpl::CreateSession
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

데이터 소스 개체에서 새 세션을 만들고 새로 생성된 된 세션에서 요청된 된 인터페이스를 반환 합니다.  
  
## 구문  
  
```  
  
      STDMETHOD(CreateSession)(   
   IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppDBSession    
);  
```  
  
#### 매개 변수  
 자세한 내용은 *OLE DB Programmer's Reference*에 있는 [IDBCreateSession::CreateSession](https://msdn.microsoft.com/en-us/library/ms714942.aspx)를 참조하십시오.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IDBCreateSessionImpl 클래스](../../data/oledb/idbcreatesessionimpl-class.md)