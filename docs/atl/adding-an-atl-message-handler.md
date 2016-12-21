---
title: "ATL 메시지 처리기 추가 | Microsoft Docs"
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
  - "ATL, 메시지 처리기"
  - "ATL, windows"
  - "message handlers [C++]"
  - "message handling [C++], ATL message handler"
  - "windows [C++], ATL"
ms.assetid: cdea38a1-0d9b-4f8d-bbd5-b4f063fb3eeb
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL 메시지 처리기 추가
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

컨트롤에 메시지 처리기 \(Windows 메시지를 처리 하는 멤버 함수\)를 추가 하려면 먼저 클래스 뷰에서 컨트롤을 선택 합니다.  다음 열은  **속성** 창에서의  **메시지** 아이콘과 드롭다운 목록 제어 반대쪽 필요 메시지 상자에서 클릭.  이 컨트롤의 헤더 파일 및 컨트롤의.cpp 파일에 처리기의 기초 구현을 선언에 대 한 메시지 처리기를 추가 합니다.  또한 메시지 맵과 고 처리기에 대 한 항목이 추가 됩니다.  
  
 ATL 메시지 처리기 추가 MFC 클래스에 메시지 처리기를 추가 하는 것과 비슷합니다.  참조  [MFC 메시지 처리기 추가](../mfc/reference/adding-an-mfc-message-handler.md) 에 대 한 자세한 내용은.  
  
 다음과 같은 ATL 메시지 처리기를 추가에 적용 됩니다.  
  
-   메시지 처리기는 MFC와 같은 명명 규칙을 따릅니다.  
  
-   새 메시지 맵 항목은 주 메시지 맵에 추가 됩니다.  마법사는 대체 메시지 맵과 체인을 인식 하지 못합니다.  
  
## 참고 항목  
 [Implementing a Window](../atl/implementing-a-window.md)