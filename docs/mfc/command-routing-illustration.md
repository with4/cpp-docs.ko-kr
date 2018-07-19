---
title: 명령 라우팅 설명 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, command routing
- command handling [MFC], routing commands
- command routing [MFC], OnCmdMsg handler
ms.assetid: 4b7b4741-565f-4878-b076-fd85c670f87f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a12a5cd19177761dfbf484c64f528d8def194ca5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341138"
---
# <a name="command-routing-illustration"></a>명령 라우팅 설명
예를 들어 MDI 응용 프로그램의 편집 메뉴에서 메뉴 항목 모두 지우기 명령 메시지를 것이 좋습니다. 이 명령의 처리기 함수 발생 하는 응용 프로그램의 문서 클래스의 멤버 함수로 가정 합니다. 메뉴 항목을 선택한 후 해당 명령에 해당 처리기 도달 하는 방법을 다음과 같습니다.  
  
1.  주 프레임 창 명령 메시지를 먼저 받습니다.  
  
2.  주 MDI 프레임 창의 명령을 처리 하는 현재 활성 MDI 자식 창을 제공 합니다.  
  
3.  MDI 자식 프레임 창은 표준 라우팅을 하면 해당 보기에서 명령에 자신의 메시지 맵을 확인 하기 전에 있습니다.  
  
4.  보기 먼저 자신의 메시지 맵을 확인 하 고 처리기를 찾는 옆에 라우팅하여 해당 명령을 관련된 문서.  
  
5.  처리기는 문서를 자신의 메시지 맵을 확인 합니다. 이 문서 멤버 함수를 호출 하 고 라우팅이 중단 합니다.  
  
 문서에는 처리기 없는 경우 해당 문서 템플릿에 명령을 라우팅합니다 다음 것입니다. 다음 명령은 뷰 및 프레임 창 돌아갑니다. 마지막으로, 프레임 창에는 자신의 메시지 맵을 확인 합니다. 이 명령은 주 MDI 프레임 창으로 다시 한 다음 응용 프로그램 개체에 보내지는 확인에 실패 한 경우-최종 대상을 처리 되지 않은 명령입니다.  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크가 처리기를 호출하는 방법](../mfc/how-the-framework-calls-a-handler.md)

