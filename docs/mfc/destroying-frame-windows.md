---
title: "프레임 창 소멸 시키기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PostNcDestroy
dev_langs: C++
helpviewer_keywords:
- Default method [MFC]
- DestroyWindow method [MFC]
- frame windows [MFC], destroying
- OnNcDestroy method, and frame windows
- document frame windows [MFC], destroying
- destroying frame windows
- MFC, frame windows
- windows [MFC], destroying
- OnClose method [MFC]
- PostNcDestroy method [MFC]
ms.assetid: 5affca77-1999-4507-a2b2-9aa226611b4b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f1cbd96f5044626c7c3c07e8fca115c2b1dca8cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="destroying-frame-windows"></a>프레임 창 제거
MFC 프레임 워크는 프레임 워크 문서 및 뷰를와 연결 된 해당 창에 대 한 작성 뿐만 아니라 창 소멸을 관리 합니다. 추가로 창을 만드는 모르는 경우을 제거 해야 합니다.  
  
 사용자가 창의 기본 프레임 창에 프레임 워크에서 [OnClose](../mfc/reference/cwnd-class.md#onclose) 처리기 호출 [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow)합니다. Windows 창을 소멸 될 때 호출 되는 마지막 멤버 함수는 [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), 약간의 정리를 수행 하는 호출 하는 [기본](../mfc/reference/cwnd-class.md#default) 멤버 Windows 정리 작업을 수행할 함수를 호출 하는 마지막으로 가상 멤버 함수 [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy)합니다. [CFrameWnd](../mfc/reference/cframewnd-class.md) 구현의 `PostNcDestroy` c + + 창 개체를 삭제 합니다. C + + 사용해 **삭제** 프레임 창에는 연산자입니다. 대신 `DestroyWindow`를 사용하세요.  
  
 주 창을 닫거나 응용 프로그램을 종료 합니다. 저장 되지 않은 문서 수정 되 면 프레임 워크 문서를 저장 해야 하는 경우 요청 하는 메시지 상자를 표시 하 고 필요한 경우 적절 한 문서는 저장 확인 합니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [문서 프레임 창 만들기](../mfc/creating-document-frame-windows.md)  
  
## <a name="see-also"></a>참고 항목  
 [프레임 창 사용](../mfc/using-frame-windows.md)

