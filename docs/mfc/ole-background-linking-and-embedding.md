---
title: "OLE 백그라운드: 연결 및 포함 | Microsoft Docs"
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
  - "포함 개체[C++]"
  - "항목 형식"
  - "항목 형식, 정의"
  - "연결된 항목(OLE)[C++]"
  - "OLE 포함 항목"
  - "OLE 항목, 형식"
  - "OLE, 연결된 항목"
ms.assetid: 11107711-eb96-4099-8f5c-7910bb3ecb75
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# OLE 백그라운드: 연결 및 포함
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

컨테이너 응용 프로그램에서 붙여넣기 명령을 사용하여 포함된 구성 요소 또는 포함된 항목을 생성할 수 있습니다.  포함된 항목에 대한 원본 데이터는 그것을 포함한 OLE 문서의 일부로서 저장됩니다.  이런 방법으로 워드 프로세서 문서의 문서 파일은 텍스트, 비트맵, 그래프, 수식, 데이터의 다른 형식도 포함할 수 있습니다.  
  
 OLE은 다른 응용 프로그램에서 데이터를 포함하기 위한 다른 방법을 제공합니다. 연결된 구성 요소, 연결된 항목 또는 링크를 생성하는 방법입니다.  연결된 항목을 만드는 단계는 붙여넣기 명령 대신 사용자가 붙여넣기 연결 명령을 사용하는 것을 제외하고 포함된 항목을 생성하는 것과 유사합니다.  포함된 구성 요소와는 달리, 연결된 구성 요소는 경로를 원본 데이터에 저장합니다. 이는 가끔 분리된 파일에 저장됩니다.  
  
 예를 들어, 워드 프로세서 문서에서 작업하고 몇몇 스프레드시트 셀에 연결된 항목을 생성하는 경우, 연결된 항목에 대한 데이터는 원본 스프레드시트 문서에 저장됩니다.  워드 프로세서 문서는 오직 항목이 발견될 수 있는 곳을 지정하는 정보만을 포함합니다. 그것은 원본 스프레드시트 문서로 하는 연결을 포함합니다.  셀을 더블클릭할 때, 스프레드시트 응용 프로그램이 시작되고 원본 스프레드시트 문서가 저장된 위치에서 로드됩니다.  
  
 포함되었거나 연결된 모든 OLE 항목은 생성한 응용 프로그램에 기초하여 연관된 형식을 갖습니다.  예를 들어, Microsoft 그림판 항목은 항목의 한 형식이고, Microsoft Excel 항목은 다른 형식입니다.  그러나 하나의 항목 형식보다 많은 일부 응용 프로그램 항목 형식을 만들 수 있습니다.  예를 들어, Microsoft Excel는 워크시트 항목, 차트 항목 및 매크로시트 항목을 만들 수 있습니다.  이러한 각 항목은 클래스 식별자 또는 **CLSID**을 사용하여 시스템에 의해 고유하게 식별될 수 있습니다.  
  
## 참고 항목  
 [OLE 백그라운드](../mfc/ole-background.md)   
 [OLE 백그라운드: 컨테이너 및 서버](../mfc/ole-background-containers-and-servers.md)   
 [컨테이너: 클라이언트 항목](../mfc/containers-client-items.md)   
 [서버: 서버 항목](../mfc/servers-server-items.md)