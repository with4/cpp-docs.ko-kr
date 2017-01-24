---
title: "끌어서 놓기: 놓기 소스 구현 | Microsoft Docs"
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
  - "끌어서 놓기, DoDragDrop 호출"
  - "끌어서 놓기, 놓기 소스"
  - "끌어서 놓기, 끌기 작업 시작"
  - "OLE 끌어서 놓기, DoDragDrop 호출"
  - "OLE 끌어서 놓기, 놓기 소스"
  - "OLE 끌어서 놓기, 끌기 작업 시작"
ms.assetid: 0ed2fda0-63fa-4b1e-b398-f1f142f40035
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 끌어서 놓기: 놓기 소스 구현
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서는 끌어서 놓기 작업에 데이터를 제공하는 응용 프로그램을 얻는 방법에 대해 설명합니다.  
  
 놓기 소스의 기본 구현은 비교적 간단합니다.  첫 번째 단계는 끌기 작업을 시작하는 이벤트를 결정하는 것입니다.  사용자 인터페이스 설명지침은 끌기 작업의 시작을 데이터 선택 영역과 선택된 데이터 내부의 지점에서 발생한  `WM_LBUTTONDOWN` 이벤트로서 정의하는 것이 권장됩니다.  MFC OLE 샘플 [OCLIENT](../top/visual-cpp-samples.md) 및 [HIERSVR](../top/visual-cpp-samples.md)은 이 설명 지침을 따릅니다.  
  
 응용 프로그램이 컨테이너이고 선택된 데이터가 형식 `COleClientItem`의 연결되거나 포함된 개체인 경우, `DoDragDrop` 멤버 함수를 호출합니다.  그렇지 않으면 `COleDataSource` 개체를 수행하고, 선택 영역을 사용하여 그것을 초기화하고, 데이터 소스 개체의 `DoDragDrop` 멤버 함수를 호출합니다.  응용 프로그램이 서버인 경우, `COleServerItem::DoDragDrop`를 사용합니다.  표준 끌어서 놓기 동작을 사용자 지정하는 방법에 대한 추가 정보는, [Drag and Drop: Customizing](../mfc/drag-and-drop-customizing.md)를 참조하세요.  
  
 `DoDragDrop`가 `DROPEFFECT_MOVE`를 반환하면, 원본 문서에서 원본 데이터를 즉시 삭제합니다.  모든 다른 `DoDragDrop`로부터의 반환값은 놓기 소스에 영향을 미치지 못합니다.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [놓기 대상 구현](../mfc/drag-and-drop-implementing-a-drop-target.md)  
  
-   [사용자 지정 끌어서 놓기](../mfc/drag-and-drop-customizing.md)  
  
-   [OLE 데이터 개체 및 데이터 소스를 생성하거나 소멸시키기](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [데이터 개체 및 데이터 소스 조작](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## 참고 항목  
 [끌어서 놓기\(OLE\)](../mfc/drag-and-drop-ole.md)   
 [COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md)   
 [COleClientItem::DoDragDrop](../Topic/COleClientItem::DoDragDrop.md)   
 [CView::OnDragLeave](../Topic/CView::OnDragLeave.md)