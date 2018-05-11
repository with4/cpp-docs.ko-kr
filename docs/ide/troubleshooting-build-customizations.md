---
title: 빌드 사용자 지정 문제 해결 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- build events [C++], troubleshooting
- builds [C++], build events
- troubleshooting [C++], builds
- build steps [C++], troubleshooting
- events [C++], build
- builds [C++], troubleshooting
- custom build steps [C++], troubleshooting
ms.assetid: e4ceb177-fbee-4ed3-a7d7-80f0d78c1d07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d48e9f7bdcbf422a25fb0bdb40411e6c662fadc2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-build-customizations"></a>빌드 사용자 지정 문제 해결
사용자 지정 빌드 단계 또는 이벤트에는 예상 대로 작동 하지 않으면 경우 무엇이 문제 입니까 이해 하려고 할 수 있는 몇 가지 사항이 있습니다.  
  
-   사용자 지정 빌드 단계를 생성 하는 파일에 출력으로 선언 하는 파일와 일치 하는지 확인 합니다.  
  
-   입력에 있는 모든 파일을 생성 하는 사용자 지정 빌드 단계 또는 다른 종속성 빌드 단계 (사용자 지정 또는 다른 방법), 다음 사항을 확인 하는 경우 해당 파일을 프로젝트에 추가 됩니다. 고 이러한 파일을 사용 하는 도구는 사용자 지정 빌드 단계 후에 실행 되는지 확인 합니다.  
  
-   사용자 지정 빌드 단계 실제로 수행 하는 추가 하며, `@echo on` 첫 번째 명령으로 합니다. 빌드 이벤트 및 빌드 단계 임시.bat 파일에 배치 하 고 프로젝트를 빌드할 때 실행 됩니다. 따라서 빌드 단계 명령을 하거나 오류 검사 빌드 이벤트를 추가할 수 있습니다.  
  
-   실제로 실행 된 중간 파일 디렉터리에 빌드 로그를 검사 합니다. 경로 빌드 로그의 이름으로 표시 됩니다는 **MSBuild** 매크로 식 **$ (intdir)\\$(MSBuildProjectName).log**합니다.  
  
-   빌드 로그에 정보가 기본 용량 보다 더 수집 하도록 프로젝트 설정을 수정 합니다. **도구** 메뉴에서 **옵션**을 클릭합니다. 에 **옵션** 대화 상자에서 클릭는 **프로젝트 및 솔루션** 노드와 클릭은 **빌드 및 실행** 노드. 그런 다음는 **MSBuild 프로젝트 빌드 로그 파일의 자세한 정도** 상자 **Detailed**합니다.  
  
-   파일 또는 디렉터리 이름을 매크로 사용 하는 모든 값을 확인 합니다. 매크로 개별적으로 출력 하거나 추가할 수 있습니다 `copy %0 command.bat` 사용자 지정 빌드 단계 시작 위치에 있는으로 복사를 사용자 지정 빌드 단계 명령을 모든 매크로 확장 합니다.  
  
-   사용자 지정 빌드 단계를 실행 하 고 빌드 이벤트를 개별적으로 여 동작을 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 빌드 단계 및 빌드 이벤트 이해](../ide/understanding-custom-build-steps-and-build-events.md)