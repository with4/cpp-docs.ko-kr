---
title: "다른 언어에 대 한 마법사 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.EastAsianLanguages
dev_langs:
- C++
helpviewer_keywords:
- wizards [C++], language support
- language support for MFC projects
- projects [C++], language support
ms.assetid: b653c673-0687-455c-885f-15d7e2f4149d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ef95c252621aa7f725098dfcd08c7b5b3620826
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="wizard-support-for-other-languages"></a>다른 언어에 대한 마법사 지원
Visual Studio를 설치할 때 설치 프로그램은 시스템에 있는 로캘을 검색 하 고 적절 한 언어 서식 파일 또는 해당 로캘에 대 한 템플릿을 설치 합니다. 예를 들어 서 부 유럽 로캘의 영어, 프랑스어, 이탈리아어, 스페인어 및 독일어가 설치 됩니다. 이 언어에 표시 된 **리소스 언어** 목록에서 [응용 프로그램 종류](../mfc/reference/application-type-mfc-application-wizard.md) MFC 응용 프로그램 마법사의 페이지입니다.  
  
## <a name="language-templates"></a>언어 서식 파일  
 모든 서식 파일은 서식 파일은 ANSI 인코딩을 기반으로 하 고 모든 시스템에서 모든 리소스를 편집할 수 때문에 모든 시스템에 설치 됩니다. 예를 들어 기본적으로 일본어 프랑스 시스템 리소스를 편집할 수 없습니다.  
  
 Windows 2000 또는 그 이상를 사용 하는 다른 언어에서 MFC 응용 프로그램을 만들려는 경우 다음에서 복사 해야 템플릿 디렉터리의 해당 언어에 대 한 Visual Studio 설치 프로그램 미디어 (디스크 1) 시스템에 있습니다.  
  
> [!NOTE]
>  만든된 프로젝트를 편집 하려면 선택한 언어에 대 한 적절 한 로캘로 시스템 로캘을 설정 해야 합니다.  
  
 템플릿은 다음 표에 나열 된 각 할당 \Microsoft Visual Studio.NET 2003\Vc7\VCWizards\mfcappwiz\templates\ 디렉터리에 폴더가 생성 됩니다. 원하는 언어 서식 파일에 액세스 하려면 컴퓨터에 \mfcappwiz\templates\ 디렉터리에 적절 한 폴더를 복사 합니다. 폴더를 복사 되 면 언어에 표시 됩니다는 **리소스 언어** 목록에 **응용 프로그램 종류** MFC 응용 프로그램 마법사의 페이지입니다.  
  
### <a name="language-templates-provided-in-visual-studio-net"></a>Visual Studio.NET에서에서 제공 하는 언어 템플릿  
  
|언어|템플릿|  
|--------------|--------------|  
|옵션 대신,|1028|  
|및|2052|  
|영어|1033|  
|프랑스어|1036|  
|독일어|1031|  
|이탈리아어|1040|  
|일본어|1041|  
|한국어|1042|  
|스페인어|3082|  
  
## <a name="format-of-visual-c-wizard-generated-files"></a>Visual c + + 마법사에서 생성 된 파일의 형식  
 설치 된 언어 버전의 Visual Studio는 시스템 로캘이 일치 하지 않는 경우 Visual c + + 마법사 유니코드에 프로젝트를 생성 합니다. 예를 들어 일본어 버전의 Visual Studio 국가별 설정이 일본어 이외의 언어로 설정 된 컴퓨터에 설치는 다음 Visual c + + 마법사에서 생성 유니코드 파일의 구성 된 프로젝트 합니다. 이 Windows (MUI) 팩이 여러 가지의 언어를 설정 하는 컴퓨터에서 일반적입니다.  
  
 시스템 로캘이 언어 버전의 Visual Studio와 동일 하 게 되도록 설정 하는 시스템에서 다르게이 동작 합니다. 이 경우 프로젝트 파일 시스템 코드 페이지에 ANSI에서 생성 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 프로젝트용 파일 형식](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Visual C++ 프로젝트 만들기 및 관리](../ide/creating-and-managing-visual-cpp-projects.md)