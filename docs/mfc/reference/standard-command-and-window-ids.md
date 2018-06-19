---
title: 표준 명령 및 창 Id | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 72b50108a9b880961f0dd8bcded1126a635fb9e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371652"
---
# <a name="standard-command-and-window-ids"></a>표준 명령 및 창 ID
Microsoft Foundation Class 라이브러리는 Afxres.h의 여러 표준 명령 및 창 ID를 정의합니다. 이러한 ID는 메시지를 처리기 함수에 매핑하기 위해 리소스 편집기 및 속성 창 내에서 일반적으로 사용됩니다. 모든 표준 명령는 **ID_** 접두사입니다. 예를 들어 메뉴 편집기를 사용 하면 일반적으로 파일 열기 메뉴 항목에 연결한 표준 `ID_FILE_OPEN` 명령 id입니다.  
  
 대부분의 표준 명령에 대 한 응용 프로그램 코드 하지 않아도 명령 ID를 참조 하는 프레임 워크 자체의 기본 프레임 워크 클래스에 대 한 메시지 맵을 통해 명령을 처리 하기 때문에 ( `CWinThread`, `CWinApp`, < c4 > `CView` , **CDocument**등).  
  
 표준 명령 Id 외에도 다른 여러 표준 id가 정의 되어 있는 접두사가의 **AFX_ID**합니다. 이러한 Id는 표준 창 Id (접두사 **AFX_IDW_**), 문자열 Id (접두사 **AFX_IDS_**), 및 기타 형식이 있습니다.  
  
 시작 하는 Id는 **AFX_ID** 접두사는 거의 사용 되지 않지만 참조 하는 프레임 워크 함수를 재정의 하는 경우 이러한 Id를 참조 해야 할 수는 **AFX_ID**s입니다.  
  
 ID는 이 참조 설명서에서 개별적으로 설명하지 않습니다. 자세한 내용은 기술 참고 사항에서 찾을 수 있습니다 [20](../../mfc/tn020-id-naming-and-numbering-conventions.md), [21](../../mfc/tn021-command-and-message-routing.md), 및 [22](../../mfc/tn022-standard-commands-implementation.md)합니다.  
  
> [!NOTE]
>  헤더 파일 Afxres.h는 Afxwin.h에 간접적으로 포함됩니다. 응용 프로그램의 리소스 스크립트(.rc) 파일에 다음 문을 명시적으로 포함해야 합니다.  
  
 [!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]  
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
