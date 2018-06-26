---
title: '방법: 상태 표시줄에 명령 정보를 표시 합니다. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- prompts [MFC]
- displaying command status [MFC]
- status bars [MFC], message area
- status bars [MFC], displaying command information
ms.assetid: de895cbe-61ee-46bf-9787-76b247527d6d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 84f1a12dd9ca25ec19415cde42dc8ce12e515833
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930955"
---
# <a name="how-to-display-command-information-in-the-status-bar"></a>방법: 상태 표시줄에 명령 정보 표시
응용 프로그램의 기초를 만드는 응용 프로그램 마법사를 실행 하면 도구 모음 및 상태 표시줄을 지원할 수 있습니다. 응용 프로그램 마법사에서 하나의 옵션 모두 지원 합니다. 상태 표시줄에 있는 경우 메뉴 항목 위에 포인터를 이동할 때 응용 프로그램이 자동으로 유용한 피드백을 제공 합니다. 응용 프로그램 자동으로 프롬프트 문자열을 표시 상태 표시줄에 메뉴 항목이 강조 됩니다. 예를 들어, 사용자 이동 하면 포인터는 **잘라내기** 명령을 **편집** 메뉴 상태 표시줄에 "선택 영역을 잘라내어 클립보드에 저장 합니다." 상태 표시줄의 메시지 영역에 표시 될 수 있습니다. 프롬프트를 통해 사용자는 메뉴 항목의 목적을 이해 합니다. 사용자가 도구 모음 단추를 클릭 하는 경우에 작동 합니다.  
  
 프로그램에 추가 하는 메뉴 항목에 대 한 프롬프트 문자열을 정의 하 여이 상태 표시줄 도움말에 추가할 수 있습니다. 이 작업을 수행 하려면 메뉴 편집기에서 메뉴 항목의 속성을 편집 하는 경우 프롬프트 문자열을 제공 합니다. 정의 하는 문자열에서 응용 프로그램 리소스 파일에 저장 됩니다. 설명 명령과 동일한 Id를 갖게 됩니다.  
  
 기본적으로 응용 프로그램 마법사 추가 **AFX_IDS_IDLEMESSAGE**, 프로그램이 새 메시지에 대 한 대기 중인 경우 표시 되는 표준 "준비" 메시지에 대 한 ID입니다. 메시지가 "도움말을 보려면 F1 키를 누릅니다."으로 변경 된 응용 프로그램 마법사에서 상황에 맞는 도움말 옵션을 지정 하는 경우  
  
## <a name="see-also"></a>참고 항목  
 [메시지 처리 및 매핑](../mfc/message-handling-and-mapping.md)

