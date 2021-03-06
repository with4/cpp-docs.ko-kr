---
title: 창 개체 제거 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3aacb01d945429bc36543f78e3635c39ef58223d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343378"
---
# <a name="destroying-window-objects"></a>창 개체 제거
주의 해야 자신의 자식 창으로 창을 사용 하 여 사용자가 완료 하는 경우 c + + 창 개체를 제거할 수 있습니다. 이러한 개체가 소멸 되지 않습니다 응용 프로그램에서 메모리를 복구 하지 않습니다. 다행히 프레임 워크는 프레임 창, 뷰 및 대화 상자에 대 한 작성 뿐만 아니라 창 소멸을 관리합니다. 추가로 창을 만드는 모르는 경우을 제거 해야 합니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아보려는 항목  
  
-   [창 소멸 시퀀스](../mfc/window-destruction-sequence.md)  
  
-   [에 할당 하 고 창 메모리 할당 해제](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [해당 HWND에서에서 CWnd 분리](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
-   [일반 창 만들기 시퀀스](../mfc/general-window-creation-sequence.md)  
  
-   [프레임 창 소멸 시키기](../mfc/destroying-frame-windows.md)  
  
## <a name="see-also"></a>참고 항목  
 [창 개체](../mfc/window-objects.md)

