---
title: "속성 맵 | Microsoft Docs"
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
  - "맵, 속성"
  - "OLE DB 공급자, 속성"
  - "속성 맵"
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 속성 맵
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

각 공급자는 세션, 행 집합 및 선택적 명령 개체 외에 하나 이상의 속성을 지원합니다.  이러한 속성은 ATL OLE DB 공급자 마법사가 만든 헤더 파일의 속성 맵에 정의됩니다.  각 헤더 파일에는 그 파일에서 정의된 개체나 개체들에 대해 정의한 OLE DB 속성 그룹의 속성에 대한 맵이 있습니다.  데이터 소스 개체가 있는 헤더 파일에는 [DataSource properties](https://msdn.microsoft.com/en-us/library/ms724188\(v=vs.140\).aspx)에 대한 속성 맵이 있습니다.  Session.h에는 [Session properties](https://msdn.microsoft.com/en-us/library/ms714221.aspx)에 대한 속성 맵이 있습니다.  행 집합 개체와 명령 개체는 *projectname*RS.h라는 단일 헤더 파일에 있습니다.  이러한 속성은 [Rowset properties](https://msdn.microsoft.com/en-us/library/ms711252.aspx) 그룹의 멤버입니다.  
  
## 참고 항목  
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)