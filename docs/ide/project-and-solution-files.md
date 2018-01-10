---
title: "프로젝트 및 솔루션 파일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.files.projectandsolution
dev_langs: C++
helpviewer_keywords:
- project files [C++]
- file types [C++], makefiles
- .sdf, browsing database file
- Makefile projects
- browsing database file, .sdf
- file types [C++], project files
ms.assetid: 5823b954-36cf-42d3-8fd5-25bab3ef63d9
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 03797d266dc0f3104d6153b9d946d06ac963fafc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="project-and-solution-files"></a>프로젝트 및 솔루션 파일
다음 파일은 Visual Studio에서 프로젝트를 만들 때 생성됩니다. 이러한 파일은 솔루션에서 프로젝트 파일을 관리하는 데 사용됩니다.  
  
|파일 이름|디렉터리 위치|솔루션 탐색기 위치|설명|  
|--------------|------------------------|--------------------------------|-----------------|  
|*Solname*.sln|*Projname*|솔루션 탐색기에 표시 안 됨|*솔루션* 파일입니다. 하나 또는 여러 프로젝트의 모든 요소를 한 솔루션으로 구성합니다.|  
|*Projname*.suo|*Projname*|솔루션 탐색기에 표시 안 됨|*솔루션 옵션* 파일입니다. 솔루션에 있는 프로젝트나 파일을 열 때마다 원하는 모양과 동작을 갖도록 솔루션에 대한 사용자 지정을 저장합니다.|  
|*Projname*.vcxproj|*Projname*|솔루션 탐색기에 표시 안 됨|*프로젝트* 파일입니다. 각 프로젝트에 대한 정보를 저장합니다. (이전 버전에서는이 파일 이름이 *Projname*.vcproj 또는 *Projname*.dsp.) 예를 보려면 Visual c + + 프로젝트 파일 참조 [프로젝트 파일](../ide/project-files.md)합니다.|  
|*Projname*.vcxitems|*Projname*|솔루션 탐색기에 표시 안 됨|*공유 항목 프로젝트* 파일입니다. 이 프로젝트는 빌드되지 않았습니다.  대신 다른 c + + 프로젝트에서 프로젝트를 참조할 수 있습니다 하 고 해당 파일에서 참조 하는 프로젝트의 빌드 프로세스의 일부가 됩니다. 플랫폼 간 c + + 프로젝트와 함께 공통 코드를 공유 데 될 수 있습니다.|
|*Projname*.sdf|*Projname*|솔루션 탐색기에 표시 안 됨|*검색 데이터베이스* 파일입니다. 와 같은 찾아보기 및 탐색 기능을 지원 **정의 이동**, **모든 참조 찾기**, 및 **클래스 뷰**합니다. 헤더 파일을 구문 분석하여 생성됩니다.|  
|*Projname 합니다.* vcxproj.filters|*Projname*|솔루션 탐색기에 표시 안 됨|*필터* 파일입니다. 솔루션에 추가된 파일을 저장할 위치를 지정합니다. .H 파일은 저장 하는 예를 들어는 **헤더 파일** 노드.|  
|*Projname 합니다.* vcxproj.user|*Projname*|솔루션 탐색기에 표시 안 됨|*마이그레이션 사용자* 파일입니다. 프로젝트를 Visual Studio 2008에서 마이그레이션한 후 이 파일은 모든 .vsprops 파일에서 변환된 정보가 들어 있습니다.|  
|*Projname*.idl|*Projname*|소스|(프로젝트에 따라 다름) 컨트롤 형식 라이브러리의 IDL(인터페이스 설명 언어) 소스 코드가 포함되어 있습니다. 이 파일은 Visual C++에 의해 형식 라이브러리를 생성하는 데 사용됩니다. 생성된 라이브러리는 다른 자동화 클라이언트에 컨트롤 인터페이스를 제공합니다. 자세한 내용은 참조 [인터페이스 정의 (IDL) 파일](http://msdn.microsoft.com/library/windows/desktop/aa378712) Windows sdk에서입니다.|  
|ReadMe.txt|*Projname*|프로젝트|*읽어보기* 파일입니다. 응용 프로그램 마법사에서 생성되며 프로젝트의 파일에 대해 설명합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 프로젝트용 파일 형식](../ide/file-types-created-for-visual-cpp-projects.md)