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
ms.openlocfilehash: 5d7544d92d55ec4a1f6d15f3c1d4358970bf2deb
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928343"
---
# <a name="messages"></a>메시지
메시지 루프에는 `Run` 클래스의 멤버 함수 `CWinApp` 대기 중인 다양 한 이벤트에 의해 생성 된 메시지를 검색 합니다. 예를 들어 사용자가 마우스를 클릭 하면 Windows에서 마우스 왼쪽된 단추를 누를 때 WM_LBUTTONDOWN 및 WM_LBUTTONUP 마우스 왼쪽된 단추를 놓을 때와 같은 여러 마우스 관련 메시지에 보냅니다. 응용 프로그램 메시지 루프의 프레임 워크의 구현 적절 한 창에 메시지를 디스패치합니다.  
  
 메시지의 중요 한 범주에 설명 된 [메시지 범주](../mfc/message-categories.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크의 메시지 및 명령](../mfc/messages-and-commands-in-the-framework.md)

