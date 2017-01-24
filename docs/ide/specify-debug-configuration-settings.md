---
title: "기존 코드 파일에서 새 프로젝트 만들기 마법사, 디버그 구성 설정 지정 | Microsoft Docs"
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
  - "vc.appwiz.importwiz.debugsettings"
dev_langs: 
  - "C++"
ms.assetid: 607339a8-9d33-458b-8095-dc73f374e29d
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 기존 코드 파일에서 새 프로젝트 만들기 마법사, 디버그 구성 설정 지정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기존 코드 파일에서 새 프로젝트 만들기 마법사의 이 페이지를 사용하여 디버그 구성 프로젝트 설정을 지정할 수 있습니다.  
  
## 작업 목록  
 [방법: 기존 코드로 C\+\+ 프로젝트 만들기](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## UI 요소 목록  
 **빌드 명령줄**  
 새 프로젝트를 빌드하는 명령줄을 지정합니다.  예를 들어, 새 프로젝트를 빌드하는 데 사용할 컴파일러 이름\(및 스위치와 인수\) 또는 빌드 스크립트를 입력합니다.  이 옵션은 **프로젝트 설정 지정** 페이지에서 **외부 빌드 시스템 사용** 옵션을 선택한 경우 활성화됩니다. 그렇지 않은 경우에는 이 옵션을 사용할 수 없습니다.  
  
 **다시 빌드 명령줄**  
 새 프로젝트를 다시 빌드하는 명령줄을 지정합니다.  이 옵션은 **프로젝트 설정 지정** 페이지에서 **외부 빌드 시스템 사용** 옵션을 선택한 경우 활성화됩니다. 그렇지 않은 경우에는 이 옵션을 사용할 수 없습니다.  
  
 **정리 명령줄**  
 빌드 도구가 새 프로젝트에 대해 생성하는 지원 파일을 삭제하는 명령줄을 지정합니다.  이 옵션은 **프로젝트 설정 지정** 페이지에서 **외부 빌드 시스템 사용** 옵션을 선택한 경우 활성화됩니다. 그렇지 않은 경우에는 이 옵션을 사용할 수 없습니다.  
  
 **출력\(디버깅용\)**  
 새 프로젝트의 디버그 구성에 대한 출력 파일의 디렉터리 경로를 지정합니다.  이 옵션은 **프로젝트 설정 지정** 페이지에서 **외부 빌드 시스템 사용** 옵션을 선택한 경우 활성화됩니다. 그렇지 않은 경우에는 이 옵션을 사용할 수 없습니다.  
  
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