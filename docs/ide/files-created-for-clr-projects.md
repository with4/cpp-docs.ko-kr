---
title: "CLR 프로젝트용 파일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Visual C++ projects, CLR programming
- .NET applications, C++
ms.assetid: 59ae9020-5f26-4ad0-bbdd-97c2e2023a20
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 355b22ecf40251e3bb0b9910660e56bf9fe763a7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="files-created-for-clr-projects"></a>CLR 프로젝트용 파일
Visual c + + 서식 파일을 사용 하 여 프로젝트를 만들 때 사용 되는 서식 파일에 따라 여러 개의 파일 생성 됩니다. 다음 표에서.NET Framework 프로젝트에 대 한 프로젝트 템플릿으로 만든 모든 파일을 나열 합니다.  
  
|파일 이름|파일 설명|  
|---------------|----------------------|  
|AssemblyInfo.cpp|파일 정보 (즉, 특성, 파일, 리소스, 형식, 버전 관리 정보, 서명 정보 및 등)를 포함 하는 프로젝트의 어셈블리 메타 데이터를 수정 합니다. 자세한 내용은 참조 [어셈블리 개념](/dotnet/framework/app-domains/assembly-contents)합니다.|  
|*projname*.asmx|관리 되는 XML 웹 서비스의 기능을 캡슐화 하는 클래스를 참조 하는 텍스트 파일입니다.|  
|*projname*.cpp|주 소스 파일과 진입점 지점 응용 프로그램에는 Visual Studio를 생성 합니다. 프로젝트.dll 파일과 프로젝트 네임 스페이스를 식별합니다. 이 파일에 사용자 고유의 코드를 제공합니다.|  
|*projname*.vsdisco|XML 웹 서비스에 설명 하는 다른 리소스에 대 한 링크를 포함 하는 XML 배포 파일.|  
|*projname*.h|모든 선언, 전역 기호, 포함 하는 프로젝트에 대 한 주 포함 파일 및 `#include` 다른 헤더 파일에 대 한 지시문입니다.|  
|*projname*.sln|단일 솔루션으로 프로젝트의 모든 요소를 구성 하는 개발 환경 내에서 사용 되는 솔루션 파일입니다.|  
|*projname*.suo|개발 환경 내에서 사용 되는 솔루션 옵션 파일입니다.|  
|*projname*.vcxproj|이 프로젝트에 대 한 정보를 저장 하는 개발 환경 내에서 사용 되는 프로젝트 파일입니다.|  
|ReadMe.txt|각 파일에 템플릿으로 만든 실제 파일 이름을 사용 하 여 프로젝트를 설명 하는 파일입니다.|