---
title: "도움말 파일 (WinHelp) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: file types [C++], WinHelp files
ms.assetid: 4fdcbd66-66b0-4866-894a-fd7b4c2557e4
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a5698f7001512c5a4f8c45b5c787f35c9ce0ca6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="help-files-winhelp"></a>도움말 파일(WinHelp)
선택 하 여 응용 프로그램에 도움말 지원 WinHelp 형식의 추가할 때 다음 파일이 생성 됩니다는 **상황에 맞는 도움말** 확인란을 선택 하면 다음 **WinHelp 형식** 는 에서[고급 기능](../mfc/reference/advanced-features-mfc-application-wizard.md) MFC 응용 프로그램 마법사의 페이지입니다.  
  
|파일 이름|디렉터리 위치|솔루션 탐색기 위치|설명|  
|---------------|------------------------|--------------------------------|-----------------|  
|*Projname*.hpj|*Projname*\hlp|소스 파일|도움말 컴파일러 프로그램 또는 컨트롤의 도움말 파일을 만드는 데 사용 되는 도움말 프로젝트 파일.|  
|*Projname*.rtf|*Projname*\hlp|도움말 파일|.Hpj 파일을 사용자 지정 하는 방법 및을 편집할 수 있습니다 하는 서식 파일 항목을 포함 합니다.|  
|*Projname*.cnt|*Projname*\hlp|도움말 파일|에 대 한 구조를 제공는 **내용을** Windows 도움말에서 창.|  
|Makehelp.bat|*Projname*|소스 파일|프로젝트를 빌드하려면 도움말 프로젝트를 컴파일할 때 시스템에서 사용 합니다.|  
|Print.rtf|*Projname*\hlp|도움말 파일|프로젝트에 인쇄 지원을 (기본값)를 생성 합니다. 인쇄 명령 및 대화 상자에 설명합니다.|  
|*.bmp|*Projname*\hlp|리소스 파일|서로 다른 생성 된 도움말 파일 항목에 대 한 이미지를 포함 합니다.|  
  
 선택 하 여 WinHelp 지원을 MFC ActiveX 컨트롤 프로젝트에 추가할 수 있습니다 **도움말 파일 생성** 에 [응용 프로그램 설정](../mfc/reference/application-settings-mfc-activex-control-wizard.md) MFC ActiveX 컨트롤 마법사의 탭 합니다. MFC ActiveX 컨트롤에 대 한 도움말 지원을 추가 하면 다음 파일을 프로젝트에 추가 됩니다.  
  
|파일 이름|디렉터리 위치|솔루션 탐색기 위치|설명|  
|---------------|------------------------|--------------------------------|-----------------|  
|*Projname*.hpj|*Projname*\hlp|소스 파일|프로그램 또는 컨트롤의 도움말 파일을 만드는 도움말 컴파일러에서 사용 되는 프로젝트 파일입니다.|  
|*Projname*.rtf|*Projname*\hlp|프로젝트|.Hpj 파일을 사용자 지정 하는 방법 및을 편집할 수 있습니다 하는 서식 파일 항목을 포함 합니다.|  
|Makehelp.bat|*Projname*|소스 파일|프로젝트를 빌드하려면 도움말 프로젝트를 컴파일할 때 시스템에서 사용 합니다.|  
|위치|*Projname*|리소스 파일|표준 도움말 파일 항목에서 글머리 기호 목록을 나타내는 데 사용 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 프로젝트용 파일 형식](../ide/file-types-created-for-visual-cpp-projects.md)