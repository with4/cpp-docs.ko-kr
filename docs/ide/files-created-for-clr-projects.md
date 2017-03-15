---
title: "CLR 프로젝트용 파일 | Microsoft Docs"
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
  - ".NET 응용 프로그램, C++"
  - "Visual C++ 프로젝트, CLR 프로그래밍"
ms.assetid: 59ae9020-5f26-4ad0-bbdd-97c2e2023a20
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# CLR 프로젝트용 파일
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 템플릿을 사용하여 프로젝트를 만들면 사용하는 템플릿에 따라 몇 가지 파일이 만들어집니다.  다음 표에서는 .NET Framework 프로젝트용 프로젝트 템플릿을 사용하여 만드는 모든 파일을 보여 줍니다.  
  
|파일 이름|파일 설명|  
|-----------|-----------|  
|AssemblyInfo.cpp|프로젝트의 어셈블리 메타데이터를 수정하기 위한 정보, 즉 특성, 파일, 리소스, 형식, 버전 정보, 시그니처 정보 등을 포함하는 파일입니다.  자세한 내용은 [어셈블리 개념](../Topic/Assembly%20Contents.md)을 참조하십시오.|  
|*projname*.asmx|XML Web services의 기능을 캡슐화하는 관리되는 클래스를 참조하는 텍스트 파일입니다.|  
|*projname*.cpp|이 파일은 주요 소스 파일로서 Visual Studio에서 사용자를 위해 작성한 응용 프로그램의 진입점입니다.  프로젝트 .dll 파일과 프로젝트 네임스페이스를 식별합니다.  이 파일에 사용자가 작성한 코드를 넣습니다.|  
|*projname*.vsdisco|XML Web services를 설명하는 다른 리소스에 대한 링크가 있는 XML 배포 파일입니다.|  
|*projname*.h|모든 선언, 전역 기호 및 기타 헤더 파일에 대한 `#include` 지시문이 있는 프로젝트의 주요 포함 파일입니다.|  
|*projname*.sln|개발 환경 내에서 사용자 프로젝트의 모든 요소를 단일 솔루션으로 구성하는 데 사용하는 솔루션 파일입니다.|  
|*projname*.suo|개발 환경 내에서 사용되는 솔루션 옵션 파일입니다.|  
|*projname*.vcxproj|개발 환경 내에서 해당 프로젝트 고유의 정보를 저장하는 데 사용하는 프로젝트 파일입니다.|  
|ReadMe.txt|템플릿이 만든 실제 파일 이름을 사용하여 사용자 프로젝트의 각 파일에 대해 설명하는 파일입니다.|