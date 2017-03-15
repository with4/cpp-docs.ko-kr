---
title: "도움말 파일(WinHelp) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "파일 형식[C++], WinHelp 파일"
ms.assetid: 4fdcbd66-66b0-4866-894a-fd7b4c2557e4
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 도움말 파일(WinHelp)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음은 MFC 응용 프로그램 마법사의 [고급 기능](../mfc/reference/advanced-features-mfc-application-wizard.md) 페이지에서 **상황에 맞는 도움말** 확인란을 선택한 다음 **WinHelp 형식**을 선택하여 WinHelp 형식의 도움말 지원을 응용 프로그램에 추가할 때 만들어지는 파일들입니다.  
  
|파일 이름|디렉터리 위치|솔루션 탐색기 위치|설명|  
|-----------|-------------|----------------|--------|  
|*Projname*.hpj|*Projname*\\hlp|소스 파일|도움말 컴파일러에서 프로그램 또는 컨트롤의 도움말 파일을 만드는 데 사용하는 도움말 프로젝트 파일|  
|*Projname*.rtf|*Projname*\\hlp|도움말 파일|편집할 수 있는 템플릿 항목과 .hpj 파일을 사용자 지정하는 방법에 대한 정보가 들어 있습니다.|  
|*Projname*.cnt|*Projname*\\hlp|도움말 파일|Windows 도움말 **목차** 창의 구조를 제공합니다.|  
|Makehelp.bat|*Projname*|소스 파일|프로젝트를 컴파일할 때 도움말 프로젝트를 빌드하는 데 사용됩니다.|  
|Print.rtf|*Projname*\\hlp|도움말 파일|프로젝트에 인쇄 지원이 포함된 경우\(기본값\) 만들어집니다.  인쇄 명령 및 대화 상자를 설명합니다.|  
|\*.bmp|*Projname*\\hlp|리소스 파일|생성된 여러 도움말 파일 항목에 대한 이미지가 들어 있습니다.|  
  
 MFC ActiveX 컨트롤 마법사의 [응용 프로그램 설정](../mfc/reference/application-settings-mfc-activex-control-wizard.md) 탭에서 **도움말 파일 생성**을 선택하여 MFC ActiveX 컨트롤 프로젝트에 WinHelp 지원을 추가할 수 있습니다.  다음 파일들은 MFC ActiveX 컨트롤에 도움말 지원을 추가할 때 프로젝트에 추가됩니다.  
  
|파일 이름|디렉터리 위치|솔루션 탐색기 위치|설명|  
|-----------|-------------|----------------|--------|  
|*Projname*.hpj|*Projname*\\hlp|소스 파일|도움말 컴파일러에서 프로그램 또는 컨트롤의 도움말 파일을 만드는 데 사용하는 프로젝트 파일|  
|*Projname*.rtf|*Projname*\\hlp|프로젝트|편집할 수 있는 템플릿 항목과 .hpj 파일을 사용자 지정하는 방법에 대한 정보가 들어 있습니다.|  
|Makehelp.bat|*Projname*|소스 파일|프로젝트를 컴파일할 때 도움말 프로젝트를 빌드하는 데 사용됩니다.|  
|Bullet.bmp|*Projname*|리소스 파일|표준 도움말 파일 항목에서 글머리 기호 목록을 나타내는 데 사용됩니다.|  
  
## 참고 항목  
 [Visual C\+\+ 프로젝트용으로 만들어지는 파일 형식](../ide/file-types-created-for-visual-cpp-projects.md)