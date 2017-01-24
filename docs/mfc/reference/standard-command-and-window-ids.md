---
title: "표준 명령 및 창 ID | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "표준 명령 및 창 ID"
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
caps.latest.revision: 13
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 표준 명령 및 창 ID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Microsoft Foundation Class Library는 표준 명령과 Afxres.h에서 IDs창을 정의합니다.  이 이러한은 메시지 처리기 함수에 매핑할 리소스 편집기 및 속성 창 내에서 가장 일반적으로 사용 됩니다.  모든 표준 명령에  **ID\_** 접두사가 있습니다.  예를 들어, 메뉴 편집기를 사용 하면 일반적으로 파일 열기 메뉴 항목에 연결한 표준  `ID_FILE_OPEN`  명령 id입니다.  
  
 대부분의 표준 명령에 대 한 응용 프로그램 코드 필요가 없습니다 명령 ID 참조 프레임 워크 자체의 기본 프레임 워크 클래스에 메시지 맵을 통해 명령을 처리 하기 때문에 \(`CWinThread`,  `CWinApp` ,  `CView` ,  **CDocument**등\).  
  
 표준 명령 Id 뿐만 아니라 다른 표준 Id 숫자 접두사가 있는 **AFX\_ID**에 정의되어 있습니다.  이 Id는 표준 창 Id \(접두사  **AFX\_IDW\_**\), Id 문자열 \(접두사  **AFX\_IDS\_**\), 및 몇 가지 다른 종류입니다.  
  
 로 시작 하는 Id는  **AFX\_ID** 접두사는 프로그래머는 거의 사용 되지 않지만 참조 프레임 워크 기능을 재정의 하는 경우이 Id를 참조 해야 할 수도 있습니다**AFX\_ID**.  
  
 이 참조 Id 개별적으로 설명 하지 않습니다.  자세한 내용은 기술 노트에서 찾을 수 있습니다. [20](../../mfc/tn020-id-naming-and-numbering-conventions.md),  [21](../../mfc/tn021-command-and-message-routing.md), 및  [22](../../mfc/tn022-standard-commands-implementation.md).  
  
> [!NOTE]
>  헤더 파일 Afxres.h가 Afxwin.h에 직접 포함 되어 있습니다.  명시적으로 응용 프로그램의 리소스 스크립트 \(.rc\) 파일에 다음 문을 포함 해야 합니다.  
  
 [!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/CPP/standard-command-and-window-ids_1.h)]  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)