---
title: "기존 코드 파일에서 새 프로젝트 만들기 마법사, 릴리스 구성 설정 지정 | Microsoft Docs"
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
  - "vc.appwiz.importwiz.releasesettings"
dev_langs: 
  - "C++"
ms.assetid: 3e2fc73c-bdbd-4790-b2bd-d31731f0cece
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 기존 코드 파일에서 새 프로젝트 만들기 마법사, 릴리스 구성 설정 지정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기존 코드 파일에서 새 프로젝트 만들기 마법사의 이 페이지를 사용하여 릴리스 구성 프로젝트 설정을 지정할 수 있습니다.  
  
## 작업 목록  
 [방법: 기존 코드로 C\+\+ 프로젝트 만들기](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## UI 요소 목록  
 **디버그 구성과 동일**  
 마법사가 디버그 구성 프로젝트 설정과 동일한 릴리스 구성 프로젝트 설정을 생성하도록 지정합니다.  이 옵션은 기본적으로 선택되어 있습니다.  이 확인란의 선택을 취소하지 않으면 이 페이지의 다른 모든 옵션은 비활성 상태입니다.  
  
 **빌드 명령줄**  
 새 프로젝트를 빌드하는 명령줄을 지정합니다.  새 프로젝트를 빌드하는 데 사용하려는 컴파일러 이름과 스위치 또는 인수를 입력합니다.  이 옵션은 **프로젝트 설정 지정** 페이지에서 **외부 빌드 시스템 사용** 옵션을 선택한 경우 활성화됩니다.  
  
 **다시 빌드 명령줄**  
 새 프로젝트를 다시 빌드하는 명령줄을 지정합니다.  이 옵션은 **프로젝트 설정 지정** 페이지에서 **외부 빌드 시스템 사용** 옵션을 선택한 경우 활성화됩니다.  
  
 **정리 명령줄**  
 빌드 도구가 새 프로젝트에 대해 생성하는 지원 파일을 삭제하는 명령줄을 지정합니다.  이 옵션은 **프로젝트 설정 지정** 페이지에서 **외부 빌드 시스템 사용** 옵션을 선택한 경우 활성화됩니다.  
  
 **출력\(디버깅용\)**  
 새 프로젝트의 디버그 구성에 대한 출력 파일의 디렉터리 경로를 지정합니다.  이 옵션은 **프로젝트 설정 지정** 페이지에서 **외부 빌드 시스템 사용** 옵션을 선택한 경우 활성화됩니다.  
  
 **전처리기 정의\(\/D\)**  
 새 프로젝트에 대한 전처리기 기호를 정의합니다.  자세한 내용은 [\/D\(전처리기 정의\)](../build/reference/d-preprocessor-definitions.md)를 참조하십시오.  
  
 **검색 경로 포함\(\/\)**  
 컴파일러가 새 프로젝트의 전처리기 지시문으로 전달되는 파일 참조를 확인하기 위해 검색할 수 있도록 디렉터리 목록에 추가할 디렉터리 경로를 지정합니다.  자세한 내용은 [\/I\(추가 포함 디렉터리\)](../build/reference/i-additional-include-directories.md)를 참조하십시오.  
  
 **강제 포함 파일\(\/FI\)**  
 새 프로젝트를 빌드할 때 처리할 헤더 파일을 지정합니다.  자세한 내용은 [\/FI\(강제 포함 파일 이름 지정\)](../build/reference/fi-name-forced-include-file.md)를 참조하십시오.  
  
 **.NET 어셈블리 검색 경로\(\/AI\)**  
 컴파일러가 새 프로젝트의 전처리기 지시문으로 전달되는 .NET 어셈블리 참조를 확인하기 위해 검색할 디렉터리 경로를 지정합니다.  자세한 내용은 [\/AI\(메타데이터 디렉터리 지정\)](../build/reference/ai-specify-metadata-directories.md)를 참조하십시오.  
  
 **강제 사용 .NET 어셈블리\(\/FU\)**  
 새 프로젝트를 빌드할 때 처리할 .NET 어셈블리를 지정합니다.  자세한 내용은 [\/FU\(강제 \#using 파일 이름 지정\)](../build/reference/fu-name-forced-hash-using-file.md)를 참조하십시오.  
  
## 참고 항목  
 [기존 코드 파일에서 새 프로젝트 만들기 마법사, 프로젝트 설정 지정](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)