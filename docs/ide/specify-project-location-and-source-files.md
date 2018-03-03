---
title: "기존 코드-소스 파일 (Visual c + +)에서 새 프로젝트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.importwiz.location
dev_langs:
- C++
ms.assetid: 29ddffb9-5918-4d72-8c7a-a365f9de96dd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04f73f89745f797658029eac2331d1764af4c065
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="specify-project-location-and-source-files-create-new-project-from-existing-code-files-wizard"></a>기존 코드 파일에서 새 프로젝트 만들기 마법사, 프로젝트 위치 및 소스 파일 지정
기존 코드 파일에서 새 프로젝트 만들기 마법사의이 페이지를 사용 하 여 지정할 수 있습니다.  
  
-   새 프로젝트의 디렉터리 경로  
  
-   기존 소스 파일을 검색할 디렉터리  
  
-   파일의 종류 마법사에서 새 프로젝트로 가져옵니다.  
  
## <a name="task-list"></a>작업 목록  
 [방법: 기존 코드로 C++ 프로젝트 만들기](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **프로젝트 파일 위치**  
 새 프로젝트의 디렉터리 경로 지정합니다. 이 위치는 모든 파일 (및 하위 디렉터리) 새 프로젝트의 마법사 위치를 저장 합니다.  
  
 **찾아보기**  
 표시는 **프로젝트 파일 위치** 대화 상자에서 새 프로젝트를 포함할 디렉터리를 지정할 수 있도록 합니다. 이 컨트롤을 사용 하 고 원하는 폴더를 이동할 수 있습니다.  
  
 **프로젝트 이름**  
 새 프로젝트의 이름을 지정합니다. 등과 같은.vcxproj 인 프로젝트 파일을이 이름은 채택 하 게 합니다. 기존 코드 파일에는 원래 이름을 유지 됩니다.  
  
 **이 폴더에서 파일을 프로젝트에 추가**  
 옵션을 선택 하면 새 프로젝트에 (즉이 컨트롤 아래에 있는 목록 상자에 지정 된)은 원래 디렉터리에서 기존 코드 파일을 복사 하려면 마법사를 설정 합니다.  
  
 **하위 폴더 추가**  
 디렉터리의 모든 하위 디렉터리에서 코드 파일을 복사 하려면 나열 된 지정 **폴더** 새 프로젝트에는 열입니다.  
  
 **폴더**  
 새 프로젝트에 복사 하려면 기존 코드 파일을 포함 하는 디렉터리의 경로를 나타냅니다. 이 열에서 마법사는 기존 코드 파일에 대 한 검색 하는 모든 디렉터리를 나열 합니다.  
  
 **추가**  
 표시는 **이 폴더에서 파일을 프로젝트에 추가** 마법사가 기존 코드 파일을 검색할 디렉터리를 지정할 수 있도록 대화 상자.  
  
 **제거**  
 이 컨트롤의 목록 상자 왼쪽에서 선택 되어 있는 디렉터리 경로 삭제 합니다.  
  
 **프로젝트에 추가할 파일 형식**  
 마법사는 지정 된 파일 확장명에 따라 새 프로젝트에 추가 하는 파일의 종류를 지정 합니다. 파일 확장명 앞에와 별표 와일드 카드 문자 및 파일 확장명의 목록에는 세미콜론으로 구분 됩니다.  
  
 **솔루션 탐색기에서 모든 파일 표시**  
 솔루션 탐색기 창에 표시 되도록 새 프로젝트의 모든 파일을 지정 합니다. 기본적으로 이 옵션은 사용하도록 설정됩니다.