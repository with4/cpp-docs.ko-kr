---
title: 해당 HWND에서에서 CWnd 분리 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CWnd
dev_langs:
- C++
helpviewer_keywords:
- HWND, detaching CWnd from
- removing HWNDs from CWnds
- CWnd objects [MFC], detaching from HWND
- detaching CWnds from HWNDs
- Detach method (CWnd class)
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a776b4ff4799750c89a322379a063030db748eec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342682"
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>CWnd를 해당 HWND에서 분리
개체-을 우회 하는 경우`HWND` 다른 관계, MFC는 `CWnd` 멤버 함수 [분리](../mfc/reference/cwnd-class.md#detach)는 c + + 창 개체 Windows 창에서 연결을 끊습니다. 이 소멸자는 개체가 소멸 될 때 Windows 창을 제거를 차단 합니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아보려는 항목  
  
-   [창 만들기](../mfc/creating-windows.md)  
  
-   [창 소멸 시퀀스](../mfc/window-destruction-sequence.md)  
  
-   [에 할당 하 고 창 메모리 할당 해제](../mfc/allocating-and-deallocating-window-memory.md)  
  
## <a name="see-also"></a>참고 항목  
 [창 개체](../mfc/window-objects.md)

