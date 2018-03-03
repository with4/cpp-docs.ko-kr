---
title: "대화 상자 제거 | Microsoft Docs"
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
- dialog boxes [MFC], deleting
- destruction, dialog box
- dialog boxes [MFC], destroying
- dialog boxes [MFC], removing
- modeless dialog boxes [MFC], destroying
- MFC dialog boxes [MFC], destroying
- modal dialog boxes [MFC], destroying
ms.assetid: dabceee7-3639-4d85-bf34-73515441b3d0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0b1b6c94c4c7efe3bc3300d6c8c5c34fbe890fb4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="destroying-the-dialog-box"></a>대화 상자 제거
모달 대화 상자가 일반적으로 스택 프레임에 생성 되 고 이들을 만든는 함수가 종료 되어도 삭제 합니다. 대화 상자 개체의 소멸자가 범위를 벗어날 때 호출 됩니다.  
  
 모덜리스 대화 상자는 일반적으로 만든가 소유 하 고 부모 뷰 또는 프레임 창-응용 프로그램의 주 프레임 창이 나 문서 프레임 창. 기본 [OnClose](../mfc/reference/cwnd-class.md#onclose) 처리기 호출 [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow), 대화 상자 창 소멸 하 합니다. 대화 상자 또는 다른 특정 소유권 의미에 대 한 포인터 없이 독립적으로 stands 경우 재정의 해야 [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) c + + 대화 개체를 소멸 합니다. 재정의 해야 [OnCancel](../mfc/reference/cdialog-class.md#oncancel) 호출 `DestroyWindow` 에서 그 안에 있습니다. 파일이 없으면 대화 상자의 소유자는 더 이상 필요한 경우 c + + 개체를 제거 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)

