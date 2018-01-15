---
title: "CWnd 개체 초기화 시점 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- window objects [MFC], when to initialize CWnd
- initializing CWnd objects [MFC]
- initializing objects [MFC], CWnd
- CWnd objects [MFC], when HWND is attached
- HWND, when attached to CWnd object
- CWnd objects [MFC], when to initialize
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3d1efceb4fa826d5cd2bf8dc900180eb36cea4de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="when-to-initialize-cwnd-objects"></a>CWnd 개체 초기화 시점
생성자에서 모든 Windows API 함수를 호출 하거나 사용자 고유의 자식 창을 만들 수 없습니다는 `CWnd`-파생 된 개체입니다. 때문에 이것이 `HWND` 에 대 한는 `CWnd` 개체 아직 생성 되지 않은 합니다. 자식 창에 추가 하는 등의 가장 Windows 관련 초기화를 수행 해야 합니다는 [OnCreate](../mfc/reference/cwnd-class.md#oncreate) 메시지 처리기입니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [문서 프레임 창 만들기](../mfc/creating-document-frame-windows.md)  
  
-   [문서/뷰 만들기](../mfc/document-view-creation.md)  
  
## <a name="see-also"></a>참고 항목  
 [프레임 창 사용](../mfc/using-frame-windows.md)

