---
title: "도움말 파일 (HTML 도움말) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: file types [C++], HTML Help files
ms.assetid: d30a1b1b-318f-4a78-8b60-93da53a224a8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c96cd6ad904439f556f2baa51602353ea00c5ac7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="help-files-html-help"></a>도움말 파일(HTML 도움말)
다음 파일을 선택 하 여 응용 프로그램에 HTML 도움말에 대 한 형식의 도움말 지원 추가할 때 생성 됩니다는 **상황에 맞는 도움말** 확인란을 선택 하면 다음 **HTML 도움말 형식** 는 에서[고급 기능](../mfc/reference/advanced-features-mfc-application-wizard.md) MFC 응용 프로그램 마법사의 페이지입니다.  
  
|파일 이름|디렉터리 위치|솔루션 탐색기 위치|설명|  
|---------------|------------------------|--------------------------------|-----------------|  
|*Projname*.hhp|*Projname*\hlp|HTML 도움말 파일|도움말 프로젝트 파일입니다. .Chm 파일 또는.hxs 파일로 도움말 파일을 컴파일하는 데 필요한 데이터를 포함 합니다.|  
|*Projname*.hhk|*Projname*\hlp|HTML 도움말 파일|도움말 항목의 인덱스를 포함 합니다.|  
|*Projname*.hhc|*Projname*\hlp|HTML 도움말 파일|도움말 프로젝트의 내용입니다.|  
|Makehtmlhelp.bat|*Projname*|소스 파일|프로젝트를 빌드하려면 도움말 프로젝트를 컴파일할 때 시스템에서 사용 합니다.|  
|Afxcore.htm|*Projname*\hlp|HTML 도움말 항목|표준 MFC 명령과 화면 개체에 대 한 표준 도움말 항목이 포함 되어 있습니다. 이 파일에 사용자 지정 도움말 항목을 추가 합니다.|  
|Afxprint.htm|*Projname*\hlp|HTML 도움말 항목|인쇄 명령에 대 한 도움말 항목이 포함 되어 있습니다.|  
|*.jpg; \*.gif|*Projname*\hlp\Images|리소스 파일|서로 다른 생성 된 도움말 파일 항목에 대 한 이미지를 포함 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 프로젝트용 파일 형식](../ide/file-types-created-for-visual-cpp-projects.md)