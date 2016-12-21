---
title: "도움말 파일(HTML 도움말) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "파일 형식[C++], HTML 도움말 파일"
ms.assetid: d30a1b1b-318f-4a78-8b60-93da53a224a8
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 도움말 파일(HTML 도움말)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 파일들은 MFC 응용 프로그램 마법사의 [고급 기능](../mfc/reference/advanced-features-mfc-application-wizard.md) 페이지에서 **상황에 맞는 도움말** 확인란을 선택한 다음 **HTML 도움말 형식**을 선택하여 HTML 도움말 형식의 도움말 지원을 응용 프로그램에 추가할 때 만들어집니다.  
  
|파일 이름|디렉터리 위치|솔루션 탐색기 위치|설명|  
|-----------|-------------|----------------|--------|  
|*Projname*.hhp|*Projname*\\hlp|HTML 도움말 파일|도움말 프로젝트 파일.  도움말 파일을 .hxs 파일 또는 .chm 파일로 컴파일하는 데 필요한 데이터가 들어 있습니다.|  
|*Projname*.hhk|*Projname*\\hlp|HTML 도움말 파일|도움말 항목의 색인이 들어 있습니다.|  
|*Projname*.hhc|*Projname*\\hlp|HTML 도움말 파일|도움말 프로젝트의 목차입니다.|  
|Makehtmlhelp.bat|*Projname*|소스 파일|프로젝트를 컴파일할 때 도움말 프로젝트를 빌드하는 데 사용됩니다.|  
|Afxcore.htm|*Projname*\\hlp|HTML 도움말 항목|표준 MFC 명령 및 화면 개체에 대한 표준 도움말 항목이 들어 있습니다.  이 파일에 사용자 지정 도움말 항목을 추가하십시오.|  
|Afxprint.htm|*Projname*\\hlp|HTML 도움말 항목|인쇄 명령에 대한 도움말 항목이 들어 있습니다.|  
|\*.jpg; \*.gif|*Projname*\\hlp\\Images|리소스 파일|생성된 여러 도움말 파일 항목에 대한 이미지가 들어 있습니다.|  
  
## 참고 항목  
 [Visual C\+\+ 프로젝트용으로 만들어지는 파일 형식](../ide/file-types-created-for-visual-cpp-projects.md)