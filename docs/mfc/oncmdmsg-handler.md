---
title: "OnCmdMsg 처리기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OnCmdMsg
dev_langs: C++
helpviewer_keywords:
- messages, routing
- handlers [MFC]
- command routing [MFC], OnCmdMsg handler
- handlers, OnCmdMessage [MFC]
- OnCmdMessage method [MFC]
ms.assetid: 8df07024-506f-47e7-bba9-1c3bc5ad8ab6
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 173741ef73cd4bf6426787ef56e8334f504d7c0e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="oncmdmsg-handler"></a>OnCmdMsg 처리기
각 명령 대상 명령 라우팅을 달성 하기 위해 호출 된 `OnCmdMsg` 시퀀스에서 다음 명령 대상의 멤버 함수입니다. 명령 대상으로 사용 하 여 `OnCmdMsg` 명령을 처리할 수 있는지 여부를 확인 하 고 처리할 수 없는 경우 다른 명령 대상에 게 전달 합니다.  
  
 각 명령 대상 클래스를 재정의할 수 있습니다는 `OnCmdMsg` 멤버 함수입니다. 재정의 통해 특정 한 다음 대상에 각 클래스 경로 명령입니다. 프레임 창 예를 들어 항상 명령을 라우팅하고 현재 자식 창 또는 뷰를 테이블에 나와 있는 것 처럼 [표준 명령 경로](../mfc/command-routing.md)합니다.  
  
 기본 `CCmdTarget` 구현의 `OnCmdMsg` 명령 대상 클래스의 메시지 맵을 사용 하 여 각 명령 메시지 수신에 대 한 처리기 함수에 대 한 검색-마찬가지로 표준 메시지 검색 됩니다. 일치 하는 항목을 찾으면 해당 처리기를 호출 합니다. 에 설명 되어 메시지 맵을 검색 [어떻게의 프레임 워크 검색 메시지 맵](../mfc/how-the-framework-searches-message-maps.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크가 처리기를 호출하는 방법](../mfc/how-the-framework-calls-a-handler.md)

