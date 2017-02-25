---
title: "액티브 문서 서버 | Microsoft Docs"
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
  - "액티브 문서 서버[C++]"
  - "활성 문서[C++], 서버"
  - "서버[C++], 활성 문서"
ms.assetid: 131fec1e-02a0-4305-a7ab-903b911232a7
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 액티브 문서 서버
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Word, Excel 또는 PowerPoint와 같은 활성 문서 서버는 활성 문서로 불리는 다른 응용 프로그램 형식의 문서를 호스트합니다.  OLE 포함 개체\(다른 문서 페이지 안에 간단히 표시된\)와는 달리, 활성 문서는 모든 인터페이스를 제공하고 그들을 생성하는 서버 응용 프로그램의 원시 기능을 완성합니다.  사용자는 자신이 좋아하는 응용 프로그램의 모든 기능을 사용하여 문서를 만들 수 있습니다\(사용가능한 활성 문서일 경우\). 그러나 결과 프로젝트를 하나의 독립체로 취급할 수 없습니다.  
  
 활성 문서는 두 페이지 이상을 가질 수 있고 언제나 활성 준비중입니다.  활성 문서는 컨테이너의 **File** 및 **Help** 메뉴와 함께 메뉴를 병합하기 위해서 사용자 인터페이스의 일부를 제어합니다.  그들은 컨테이너의 전체 편집 영역을 사용하고 보기와 프린터 용지의 레이아웃\(여백, 바닥글 등\)을 제어합니다.  
  
 MFC는 문서\/보기 인터페이스, 커맨드 디스패치 맵, 인쇄, 메뉴 관리, 레지스트리 관리를 사용하여 활성 문서 서버를 구현합니다.  특정 프로그래밍 요구 사항은 [액티브 문서](../mfc/active-documents.md)에 설명되어 있습니다.  
  
 MFC는 [CCmdTarget](../mfc/reference/ccmdtarget-class.md)에서 파생된 [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md) 클래스 및 [COleServerItem](../mfc/reference/coleserveritem-class.md)에서 파생된 [CDocObjectServerItem](../mfc/reference/cdocobjectserveritem-class.md)을 사용하여 활성 문서를 지원합니다.  MFC는 [COleClientItem](../mfc/reference/coleclientitem-class.md)에서 파생된 [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md) 클래스를 사용하여 활성 문서 컨테이너를 지원합니다.  
  
 `CDocObjectServer`는 활성 문서 인터페이스를 매핑하고, 초기화하고, 활성 문서를 활성화시킵니다.  또한 MFC는 활성 문서에서 명령 라우팅을 처리하는 매크로를 제공합니다.  응용 프로그램에서 활성 문서를 사용하기 위해서는, StdAfx.h 파일의 AfxDocOb.h를 포함하십시오.  
  
 일반 MFC 서버는 그들의 자체 `COleServerItem`\-파생된 클래스를 연결합니다.  사용자가 **Mini\-server** 또는 응용 프로그램 서버에 복합 문서 지원을 제공하는 **Full\-serve** 확인란을 선택하면, MFC 응용 프로그램 마법사는 사용자를 위해 이 클래스를 생성합니다.  **Active document server** 확인란을 선택하면, MFC 응용 프로그램 마법사는 대신  `CDocObjectServerItem`에서 유래된 클래스를 생성합니다.  
  
 `COleDocObjectItem` 클래스는 OLE 컨테이너가 활성 문서 컨테이너가 되도록 합니다.  사용자는 MFC 응용 프로그램 마법사의 복합 문서 지원 페이지에서 **Active document container** 확인란을 선택하여 활성 문서 컨테이너를 만드는 MFC 응용 프로그램 마법사를 사용할 수 있습니다.  자세한 내용은 [활성 문서 컨테이너 응용 프로그램 생성](../mfc/creating-an-active-document-container-application.md)을 참조하십시오.  
  
## 참고 항목  
 [액티브 문서 포함](../mfc/active-document-containment.md)