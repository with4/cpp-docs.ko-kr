---
title: "OLE DB 서비스 사용 및 사용 안 함 | Microsoft Docs"
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
  - "OLE DB 서비스[OLE DB], 사용 및 사용 안 함"
  - "서비스 공급자[OLE DB]"
ms.assetid: 445f97eb-32a8-41c2-ad26-1169f78a074f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE DB 서비스 사용 및 사용 안 함
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB Service Component Manager는 소비자가 지정한 속성을 공급자가 지원하는 속성과 비교하여 소비자가 요청한 확장 기능을 제공하기 위해 개별 서비스 구성 요소를 호출할지를 결정합니다.  예를 들어, 응용 프로그램은 스크롤 가능한 커서를 요청하고 공급자는 앞으로만 이동 가능한 커서를 지원할 경우에는 Service Component Manager가 Client Cursor Engine 서비스 구성 요소를 호출하여 스크롤 가능 기능을 제공합니다.  기본적으로 응용 프로그램은 공급자의 행 집합에서 지원되는 확장 기능에 의존하므로 이 기능을 요청하기 위한 속성을 명시적으로 설정하지 않은 경우에는 Client Cursor Engine이 반환한 행 집합에 이 기능이 나타나지 않을 수 있습니다.  상호 운용성을 위해 응용 프로그램은 항상 필요한 확장 기능을 명시적으로 요청하는 속성을 설정해야 합니다.  
  
 어떤 경우에는 개별 OLE DB 서비스를 사용하지 않아야 공급자의 특징을 예상해서 만든 기존 응용 프로그램과 제대로 작동하게 됩니다.  OLE DB 서비스는 연결 기반 또는 단일 공급자를 사용하는 모든 응용 프로그램에서 개별 서비스나 모든 서비스를 사용하지 않는 기능을 제공합니다.  
  
## 참고 항목  
 [OLE DB 리소스 풀링 및 서비스](../../data/oledb/ole-db-resource-pooling-and-services.md)