---
title: 다른 언어에 대한 마법사 지원 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.EastAsianLanguages
dev_langs:
- C++
helpviewer_keywords:
- wizards [C++], language support
- language support for MFC projects
- projects [C++], language support
ms.assetid: b653c673-0687-455c-885f-15d7e2f4149d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75aafd7177c3799c17b75419fd5ab9f54af91d35
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33332444"
---
# <a name="wizard-support-for-other-languages"></a>다른 언어에 대한 마법사 지원
Visual Studio를 설치할 때 설치 응용 프로그램은 시스템에 나열된 로캘을 검색하고 해당 로캘에 적합한 언어 템플릿을 설치합니다. 예를 들어 유럽 서부 로캘의 경우 설치 프로그램은 영어, 프랑스어, 이탈리아어, 스페인어 및 독일어를 설치합니다. 이러한 언어는 MFC 응용 프로그램 마법사의 [응용 프로그램 종류](../mfc/reference/application-type-mfc-application-wizard.md) 페이지에 있는 **리소스 언어** 목록에 나타납니다.  
  
## <a name="language-templates"></a>언어 템플릿  
 템플릿은 ANSI 인코딩 기반이며 모든 시스템에서 모든 리소스를 편집할 수 있는 것은 아니므로, 모든 시스템에 모든 템플릿이 설치되어 있는 것은 아닙니다. 예를 들어, 기본적으로 프랑스어 시스템에서는 일본어 리소스를 편집할 수 없습니다.  
  
 Windows 2000 이상을 사용하고 있고 다른 언어로 MFC 응용 프로그램을 만들려는 경우, Visual Studio 설치 프로그램 미디어(디스크 1)에서 해당 언어에 대한 템플릿 디렉터리를 시스템에 복사해야 합니다.  
  
> [!NOTE]
>  생성된 프로젝트를 편집하려면 시스템 로캘을 선택한 언어의 적절한 시스템 로캘로 설정해야 합니다.  
  
 템플릿에는 각각 다음 표에 나열된 대로 \Microsoft Visual Studio.NET 2003\Vc7\VCWizards\mfcappwiz\templates\ 디렉터리의 폴더가 할당됩니다. 원하는 언어 템플릿에 액세스하려면 해당 폴더를 컴퓨터의 \mfcappwiz\templates\ 디렉터리에 복사합니다. 폴더를 복사하면 언어가 MFC 응용 프로그램 마법사의 **응용 프로그램 종류** 페이지에 있는 **리소스 언어** 목록에 나타납니다.  
  
### <a name="language-templates-provided-in-visual-studio-net"></a>Visual Studio .NET에 제공되는 언어 템플릿  
  
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
  
## <a name="format-of-visual-c-wizard-generated-files"></a>Visual C++ 마법사에서 생성된 파일 형식  
 Visual C++ 마법사는 설치된 언어 버전의 Visual Studio가 시스템 로캘과 일치하지 않으면, 유니코드로 프로젝트를 생성합니다. 예를 들어 일본어 버전의 Visual Studio가 국가별 설정이 일본어 이외의 언어로 설정된 컴퓨터에 설치된 경우, Visual C++ 마법사는 유니코드 파일로 구성된 프로젝트를 생성합니다. 이는 Windows 다중 언어(MUI) 팩으로 설정된 컴퓨터에서 일반적입니다.  
  
 이 동작은 시스템 로캘이 Visual Studio의 언어 버전과 동일하도록 설정된 시스템과 다릅니다. 이 경우 시스템 코드 페이지에서 ANSI로 프로젝트 파일이 생성됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 프로젝트용 파일 형식](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Visual C++ 프로젝트 만들기 및 관리](../ide/creating-and-managing-visual-cpp-projects.md)