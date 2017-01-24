---
title: "OLE DB 소비자 및 공급자 | Microsoft Docs"
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
  - "OLE DB 소비자"
  - "OLE DB 소비자, OLE DB 데이터 아키텍처"
  - "OLE DB 공급자"
  - "OLE DB 공급자, OLE DB 데이터 아키텍처"
  - "OLE DB, 데이터 모델"
ms.assetid: 886cb39d-652b-4557-93f0-4b1b0754d8bc
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE DB 소비자 및 공급자
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB 아키텍처는 소비자와 공급자 모델을 사용합니다.  소비자는 데이터를 요청하며,  공급자는 표 형식에 데이터를 입력하고 소비자에게 반환함으로써 이러한 요청에 응답합니다.  고객이 하는 모든 호출은 공급자에서 구현되어야 합니다.  
  
 엄밀한 의미의 소비자는 OLE DB 인터페이스를 거쳐 데이터에 액세스하는 시스템이나 응용 프로그램 코드\(OLE DB 구성 요소 불필요\)입니다.  인터페이스는 공급자에서 구현됩니다.  따라서 공급자는 데이터에 대한 액세스를 캡슐화하고 다른 개체\(즉, 소비자\)에 노출하도록 OLE DB 인터페이스를 구현하는 소프트웨어 구성 요소입니다.  
  
 역할면에 있어서 소비자는 OLE DB 인터페이스에서 메서드를 호출하고, OLE DB 공급자는 요구된 OLE DB 인터페이스를 구현합니다.  
  
 OLE DB에서는 클라이언트와 서버 역할이 모든 경우에 의미가 통하는 것이 아니므로\(특히 n 계층 상황인 경우\) 클라이언트와 서버라는 용어를 사용하지 않습니다.  계층에서 소비자는 다른 구성 요소에 대한 서버가 될 수도 있으므로 소비자를 클라이언트라고 하면 혼동의 소지가 있습니다.  또한 공급자는 때때로 서버 라기 보다는 데이터베이스 드라이버처럼 작동합니다.  
  
## 참고 항목  
 [OLE DB 프로그래밍](../../data/oledb/ole-db-programming.md)   
 [OLE DB 프로그래밍 개요](../../data/oledb/ole-db-programming-overview.md)