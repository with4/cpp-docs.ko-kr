---
title: 기존 코드 - 원본 파일에서 새 프로젝트 만들기(Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.importwiz.location
dev_langs:
- C++
ms.assetid: 29ddffb9-5918-4d72-8c7a-a365f9de96dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d85a7b85996ed307596865a31d55cf4b119e5bd5
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33338697"
---
# <a name="specify-project-location-and-source-files-create-new-project-from-existing-code-files-wizard"></a>기존 코드 파일에서 새 프로젝트 만들기 마법사, 프로젝트 위치 및 소스 파일 지정
기존 코드 파일에서 새 프로젝트 만들기 마법사의 이 페이지를 사용하여 다음을 지정합니다.  
  
-   새 프로젝트의 디렉터리 경로  
  
-   기존 원본 파일을 검색할 디렉터리  
  
-   마법사가 새 프로젝트로 가져올 파일 종류  
  
## <a name="task-list"></a>작업 목록  
 [방법: 기존 코드로 C++ 프로젝트 만들기](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **프로젝트 파일 위치**  
 새 프로젝트의 디렉터리 경로를 지정합니다. 이 위치에 마법사가 새 프로젝트의 모든 파일(및 하위 디렉터리)을 저장합니다.  
  
 **찾아보기**  
 새 프로젝트를 포함할 디렉터리를 지정하는 데 도움이 되는 **프로젝트 파일 위치** 대화 상자를 표시합니다. 이 컨트롤을 사용하여 원하는 폴더로 이동할 수 있습니다.  
  
 **프로젝트 이름**  
 새 프로젝트의 이름을 지정합니다. .vcxproj와 같은 파일 확장명을 가진 프로젝트 파일은 이 이름을 사용합니다. 기존 코드 파일은 원래 이름을 유지합니다.  
  
 **이 폴더의 파일을 프로젝트에 추가**  
 이 옵션을 선택하면 원래 디렉터리(이 컨트롤 아래 목록 상자에 지정됨)의 기존 파일을 새 프로젝트로 복사하도록 마법사가 설정됩니다.  
  
 **하위 폴더 추가**  
 **폴더** 열에 나열된 디렉터리의 모든 하위 디렉터리에서 코드 파일을 새 프로젝트로 복사하도록 지정합니다.  
  
 **폴더**  
 새 프로젝트에 복사할 기존 코드 파일이 들어 있는 디렉터리의 경로를 나타냅니다. 이 열은 마법사가 기존 코드 파일을 검색할 모든 디렉터리를 나열합니다.  
  
 **추가**  
 마법사가 기존 코드 파일을 검색할 디렉터리를 지정하는 데 도움이 되는 **이 폴더에서 프로젝트에 파일 추가** 대화 상자를 표시합니다.  
  
 **제거**  
 이 컨트롤의 왼쪽 목록 상자에서 선택한 디렉터리 경로를 삭제합니다.  
  
 **프로젝트에 추가할 파일 형식**  
 마법사가 지정된 파일 확장명에 따라 새 프로젝트에 추가할 파일의 종류를 지정합니다. 파일 확장명 앞에는 별표 와일드카드 문자가 오며, 파일 확장명 목록은 세미콜론으로 구분됩니다.  
  
 **솔루션 탐색기에 모든 파일 표시**  
 새 프로젝트의 모든 파일을 솔루션 탐색기 창에 표시하도록 지정합니다. 기본적으로 이 옵션은 사용하도록 설정됩니다.