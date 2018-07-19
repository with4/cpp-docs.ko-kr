---
title: 프레임 워크 코드를 호출 하는 방법 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- control flow [MFC], MFC framework and your code
- events [MFC], command routing in MFC
- command routing [MFC], framework
- command handling [MFC], calling handlers and code in MFC
- events [MFC], event-driven programming
- MFC, calling code from
- MFC, calling code
- application-specific events [MFC]
- command routing [MFC], MFC
ms.assetid: 39e68189-a580-40d0-9e35-bf5cd24a8ecf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f746ce3c3d658ab1dccc098939410b52d91b1188
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348181"
---
# <a name="how-the-framework-calls-your-code"></a>프레임워크가 코드를 호출하는 방법
것 MFC 프레임 워크에서 코드와 소스 코드 사이의 관계를 이해 하는 데 중요 합니다. 응용 프로그램을 실행 하는 경우 대부분의 제어 흐름의 프레임 워크의 코드에 상주 합니다. 프레임 워크는 메시지 루프를 메시지에서 Windows 사용자 명령을 선택 하 고 편집 보기에서 데이터를 관리 합니다. 프레임 워크는 자체적으로 처리할 수 있는 이벤트 코드에 대해 전혀 사용 하지 마세요. 예를 들어 프레임 워크 창을 닫고 하는 방법과 사용자 명령에 대 한 응답으로 응용 프로그램을 종료 하는 방법을 알고 있습니다. 이러한 작업을 처리 프레임 워크를 사용 하 여 메시지 처리기 및 가상 함수를 c + + 에서도 이러한 이벤트에 응답 하는 기회를 제공 합니다. 그러나; 컨트롤에 없는 코드는 프레임 워크가입니다.  
  
 응용 프로그램 관련 이벤트에 대 한 코드를 호출 하는 프레임 워크입니다. 예를 들어 메뉴 명령 선택 하면 프레임 워크 라우팅하여 해당 명령을 c + + 개체의 시퀀스를 따라: 현재 뷰 및 프레임 창, 보기, 문서의 문서 서식 파일을 응용 프로그램 개체와 연결 된 문서입니다. 이러한 개체 중 하나는 명령을 처리할 수 있는 경우이 작업을 수행, 적절 한 메시지 처리기 함수를 호출 합니다. 지정한 명령에 대 한 호출 코드 일 수도 있고 프레임 워크의 수도 있습니다.  
  
 이 정렬은 Windows 용 기존의 프로그래밍 또는 이벤트 구동 프로그래밍 프로그래머에 어느 정도 알고 있습니다.  
  
 관련된 항목을 기능 프레임 워크 않습니다을 초기화 하 고 응용 프로그램을 실행 하 고 다음 정리 종료를 설명 합니다. 작성 하는 코드 채택 된 위치를 이해할 수 있습니다.  
  
 자세한 내용은 참조 [클래스 CWinApp: 응용 프로그램 클래스](../mfc/cwinapp-the-application-class.md) 및 [문서 템플릿 및 문서/뷰 만들기 프로세스](../mfc/document-templates-and-the-document-view-creation-process.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크를 기반으로 구축](../mfc/building-on-the-framework.md)

