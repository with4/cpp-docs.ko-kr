---
title: "사용자 지정 빌드 단계 및 빌드 이벤트 이해 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "빌드 이벤트[C++], 이벤트 및 빌드 단계 순서"
  - "빌드 단계[C++]"
  - "빌드 단계[C++], 빌드 이벤트"
  - "빌드[C++], 사용자 지정 빌드 단계"
  - "빌드[C++], 이벤트"
  - "사용자 지정 빌드 단계[C++]"
  - "사용자 지정 빌드 단계[C++], 빌드 사용자 지정"
  - "이벤트[C++], 빌드"
ms.assetid: beb2f017-3e9f-4b2c-9b57-2572fd2628e4
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 사용자 지정 빌드 단계 및 빌드 이벤트 이해
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 개발 환경에서는 빌드 프로세스를 세 가지 기본 방법으로 사용자 지정할 수 있습니다.  
  
 **사용자 지정 빌드 단계**  
 사용자 지정 빌드 단계는 프로젝트와 관련된 빌드 규칙입니다.  사용자 지정 빌드 단계는 실행할 명령줄, 추가 입력 또는 출력 파일 및 표시할 메시지를 지정할 수 있습니다.  자세한 내용은 [방법: MSBuild 프로젝트에 사용자 지정 빌드 단계 추가](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)을 참조하십시오.  
  
 **사용자 지정 빌드 도구**  
 사용자 지정 빌드 도구란 하나 이상의 파일과 연관된 빌드 규칙을 말합니다.  사용자 지정 빌드 단계에서는 입력 파일을 사용자 지정 빌드 도구에 전달하여 하나 이상의 출력 파일을 생성할 수 있습니다.  예를 들어, MFC 응용 프로그램의 도움말 파일은 사용자 지정 도구를 통해 빌드됩니다.  자세한 내용은 [방법: MSBuild 프로젝트에 사용자 지정 빌드 도구 추가](../build/how-to-add-custom-build-tools-to-msbuild-projects.md) 및 [사용자 지정 빌드 도구 지정](../ide/specifying-custom-build-tools.md)를 참조하십시오.  
  
 **빌드 이벤트**  
 빌드 이벤트를 사용하면 프로젝트의 빌드를 사용자 지정할 수 있습니다.  빌드 이벤트는 *빌드 전*, *링크 전* 및 *빌드 후* 등 세 가지가 있습니다.  빌드 이벤트를 사용하면 빌드 프로세스의 특정 시기에 발생시킬 동작을 지정할 수 있습니다.  예를 들어, 빌드 이벤트를 사용하면 프로젝트 빌드가 끝난 후 **regsvr32.exe**를 사용하여 파일을 등록할 수 있습니다.  자세한 내용은 [빌드 이벤트 지정](../ide/specifying-build-events.md)을 참조하십시오.  
  
 [빌드 사용자 지정 문제 해결](../ide/troubleshooting-build-customizations.md)에서는 사용자 지정 빌드 단계와 빌드 이벤트가 예상한 대로 실행되는지 확인할 수 있습니다.  
  
 사용자 지정 빌드 단계나 빌드 이벤트의 출력 형식을 지정하여 이 도구를 보다 유용하게 사용할 수도 있습니다.  자세한 내용은 [사용자 지정 빌드 단계 또는 빌드 이벤트의 출력 형식 지정](../ide/formatting-the-output-of-a-custom-build-step-or-build-event.md)을 참조하십시오.  
  
 빌드 이벤트와 사용자 지정 빌드 단계는 다른 빌드 단계와 함께 다음 순서로 실행됩니다.  
  
1.  빌드 전 이벤트  
  
2.  개별 파일에 대한 사용자 지정 빌드 도구  
  
3.  MIDL  
  
4.  리소스 컴파일러  
  
5.  C\/C\+\+ 컴파일러  
  
6.  링크 전 이벤트  
  
7.  링커 또는 라이브러리 관리자\(해당되는 경우\)  
  
8.  매니페스트 도구  
  
9. BSCMake  
  
10. 프로젝트에 대한 사용자 지정 빌드 단계  
  
11. 빌드 후 이벤트  
  
 `custom build step on the project` 및 `post-build event`는 다른 모든 빌드 프로세스가 완료된 후에 순차적으로 실행됩니다.  
  
## 참고 항목  
 [Visual Studio에서 C\+\+ 프로젝트 빌드](../ide/building-cpp-projects-in-visual-studio.md)   
 [빌드 명령 및 속성 매크로](../ide/common-macros-for-build-commands-and-properties.md)   
 [Tool Build Order Dialog Box](http://msdn.microsoft.com/ko-kr/6204c5b1-7ce9-4948-9ff6-0268642ee14c)