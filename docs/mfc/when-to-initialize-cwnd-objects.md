---
title: CWnd 개체 초기화 시점 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window objects [MFC], when to initialize CWnd
- initializing CWnd objects [MFC]
- initializing objects [MFC], CWnd
- CWnd objects [MFC], when HWND is attached
- HWND, when attached to CWnd object
- CWnd objects [MFC], when to initialize
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ee10a4632809a224028bfa482f80ed9e8a9334a5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382875"
---
# <a name="when-to-initialize-cwnd-objects"></a>CWnd 개체 초기화 시점
생성자에서 모든 Windows API 함수를 호출 하거나 사용자 고유의 자식 창을 만들 수 없습니다는 `CWnd`-파생 된 개체입니다. 때문에 이것이 `HWND` 에 대 한는 `CWnd` 개체 아직 생성 되지 않은 합니다. 자식 창에 추가 하는 등의 가장 Windows 관련 초기화를 수행 해야 합니다는 [OnCreate](../mfc/reference/cwnd-class.md#oncreate) 메시지 처리기입니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아보려는 항목  
  
-   [문서 프레임 창 만들기](../mfc/creating-document-frame-windows.md)  
  
-   [문서/뷰 만들기](../mfc/document-view-creation.md)  
  
## <a name="see-also"></a>참고 항목  
 [프레임 창 사용](../mfc/using-frame-windows.md)

