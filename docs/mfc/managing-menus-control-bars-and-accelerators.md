---
title: 메뉴, 컨트롤 막대 및 액셀러레이터 관리 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MDI [MFC], frame windows
- control bars [MFC], updating in frame windows
- menus [MFC], updating as context changes
- user interface objects [MFC], updating
- accelerator tables [MFC]
- sharing menus [MFC]
- updating user-interface objects [MFC]
- frame windows [MFC], updating
- status bars [MFC], updating
ms.assetid: 97ca1997-06df-4373-b023-4f7ecd81047b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e19cda1869938a854ff03ea83cdda747e8120a0
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929532"
---
# <a name="managing-menus-control-bars-and-accelerators"></a>메뉴, 컨트롤 막대 및 액셀러레이터 관리
프레임 창 메뉴, 도구 모음 단추, 상태 표시줄 및 액셀러레이터를 포함 하 여 업데이트 사용자 인터페이스 개체를 관리 합니다. 또한 공유 MDI 응용 프로그램의 메뉴 모음을 관리 합니다.  
  
## <a name="managing-menus"></a>메뉴 관리  
 프레임 창 사용자 인터페이스 항목에 설명 된 ON_UPDATE_COMMAND_UI 메커니즘을 사용 하 여 업데이트에 참여 [사용자 인터페이스 개체 업데이트 하는 방법을](../mfc/how-to-update-user-interface-objects.md)합니다. 유휴 루프 중 단추 도구 모음 및 다른 컨트롤 막대에 업데이트 됩니다. 메뉴 모음에서 드롭다운 메뉴에 메뉴 항목 메뉴가 드롭다운 하기 바로 전에 업데이트 됩니다.  
  
 MDI 응용 프로그램에 대 한 MDI 프레임 창 메뉴 모음 및 캡션을 관리합니다. MDI 프레임 창은 활성 MDI 자식 창이 없는지 경우 메뉴 모음으로 사용 되는 하나의 기본 메뉴를 소유 합니다. 활성 자식 인 경우 MDI 프레임 창 메뉴 모음 활성 MDI 자식 창에 대 한 메뉴 키를 가져옵니다. MDI 응용 프로그램 문서, 워크시트 및 차트 같은 여러 문서 유형을 지 원하는 경우 각 유형에 고유한 메뉴가 메뉴 모음에 배치 하 고 주 프레임 창 캡션의 변경 합니다.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) MDI 응용 프로그램에 대 한 표시 되는 창 메뉴 표준 명령에 대 한 기본 구현을 제공 합니다. 특히, 새 프레임 창 개체와 현재 문서에서 보기를 만들려면 (ID_WINDOW_NEW) 새 창 명령을 구현 됩니다. 고급 사용자 지정 해야 하는 경우에 이러한 구현을 재정의 해야 합니다.  
  
 동일한 문서 종류의 MDI 자식 창이 여러 메뉴 리소스를 공유 합니다. 여러 MDI 자식 창을 동일한 문서 서식 파일에서 생성 되 면 모두 사용할 수 있습니다 Windows의 시스템 리소스가 절약 같은 메뉴 리소스입니다.  
  
## <a name="managing-the-status-bar"></a>상태 표시줄 관리  
 프레임 창에서도 클라이언트 영역 내에서 상태 표시줄을 배치 하 고 상태 관리 표시줄의 표시기입니다. 프레임 창 및 필요에 따라 메시지 영역 상태 표시줄에 업데이트 지우고에 설명 된 대로 프롬프트 문자열을 사용자가 메뉴 항목 또는 도구 모음 단추를 선택 하는 대로 표시 [상태 표시줄에 명령 정보를 표시 하는 방법을](../mfc/how-to-display-command-information-in-the-status-bar.md)합니다.  
  
## <a name="managing-accelerators"></a>액셀러레이터 키 관리  
 각 프레임 창에는 액셀러레이터 번역을 자동으로 키보드에 있는 선택적 액셀러레이터 키 테이블 유지 관리 합니다. 이 메커니즘을 사용 하면 쉽게 메뉴 명령을 호출 하는 액셀러레이터 키 (바로 가기 키)를 정의할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [프레임 창 사용](../mfc/using-frame-windows.md)

