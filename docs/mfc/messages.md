---
title: "메시지 | Microsoft Docs"
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
- messages, MFC
- messages [MFC]
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d03eed129fd5a2a7c73f7c7948cb766813f63c34
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="messages"></a>메시지
메시지 루프에는 **실행** 클래스의 멤버 함수 `CWinApp` 대기 중인 다양 한 이벤트에 의해 생성 된 메시지를 검색 합니다. 예를 들어 사용자가 마우스를 클릭 하면 보내는데 여러 마우스 관련 메시지와 같은 `WM_LBUTTONDOWN` 마우스 왼쪽된 단추를 누를 때 및 `WM_LBUTTONUP` 마우스 왼쪽된 단추를 놓았음을 합니다. 응용 프로그램 메시지 루프의 프레임 워크의 구현 적절 한 창에 메시지를 디스패치합니다.  
  
 메시지의 중요 한 범주에 설명 된 [메시지 범주](../mfc/message-categories.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크의 메시지 및 명령](../mfc/messages-and-commands-in-the-framework.md)

