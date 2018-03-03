---
title: "클래스에 Windows 메시지 매핑 | Microsoft Docs"
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
- MFC dialog boxes [MFC], Windows messages
- message maps [MFC], in dialog class
- Windows messages [MFC], mapping in dialog classes
- messages to dialog class [MFC]
- mappings [MFC], messages to dialog class [MFC]
- message maps [MFC], mapping Windows messages to classes
- messages to dialog class [MFC], mapping
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4701b0ae9f71099febb1a239cea6285fb0a7b229
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mapping-windows-messages-to-your-class"></a>클래스에 Windows 메시지 매핑
Windows 메시지를 처리 하 여 대화 상자를 필요한 경우 적절 한 처리기 함수를 재정의 합니다. 이렇게 하려면 속성 창을 사용 하 여 [메시지 매핑](../mfc/reference/mapping-messages-to-functions.md) 대화 상자 클래스에 있습니다. 각 메시지에 대 한 메시지 맵 항목을 기록 하 고 메시지 처리기 멤버 함수는 클래스에 추가 합니다. Visual c + + 소스 코드 편집기를 사용 하 여 메시지 처리기에 코드를 작성 합니다.  
  
 멤버 함수를 재정의할 수도 있습니다 [CDialog](../mfc/reference/cdialog-class.md) 와 해당 기본 클래스, 특히 [CWnd](../mfc/reference/cwnd-class.md)합니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [메시지 처리 및 매핑](../mfc/message-handling-and-mapping.md)  
  
-   [일반적으로 재정의 되는 멤버 함수](../mfc/commonly-overridden-member-functions.md)  
  
-   [일반적으로 추가 되는 멤버 함수](../mfc/commonly-added-member-functions.md)  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자](../mfc/dialog-boxes.md)   
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)

