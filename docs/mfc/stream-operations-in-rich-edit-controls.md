---
title: "Rich Edit 컨트롤의 스트림 작업 | Microsoft Docs"
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
  - "CRichEditCtrl 클래스, 스트림 작업"
  - "CRichEditCtrl 클래스, 스트림 저장소"
  - "rich edit 컨트롤, 스트림 작업"
  - "저장소, CRichEditCtrl의 스트림"
  - "CRichEditCtrl의 스트림 작업"
  - "스트림 저장소 및 CRichEditCtrl"
ms.assetid: 110b4684-1e76-4ca6-9ef0-5bc8b2d93c78
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Rich Edit 컨트롤의 스트림 작업
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

데이터를 rich 편집 컨트롤\([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\)로 전송하거나 빼내기 위해서 스트림을 사용할 수 있습니다.  버퍼와 응용 프로그램에서 정의된 콜백 함수를 지정하는 [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) 구조체에 의해 정의된 스트림입니다.  
  
 데이터를 rich 편집 컨트롤로 읽기 위해서\(데이터를 스트림 인하기 위해\) [StreamIn](../Topic/CRichEditCtrl::StreamIn.md) 멤버 함수를 사용합니다.  컨트롤이 반복하여 매번 데이터의 일부를 버퍼로 전송하는 응용 프로그램 정의 호출 함수를 호출합니다.  
  
 rich 편집 컨트롤의 내용을 저장하기 위해\(데이터를 스트림 아웃하기 위해\), [StreamOut](../Topic/CRichEditCtrl::StreamOut.md) 멤버 함수를 사용할 수 있습니다.  컨트롤은 반복적으로 버퍼에 쓰고 응용 프로그램 정의 호출 함수를 호출합니다.  각 호출마다, 호출 함수는 버퍼의 내용을 저장합니다.  
  
## 참고 항목  
 [CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)