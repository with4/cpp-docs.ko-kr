---
title: 메시지 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages, MFC
- messages [MFC]
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: abd49410f9982788e9403f0cb83ca8656473417d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344106"
---
# <a name="messages"></a>메시지
메시지 루프에는 **실행** 클래스의 멤버 함수 `CWinApp` 대기 중인 다양 한 이벤트에 의해 생성 된 메시지를 검색 합니다. 예를 들어 사용자가 마우스를 클릭 하면 보내는데 여러 마우스 관련 메시지와 같은 `WM_LBUTTONDOWN` 마우스 왼쪽된 단추를 누를 때 및 `WM_LBUTTONUP` 마우스 왼쪽된 단추를 놓았음을 합니다. 응용 프로그램 메시지 루프의 프레임 워크의 구현 적절 한 창에 메시지를 디스패치합니다.  
  
 메시지의 중요 한 범주에 설명 된 [메시지 범주](../mfc/message-categories.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크의 메시지 및 명령](../mfc/messages-and-commands-in-the-framework.md)

