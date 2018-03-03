---
title: "프레임 창 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- frame window classes [MFC], about frame window classes
- frame window classes [MFC]
- windows [MFC], MDI
- document frame windows [MFC], classes
- single document interface (SDI), frame windows
- window classes [MFC], frame
- MFC, frame windows
- MDI [MFC], frame windows
- classes [MFC], window
ms.assetid: c27e43a7-8ad0-4759-b1b7-43f4725f4132
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b5e67ef155c029285d0b306ca2d05179e993de78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="frame-window-classes"></a>프레임 창 클래스
각 응용 프로그램 "주 프레임 창," 캡션을 응용 프로그램 이름은 일반적으로 사용 하는 데스크톱 창 하나를 취합니다. 각 문서 일반적으로 개가 "문서 프레임 창입니다." 문서 프레임 창에 문서의 데이터를 표시 하는 하나 이상의 보기가 있습니다.  
  
## <a name="frame-windows-in-sdi-and-mdi-applications"></a>SDI 및 MDI 응용 프로그램의 프레임 창  
 SDI 응용 프로그램에 대 한가 한 프레임 창 클래스에서 파생 된 [CFrameWnd](../mfc/reference/cframewnd-class.md)합니다. 이 창은 주 프레임 창 및 문서 프레임 창 모두입니다. MDI 응용 프로그램에 대 한 주 프레임 창 클래스에서 파생 되며 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), 요소인 MDI 자식 창을 문서 프레임 창 클래스에서 파생 되 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)합니다.  
  
## <a name="use-the-frame-window-class-or-derive-from-it"></a>프레임 창 클래스를 사용 하 여 또는에서 파생  
 이러한 클래스는 대부분의 응용 프로그램에 필요한 프레임 창 기능을 제공 합니다. 정상적인 상황에서는 기본 동작 및 모양을 제공 요구 사항에 맞게 됩니다. 추가 기능이 필요한 경우 이러한 클래스에서 파생 됩니다.  
  
### <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [응용 프로그램 마법사로 만든 프레임 창 클래스](../mfc/frame-window-classes-created-by-the-application-wizard.md)  
  
-   [프레임 창 스타일](../mfc/frame-window-styles-cpp.md)  
  
-   [MFC에서 만든 창 스타일 변경](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
## <a name="see-also"></a>참고 항목  
 [프레임 창](../mfc/frame-windows.md)

