---
title: "OLE DB 리소스 풀링 및 서비스 | Microsoft Docs"
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
  - "OLE DB 공급자, 리소스 풀링"
  - "OLE DB 서비스[OLE DB]"
  - "OLE DB 서비스[OLE DB], 공급자 요구 사항"
  - "OLE DB, 리소스 풀링"
  - "리소스 풀링[OLE DB], 공급자 요구 사항"
  - "서비스 공급자[OLE DB]"
ms.assetid: 360c36e2-25ae-4caf-8ee7-d4a6b6898f68
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE DB 리소스 풀링 및 서비스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

공급자가 OLE DB 풀링이나 OLE DB 서비스와 잘 작동하려면 모든 개체 집합체를 지원해야 합니다.  이는 OLE DB 1.5 이상 공급자의 요구 사항입니다.  이는 특히 레버리징 서비스에서 중요한 사항입니다.  집합체를 지원하지 않는 공급자는 풀링될 수 없으므로 추가 서비스가 전혀 제공되지 않습니다.  
  
 공급자는 풀링되려면 자유 스레드 모델을 지원해야 합니다.  리소스 풀은 **DBPROP\_THREADMODEL** 속성에 따라 공급자의 스레드 모델을 결정합니다.  
  
 데이터 소스가 초기화된 상태에 있는 동안 공급자에 변경될 수 있는 전역 연결 상태가 있을 경우에는 공급자가 새로운 **DBPROP\_RESETDATASOURCE** 속성을 지원해야 합니다.  이 속성은 연결이 다시 사용되기 전에 호출되어 연결을 다시 사용하기 전에 상태를 정리할 수 있는 기회를 공급자에게 제공합니다.  공급자가 연결과 관련된 상태를 정리할 수 없을 경우에는 속성에 **DBPROPSTATUS\_NOTSETTABLE**을 반환할 수 있으며, 그러면 연결을 다시 사용할 수 없습니다.  
  
 원격 데이터베이스에 연결되어 연결이 끊어졌는지를 감지할 수 있는 공급자는 **DBPROP\_CONNECTIONSTATUS** 속성을 지원해야 합니다.  이 속성은 끊어진 연결을 감지하고 이러한 연결이 풀에 반환되지 않도록 하는 기능을 OLE DB 서비스에 제공합니다.  
  
 마지막으로 자동 트랜잭션 참여는 풀링이 발생하는 것과 같은 수준에서 구현하지 않으면 일반적으로 작동하지 않습니다.  자동 트랜잭션 참여를 자체적으로 지원하는 공급자는 **DBPROPVAL\_OS\_TXNENLISTMENT**선택이 해제된 경우 **DBPROP\_INIT\_OLEDBSERVICES** 속성을 노출하고 참여를 해제하는 방법으로 참여 해제를 지원해야 합니다.  
  
## 참고 항목  
 [고급 공급자 기술](../../data/oledb/advanced-provider-techniques.md)