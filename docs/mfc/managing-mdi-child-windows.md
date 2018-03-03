---
title: "MDI 자식 창 관리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MDICLIENT
dev_langs:
- C++
helpviewer_keywords:
- MDI [MFC], child windows
- child windows [MFC], and MDICLIENT window
- MDICLIENT window [MFC]
- windows [MFC], MDI
- frame windows [MFC], MDI child windows
- child windows [MFC]
- MDI [MFC], frame windows
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5ebcd6e484385ada3cd3d5ccfe450e7e25f539eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="managing-mdi-child-windows"></a>MDI 자식 창 관리
MDI 주 프레임 창 (응용 프로그램 당 하나) 라는 특수 한 자식 창이 포함 된 **MDICLIENT** 창. **MDICLIENT** 창은 주 프레임 창의 클라이언트 영역을 관리 하 고 자식 창 자체에:에서 파생 된 문서 창인 `CMDIChildWnd`합니다. 문서 창은 그 자체로 프레임 창(MDI 자식 창)이기 때문에 고유 자식을 포함할 수도 있습니다. 이러한 모든 경우, 부모 창은 해당 자식 창을 관리하고 일부 명령을 자식 창에 전달합니다.  
  
 MDI 프레임 창, 프레임 창을 관리 하는 **MDICLIENT** 창, 컨트롤 막대와 함께에서 위치를 변경 합니다. **MDICLIENT** 창 다시 모든 MDI 자식 프레임 창을 관리 합니다. 다음 그림은 MDI 프레임 창 사이의 관계를 보여 줍니다. 그 **MDICLIENT** 창 및 해당 자식 문서 프레임 창.  
  
 ![MDI 프레임 창의 자식 창](../mfc/media/vc37gb1.gif "vc37gb1")  
MDI 프레임 창 및 자식  
  
 MDI 프레임 창은 또한 현재 MDI 자식 창(있는 경우)과 결합한 상태에서도 작동합니다. MDI 프레임 창은 명령 메시지를 직접 처리하려고 시도하기 전에 이를 먼저 MDI 자식에 위임합니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [문서 프레임 창 만들기](../mfc/creating-document-frame-windows.md)  
  
-   [프레임 창 스타일](../mfc/frame-window-styles-cpp.md)  
  
## <a name="see-also"></a>참고 항목  
 [프레임 창 사용](../mfc/using-frame-windows.md)

