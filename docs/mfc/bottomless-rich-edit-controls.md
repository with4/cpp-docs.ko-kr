---
title: "바닥 없는 Rich Edit 컨트롤 | Microsoft Docs"
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
  - "바닥 없는 rich edit 컨트롤"
  - "CRichEditCtrl 클래스, 바닥 없음"
  - "rich edit 컨트롤, 바닥 없음"
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 바닥 없는 Rich Edit 컨트롤
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

응용 프로그램은 rich edit 컨트롤\([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) 크기를 항상 같은 내용에 맞게 필요에 따라 조정할 수 있습니다.   Rich edit 컨트롤은 해당 내용의 크기가 변경될 때마다 부모 창에 [EN\_REQUESTRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787983)을 보냄으로써 이러한 소위 "바닥 없음" 기능을 지원합니다.  
  
 **EN\_REQUESTRESIZE** 알림 메시지를 처리할 때, 응용 프로그램은 지정된 [REQRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787950) 구조에 컨트롤을 지정된 크기로 조정해야합니다.  응용 프로그램은 또한 높이 컨트롤의 변화를 수용하기 위해 컨트롤 근처의 모든 정보를 이동 할 수 있습니다.  컨트롤의 크기를 조정 하려면  `CWnd`  함수  [SetWindowPos](../Topic/CWnd::SetWindowPos.md)을 사용합니다.  
  
 [RequestResize](../Topic/CRichEditCtrl::RequestResize.md) 멤버 함수를 사용하여   **EN\_REQUESTRESIZE** 알림 메시지를 보내기 위해 바닥 없음 rich edit 컨트롤을 할 수 있습니다.  이 메시지는 [OnSize](../Topic/CWnd::OnSize.md) 처리기에서 유용할 수 있습니다.  
  
 **EN\_REQUESTRESIZE** 알림 메시지를 받으려면  `SetEventMask`  멤버 함수를 사용해 알림을 활성화해야 합니다.  
  
## 참고 항목  
 [CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)