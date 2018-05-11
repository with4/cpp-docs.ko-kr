---
title: 사용자 지정 빌드 단계 및 빌드 이벤트 이해 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- builds [C++], events
- custom build steps [C++], customizing builds
- events [C++], build
- custom build steps [C++]
- build steps [C++]
- build events [C++], order of events and build steps
- build steps [C++], build events
- builds [C++], custom build steps
ms.assetid: beb2f017-3e9f-4b2c-9b57-2572fd2628e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a50c0cf224104f720a73a4830405e7114cda74ed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="understanding-custom-build-steps-and-build-events"></a>사용자 지정 빌드 단계 및 빌드 이벤트 이해
Visual c + + 개발 환경 내 세 가지가 기본 빌드 프로세스를 사용자 지정할 수 있습니다.  
  
 **사용자 지정 빌드 단계**  
 사용자 지정 빌드 단계에는 프로젝트와 연결 된 빌드 규칙입니다. 사용자 지정 빌드 단계 추가 입력 또는 출력 파일 및 표시할 메시지를 실행 하는 명령줄을 지정할 수 있습니다. 자세한 내용은 참조 [하는 방법: MSBuild 프로젝트에 사용자 지정 빌드 단계 추가](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)합니다.  
  
 **사용자 지정 빌드 도구**  
 사용자 지정 빌드 도구에는 하나 이상의 파일에 연결 된 빌드 규칙입니다. 사용자 지정 빌드 단계에는 사용자 지정 빌드 도구에 입력된 파일을 전달할 수 또는 이상의 출력 파일입니다. 예를 들어, MFC 응용 프로그램의 도움말 파일 사용자 지정 빌드 도구와 함께 빌드됩니다. 자세한 내용은 참조 [하는 방법: MSBuild 프로젝트에 사용자 지정 빌드 도구 추가](../build/how-to-add-custom-build-tools-to-msbuild-projects.md) 및 [사용자 지정 빌드 도구 지정](../ide/specifying-custom-build-tools.md)합니다.  
  
 **빌드 이벤트**  
 빌드 이벤트를 통해 프로젝트의 빌드를 사용자 지정할 수 있습니다. 빌드 이벤트 세 가지가: *빌드 전*, *링크 전*, 및 *빌드 후*합니다. 빌드 이벤트를 사용 하면 빌드 프로세스에서 특정 시간에 발생 하는 동작을 지정할 수 있습니다. 예를 들어 있는 파일을 등록 하려면 빌드 이벤트를 사용할 수 있습니다 **regsvr32.exe** 프로젝트 빌드가 끝난 후 합니다. 자세한 내용은 참조 [빌드 이벤트 지정](../ide/specifying-build-events.md)합니다.  
  
 [사용자 지정 빌드 문제 해결](../ide/troubleshooting-build-customizations.md) 사용자 지정 빌드 단계를 확인 하 고 빌드 이벤트가 예상 대로 실행 수 있습니다.  
  
 출력 형식을 사용자 지정 빌드 단계 또는 빌드 이벤트 도구의 유용성 향상 시킬 수도 있습니다. 자세한 내용은 [사용자 지정 빌드 단계 또는 빌드 이벤트의 출력 형식 지정](../ide/formatting-the-output-of-a-custom-build-step-or-build-event.md)을 참조하세요.  
  
 빌드 이벤트와 사용자 지정 빌드 단계 다른 빌드 단계와 함께 다음과 같은 순서로 실행:  
  
1.  빌드 전 이벤트  
  
2.  사용자 지정 빌드 도구를 개별 파일에 대해  
  
3.  MIDL  
  
4.  리소스 컴파일러  
  
5.  C/c + + 컴파일러  
  
6.  링크 전 이벤트  
  
7.  링커 또는 적절 하 게 라이브러리 관리자  
  
8.  매니페스트 도구  
  
9. BSCMake  
  
10. 프로젝트에 사용자 지정 빌드 단계  
  
11. 빌드 후 이벤트  
  
 `custom build step on the project` 및 `post-build event` 프로세스가 완료 된 다른 모든 빌드 후에 순차적으로 실행 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에서 c + + 프로젝트 빌드](../ide/building-cpp-projects-in-visual-studio.md)   
 [빌드 명령 및 속성에 대 한 일반적인 매크로](../ide/common-macros-for-build-commands-and-properties.md)   
 [도구 빌드 순서 대화 상자](http://msdn.microsoft.com/en-us/6204c5b1-7ce9-4948-9ff6-0268642ee14c)