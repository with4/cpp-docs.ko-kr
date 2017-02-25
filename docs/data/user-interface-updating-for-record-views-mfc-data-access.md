---
title: "레코드 뷰의 사용자 인터페이스 업데이트  (MFC Data Access) | Microsoft Docs"
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
  - "메뉴, 컨텍스트 변경으로 업데이트"
  - "레코드 뷰, 사용자 인터페이스"
  - "사용자 인터페이스, 업데이트"
ms.assetid: 2c7914b6-2dc3-40c3-b2f2-8371da2a4063
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 레코드 뷰의 사용자 인터페이스 업데이트  (MFC Data Access)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CRecordView` 및 `CDaoRecordView`는 탐색 명령에 대한 기본 사용자 인터페이스 업데이트 처리기도 제공합니다.  이러한 처리기는 사용자 인터페이스 개체\(메뉴 항목 및 도구 모음 단추\)를 자동으로 시용하거나 사용하지 않도록 설정합니다.  응용 프로그램 마법사는 표준 메뉴를 제공하며 **도킹 가능한 도구 모음** 옵션을 선택하는 경우 명령의 도구 모음 단추 집합을 제공합니다.  `CRecordView`를 사용하여 레코드 뷰 클래스를 만드는 경우 응용 프로그램에 비슷한 사용자 인터페이스 개체를 추가할 수 있습니다.  
  
### 메뉴 편집기를 사용하여 메뉴 리소스를 만들려면  
  
1.  [메뉴 편집기](../mfc/menu-editor.md)를 사용하는 방법에 대한 정보를 참조하여 같은 명령 4개가 있는 메뉴를 만듭니다.  
  
#### 그래픽 편집기를 사용하여 도구 모음 단추를 만들려면  
  
1.  [도구 모음 편집기](../mfc/toolbar-editor.md)를 사용하는 방법에 대한 정보를 참조하여 도구 모음 리소스를 편집해 레코드 탐색 명령에 해당하는 도구 모음 단추를 추가합니다.  
  
## 참고 항목  
 [레코드 뷰에서의 탐색 지원](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)   
 [레코드 뷰 사용](../data/using-a-record-view-mfc-data-access.md)