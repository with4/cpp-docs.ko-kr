---
title: 멤버 함수 실행 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- WinMain method [MFC]
ms.assetid: 24ab7597-2354-495b-9a20-2c8ccc7385b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be1d7d90b4c13a23e2e3456e7371abbae61be4e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379898"
---
# <a name="run-member-function"></a>Run 멤버 함수
프레임 워크 응용에서 대부분의 시간에는 [실행](../mfc/reference/cwinapp-class.md#run) 클래스의 멤버 함수 [CWinApp](../mfc/reference/cwinapp-class.md)합니다. 초기화 된 후 `WinMain` 호출 **실행** 메시지 루프를 처리할 수 있습니다.  
  
 **실행** 순환 메시지 루프를 사용할 수 있는 메시지에 대 한 메시지 큐를 확인 합니다. 메시지를 사용할 수 있는 경우 **실행** 동작에 대 한 디스패치합니다. 사용할 수 있는 메시지가 없을 경우는 더욱 그렇습니다, **실행** 호출 `OnIdle` 수행 유휴 시간 처리 프레임 워크에서 해야 하는 작업을 수행할 합니다. 가 없을 경우 메시지가 및 없는 유휴 처리 작업을 수행 하는 응용 프로그램 일이 발생 될 때까지 대기 합니다. 응용 프로그램이 종료 되 면 **실행** 호출 `ExitInstance`합니다. 이 그림에서 [OnIdle 멤버 함수](../mfc/onidle-member-function.md) 메시지 루프에는 일련의 동작을 보여 줍니다.  
  
 메시지 디스패치 메시지의 종류에 따라 달라 집니다. 자세한 내용은 참조 [프레임 워크의 메시지 및 명령](../mfc/messages-and-commands-in-the-framework.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CWinApp: 응용 프로그램 클래스](../mfc/cwinapp-the-application-class.md)
