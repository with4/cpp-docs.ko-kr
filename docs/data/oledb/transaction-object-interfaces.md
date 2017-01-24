---
title: "트랜잭션 개체 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "인터페이스, 목록"
  - "인터페이스, OLE DB"
  - "OLE DB 공급자 템플릿, 개체 인터페이스"
  - "OLE DB 공급자, 트랜잭션 지원"
  - "OLE DB, 인터페이스"
  - "트랜잭션 개체 인터페이스"
ms.assetid: d2ce99ce-6f7a-4ff9-bc6e-acda3633d5c8
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 트랜잭션 개체 인터페이스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

트랜잭션 개체는 데이터 소스에 대한 작업의 원자 단위를 정의하고 이러한 작업 단위가 서로 연관되는 방법을 결정합니다.  이 개체는 OLE DB 공급자가 직접 지원하지 않으므로 사용자가 직접 만들어야 합니다.  
  
 다음 표는 OLE DB가 트랜잭션 개체에 대해 정의한 필수 인터페이스와 선택적 인터페이스를 보여 줍니다.  
  
|인터페이스|필수 여부|OLE DB 템플릿에 의해 구현되었습니까?|  
|-----------|-----------|-----------------------------|  
|[\<caps:sentence id\="tgt7" sentenceid\="63e99e63156fc90f114fa402662387ef" class\="tgtSentence"\>IConnectionPointContainer\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms683857)|필수|아니요|  
|[\<caps:sentence id\="tgt10" sentenceid\="f5097e646bb93cceb560c38e13953a89" class\="tgtSentence"\>ITransaction\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms723053.aspx)|필수|아니요|  
|[\<caps:sentence id\="tgt13" sentenceid\="130702210bcc45e1afd88b1f2aae1a0b" class\="tgtSentence"\>ISupportErrorInfo\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms715816.aspx)|선택적|아니요|  
  
## 참고 항목  
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)