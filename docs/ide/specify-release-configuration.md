---
title: "기존 코드에서 새 프로젝트 릴리스 구성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.importwiz.releasesettings
dev_langs: C++
ms.assetid: 3e2fc73c-bdbd-4790-b2bd-d31731f0cece
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ff208af8bb89dbcb7df00b37ce542a5adae5fa23
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="specify-release-configuration-settings-create-new-project-from-existing-code-files-wizard"></a>기존 코드 파일에서 새 프로젝트 만들기 마법사, 릴리스 구성 설정 지정
기존 코드 파일에서 새 프로젝트 만들기 마법사의이 페이지를 사용 하 여 릴리스 구성 프로젝트 설정 지정 합니다.  
  
## <a name="task-list"></a>작업 목록  
 [방법: 기존 코드로 C++ 프로젝트 만들기](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **디버그 구성과 동일**  
 마법사가 릴리스 구성 프로젝트 설정 동일한 구성 프로젝트 설정 디버깅을 생성을 지정 합니다. 기본적으로이 옵션을 선택 합니다. 이 상자의 선택을 취소 하지 않으면이 페이지의 다른 모든 옵션이 비활성화 됩니다.  
  
 **빌드 명령줄**  
 새 프로젝트를 빌드하는 명령줄을 지정 합니다. 컴파일러 스위치 또는 인수를 새 프로젝트를 빌드하는 데 사용할 이름을 입력 합니다. 이 옵션은 때는 **외부 빌드 시스템 사용** 옵션을 선택는 **프로젝트 설정 지정** 페이지.  
  
 **다시 빌드 명령줄**  
 새 프로젝트를 다시 작성 하는 명령줄을 지정 합니다. 이 옵션은 때는 **외부 빌드 시스템 사용** 옵션을 선택는 **프로젝트 설정 지정** 페이지.  
  
 **정리 명령줄**  
 새 프로젝트에 대 한 빌드 도구에 의해 생성 된 지원 파일을 삭제 하도록 명령줄을 지정 합니다. 이 옵션은 때는 **외부 빌드 시스템 사용** 옵션을 선택는 **프로젝트 설정 지정** 페이지.  
  
 **출력 (디버깅)**  
 새 프로젝트의 디버그 구성에 대 한 출력 파일의 디렉터리 경로 지정합니다. 이 옵션은 때는 **외부 빌드 시스템 사용** 옵션을 선택는 **프로젝트 설정 지정** 페이지.  
  
 **전처리기 정의 (/ D)**  
 새 프로젝트에 대 한 전처리기 기호를 정의합니다. 자세한 내용은 [/D (Preprocessor Definitions)](../build/reference/d-preprocessor-definitions.md)을 참조하세요.  
  
 **포함 검색 경로 (/ I)**  
 새 프로젝트에서 전처리기 지시문에 전달 된 파일 참조를 확인 하는 컴파일러가 검색할 디렉터리 목록에 추가할 디렉터리 경로를 지정 합니다. 자세한 내용은 [/I(추가 포함 디렉터리)](../build/reference/i-additional-include-directories.md)를 참조하세요.  
  
 **강제 포함된 파일 (/FI)**  
 새 프로젝트를 빌드할 때 처리할 헤더 파일을 지정 합니다. 자세한 내용은 [/FI(강제 포함 파일 이름 지정)](../build/reference/fi-name-forced-include-file.md)를 참조하세요.  
  
 **.NET 어셈블리 검색 경로 (/ AI)**  
 새 프로젝트에서 전처리기 지시문에 전달 되는.NET 어셈블리 참조를 확인 하기 위해 컴파일러가 검색할 디렉터리 경로 지정 합니다. 자세한 내용은 [/AI(메타데이터 디렉터리 지정)](../build/reference/ai-specify-metadata-directories.md)를 참조하세요.  
  
 **.NET 어셈블리를 사용 하 여 강제 (/ FU)**  
 새 프로젝트를 빌드할 때 처리할.NET 어셈블리를 지정 합니다. 자세한 내용은 [/FU(강제 #using 파일 이름 지정)](../build/reference/fu-name-forced-hash-using-file.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [기존 코드 파일에서 새 프로젝트 만들기 마법사, 프로젝트 설정 지정](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)