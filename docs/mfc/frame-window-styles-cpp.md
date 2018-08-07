---
title: 프레임 창 스타일 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window styles [MFC]
- PreCreateWindow method, setting window styles
- windows [MFC], MFC
- frame windows [MFC], styles
- MFC, frame windows
- styles [MFC], windows
ms.assetid: fc5058c1-eec8-48d8-9f76-3fc01cfa53f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 102b3a4c8372a53aada23ad448ce5dc1cf323a97
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343762"
---
# <a name="frame-window-styles-c"></a>프레임 창 스타일(C++)
프레임 창 프레임 워크와 이용은 대부분의 프로그램에 대 한 적합 하지만 고급 함수를 사용 하 여 추가적인 유연성을 얻을 수 있는 [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) MFC 전역 함수 및 [AfxRegisterWndClass ](../mfc/reference/application-information-and-management.md#afxregisterwndclass). `PreCreateWindow` 멤버 함수는 `CWnd`합니다.  
  
 적용 하는 경우는 **WS_HSCROLL** 및 **WS_VSCROLL** 주 프레임 창에 스타일, 대신에 적용 되는 **MDICLIENT** 사용자는 스크롤할수있도록창**MDICLIENT** 영역입니다.  
  
 경우 창의 **FWS_ADDTOTITLE** 스타일 비트가 설정 되 면 (기본적으로이), 뷰 보기의 문서 이름을 기반으로 하는 창의 제목 표시줄에 표시할 제목을 프레임 창에 알립니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아보려는 항목  
  
-   [MDI 자식 창 (MDICLIENT) 관리](../mfc/managing-mdi-child-windows.md), MDI 자식 창이 포함 된 MDI 프레임 창  
  
-   [MFC에서 만든 창 스타일 변경](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
-   [창 스타일](../mfc/reference/styles-used-by-mfc.md#window-styles)  
  
## <a name="see-also"></a>참고 항목  
 [프레임 창](../mfc/frame-windows.md)

