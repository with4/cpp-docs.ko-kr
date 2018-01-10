---
title: "표준 명령 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- File menu
- identifiers [MFC], command IDs
- command IDs, standard commands
- OLE commands
- commands [MFC], standard
- standard command IDs
- Window menu commands
- standard commands
- View menu commands
- Edit menu standard commands
- Help [MFC], menus
- programmer-defined IDs [MFC]
ms.assetid: 88cf3ab4-79b3-4ac6-9365-8ac561036fbf
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bbdb763b2d7da04267a195e5d534da9528f2b74d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="standard-commands"></a>표준 명령
프레임 워크는 많은 표준 명령 메시지를 정의합니다. 이러한 명령에 대 한 Id는 일반적으로 다음 양식을 사용:  
  
 **ID_** *소스*_*항목*  
  
 여기서 *소스* 는 일반적으로 메뉴 이름 및 *항목* 는 메뉴 항목입니다. 예를 들어 파일 메뉴에서 새 명령에 대 한 명령 ID가 `ID_FILE_NEW`합니다. 표준 명령 Id의 설명서에서 굵게에서 표시 됩니다. 프로그래머 정의 Id는 주변 텍스트와에서는 다른 글꼴에 표시 됩니다.  
  
 다음은 지원 되는 가장 중요 한 명령을 중 일부 목록입니다.  
  
 *파일 메뉴 명령*  
 새로 만들기, 열기, 닫기, 다른 이름으로 저장, 페이지 설정, 인쇄 설정, 인쇄, 인쇄 미리 보기, 종료 및 가장 최근에 사용한 파일 저장 합니다.  
  
 *편집 메뉴 명령*  
 지우기, 지우기 All, 복사, 잘라내기, 찾기, 붙여넣기, 반복, Replace, 모두 선택, 실행 취소 및 다시 실행 합니다.  
  
 *보기 메뉴 명령*  
 도구 모음 및 상태 표시줄입니다.  
  
 *창 메뉴 명령*  
 새로 만들기, 정렬, 계단식 배열, 가로, 세로 바둑판식으로 배열 및 분할 합니다.  
  
 *도움말 메뉴 명령*  
 색인, 도움말을 사용 하 고 약 합니다.  
  
 *OLE 편집 메뉴 명령*  
 새 개체, 편집 링크, 연결 하 여 붙여넣기, 붙여넣기, 삽입 및 *typename* 개체 (동사 명령).  
  
 프레임 워크는 이러한 명령에 대 한 다양 한 수준의 지원 제공합니다. 일부 명령은 다른 사용자가 완전 한 구현으로 지원 됩니다 정의 된 명령 Id로만 지원 됩니다. 예를 들어 프레임 워크에서 새 문서 개체 만들기, 열기 대화 상자를 표시 하 고 열기 및 파일을 읽는 파일 메뉴에서 열기 명령의 구현 합니다. 반면, 구현 해야 편집 메뉴에서 명령, 직접과 같은 명령을 이후 **ID_EDIT_COPY** 복사할 데이터의 특성에 따라 달라 집니다.  
  
 지원 되는 명령에 대 한 자세한 내용 및 제공 되는 구현 수준에 대 한 참조 [Technical Note 22](../mfc/tn022-standard-commands-implementation.md)합니다. 표준 명령 AFXRES 파일에 정의 됩니다. 8.  
  
## <a name="see-also"></a>참고 항목  
 [사용자 인터페이스 개체 및 명령 ID](../mfc/user-interface-objects-and-command-ids.md)

