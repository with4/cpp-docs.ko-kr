---
title: "공급자가 지원하지 않는 데이터 변환 | Microsoft Docs"
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
  - "OLE DB 공급자 템플릿, 지원되지 않는 데이터 형식"
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 공급자가 지원하지 않는 데이터 변환
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

공급자가 지원하지 않는 데이터 형식을 소비자가 요청하면 `IRowsetImpl::GetData`에 대한 OLE DB 공급자 템플릿 코드가 Msdadc.dll을 호출하여 데이터 형식을 변환합니다.  
  
 `IRowsetChange`와 같이 데이터 변환이 필요한 인터페이스를 구현할 경우에는 Msdaenum.dll을 호출하여 변환할 수 있습니다.  Atldb.h에 정의된 `GetData`를 예제로 사용합니다.  
  
## 참고 항목  
 [OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)