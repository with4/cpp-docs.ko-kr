---
title: "비 명령 메시지 해당 처리기에 도달 하는 방법 | Microsoft Docs"
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
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 33d0d65c9916cfc571ecfd623138938c0c883ba5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>명령이 아닌 메시지가 해당 처리기에 도달하는 방법
명령, 달리 표준 Windows 메시지 체인 of 명령 대상을 통해 라우팅되지 않게 하지만 일반적으로 Windows에서 메시지를 보내는 경우 창으로 처리 됩니다. 창을 주 프레임 창, MDI 자식 창, 표준 컨트롤, 대화 상자, 뷰 또는 일부 다른 자식 창의 종류가 수 있습니다.  
  
 Window 개체에 연결 된 Windows 창을 각 실행 시 (에서 직접 또는 간접적으로 파생 `CWnd`) 자체 연결 된 메시지 맵 및 처리기 함수가 있는 합니다. 프레임 워크가 메시지 맵을 사용 하 여-는 명령-들어오는 메시지 처리기에 매핑됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크가 처리기를 호출하는 방법](../mfc/how-the-framework-calls-a-handler.md)

