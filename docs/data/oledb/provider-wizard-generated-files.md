---
title: "공급자 마법사가 생성하는 파일 | Microsoft Docs"
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
  - "OLE DB 공급자, 마법사에서 생성된 파일"
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 공급자 마법사가 생성하는 파일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL OLE DB 공급자 마법사는 다음과 같은 파일을 생성합니다.  다음 항목에서는 "MyProvider"라는 약식 이름을 사용하지만 정확한 파일 이름은 공급자를 만들 때 입력한 이름에 따라 다릅니다.  
  
|파일 이름|설명|  
|-----------|--------|  
|MyProviderRS.cpp|명령 도우미 `Execute` 메서드와 공급자 열 맵이 있습니다.|  
|MyProviderDS.h|데이터 소스 개체를 구현합니다.  이 헤더 파일에는 데이터 소스 속성에 대한 속성 맵이 있습니다.|  
|MyProviderRS.h|명령 개체와 행 집합 개체를 구현합니다.  이 헤더 파일에는 행 집합과 명령 속성에 대한 속성 맵이 있습니다.|  
|MyProviderSess.h|세션 개체를 구현합니다.  이 헤더 파일에는 세션 속성에 대한 속성 맵이 있습니다.|  
|MyProvider.rgs|ATL OLE DB 공급자 마법사가 생성한 등록된 개체가 있습니다.|  
  
## 참고 항목  
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)