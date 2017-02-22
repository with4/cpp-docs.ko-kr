---
title: "그래픽 개체를 선택하여 장치 컨텍스트로 넣기 | Microsoft Docs"
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
  - "장치 컨텍스트, 그래픽 개체"
  - "장치 컨텍스트, 그래픽 개체 선택"
  - "GDI 개체[C++], 장치 컨텍스트"
  - "그래픽 개체, 장치 컨텍스트에서 선택"
  - "수명, 그래픽 개체"
  - "SelectObject 메서드"
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 그래픽 개체를 선택하여 장치 컨텍스트로 넣기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This topic applies to using graphic objects in a window's device context.  After you [create a drawing object](../mfc/one-stage-and-two-stage-construction-of-objects.md), you must select it into the device context in place of the default object stored there:  
  
 [!code-cpp[NVC_MFCDocViewSDI#7](../mfc/codesnippet/CPP/selecting-a-graphic-object-into-a-device-context_1.cpp)]  
  
## Lifetime of Graphic Objects  
 The graphic object returned by [SelectObject](../Topic/CDC::SelectObject.md) is "temporary." That is, it will be deleted by the [OnIdle](../Topic/CWinApp::OnIdle.md) member function of class `CWinApp` the next time the program gets idle time.  As long as you use the object returned by `SelectObject` in a single function without returning control to the main message loop, you will have no problem.  
  
### 추가 정보  
  
-   [Graphic objects](../mfc/graphic-objects.md)  
  
-   [One\-stage and two\-stage construction of graphic objects](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [Device contexts](../mfc/device-contexts.md)  
  
-   [Drawing in a View](../mfc/drawing-in-a-view.md)  
  
## 참고 항목  
 [그래픽 개체](../mfc/graphic-objects.md)