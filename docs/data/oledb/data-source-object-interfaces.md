---
title: "데이터 소스 개체 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "데이터 소스 개체[C++]"
  - "데이터 소스 개체[C++], 인터페이스"
  - "인터페이스[C++], 목록"
  - "인터페이스[C++], OLE DB"
  - "OLE DB[C++], 인터페이스"
  - "OLE DB 공급자 템플릿[C++], 개체 인터페이스"
ms.assetid: 929e100c-c08c-4b64-8437-d8d1357226f6
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# 데이터 소스 개체 인터페이스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 표는 OLE DB가 데이터 소스 개체에 대해 정의한 필수 인터페이스와 선택적 인터페이스를 보여 줍니다.  
  
|인터페이스|필수 여부|OLE DB 템플릿에 의해 구현되었습니까?|  
|-----------|-----------|-----------------------------|  
|`IDBCreateSession`|필수|예|  
|`IDBInitialize`|필수|예|  
|`IDBProperties`|필수|예|  
|[\<caps:sentence id\="tgt14" sentenceid\="731a3344bc1c6b5f8f54d9de3524f18a" class\="tgtSentence"\>IPersist\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms688695)|필수|예|  
|[\<caps:sentence id\="tgt17" sentenceid\="63e99e63156fc90f114fa402662387ef" class\="tgtSentence"\>IConnectionPointContainer\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms683857)|선택적|아니요|  
|`IDBDataSourceAdmin`|선택적|아니요|  
|`IDBInfo`|선택적|아니요|  
|[\<caps:sentence id\="tgt26" sentenceid\="7e6a12ecd4cb3b1bd45dccf9421ed567" class\="tgtSentence"\>IPersistFile\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms687223)|선택적|아니요|  
|`ISupportErrorInfo`|선택적|아니요|  
  
 데이터 소스 개체는 상속을 통해 `IDBProperties`, `IDBInitialize` 및 `IDBCreateSession` 인터페이스를 구현합니다.  이러한 구현 클래스 중 하나에서 상속하거나 상속하지 않도록 하여 추가 기능을 지원하도록 선택할 수 있습니다.  `IDBDataSourceAdmin` 인터페이스를 지원하려는 경우 `IDBDataSourceAdminImpl` 클래스에서 상속해야 합니다.  
  
## 참고 항목  
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)