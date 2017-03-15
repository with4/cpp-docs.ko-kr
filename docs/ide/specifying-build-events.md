---
title: "빌드 이벤트 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.IVCEventTool.CommandLine"
  - "VC.Project.IVCEventTool.ExcludedFromBuild"
  - "VC.Project.IVCEventTool.Description"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "빌드 이벤트[C++]"
  - "빌드 이벤트[C++], 지정"
  - "빌드[C++], C++ 사용자 지정"
  - "빌드[C++], 이벤트"
  - "사용자 지정 빌드 단계[C++], 빌드 이벤트"
  - "이벤트[C++], 빌드"
  - "빌드 후 이벤트"
  - "링크 전 이벤트"
ms.assetid: 788a6c18-2dbe-4a49-8cd6-86c1ad7a95cc
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 빌드 이벤트 지정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

빌드 이벤트를 사용하여 빌드 시작 전, 링크 프로세스 전 또는 빌드 완료 후에 실행되는 명령을 지정할 수 있습니다.  
  
 빌드 이벤트는 빌드가 빌드 프로세스의 해당 위치에 제대로 도달한 경우에만 실행됩니다.  빌드 도중 오류가 발생하면 *빌드 후* 이벤트는 발생하지 않으며, 링크 단계 이전에 오류가 발생하면 *링크 전* 이벤트나 *빌드 후* 이벤트가 발생하지 않습니다.  또한 파일을 링크할 필요가 없으면 *링크 전* 이벤트도 발생하지 않습니다.  또한 링크 단계가 없는 프로젝트에서는 *링크 전* 이벤트를 사용할 수 없습니다.  
  
 파일을 빌드할 필요가 없으면 빌드 이벤트가 발생하지 않습니다.  
  
 빌드 이벤트에 대한 일반 정보를 보려면 [사용자 지정 빌드 단계 및 빌드 이벤트 이해](../ide/understanding-custom-build-steps-and-build-events.md)를 참조하십시오.  
  
### 빌드 이벤트를 지정하려면  
  
1.  **솔루션 탐색기**에서 빌드 이벤트를 지정할 프로젝트를 선택합니다.  
  
2.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../ide/working-with-project-properties.md)을 참조하십시오.  
  
3.  **빌드 이벤트** 폴더에서 빌드 이벤트 속성 페이지를 선택합니다.  
  
4.  빌드 이벤트와 연관된 속성을 지정합니다.  
  
    -   명령 프롬프트에서 명령을 지정할 때와 같이 **명령줄**에서 명령을 지정합니다.  올바른 명령 또는 배치 파일과 필수 입력 또는 출력 파일을 지정합니다.  배치 파일의 이름 앞에 **call** 배치 명령을 지정해야 이어지는 모든 명령이 실행됩니다.  
  
         MSBuild 매크로를 사용하여 여러 입력 및 출력 파일을 기호로 지정할 수 있습니다.  [!INCLUDE[crabout](../build/reference/includes/crabout_md.md)] 파일의 위치 또는 파일 집합의 이름을 지정하는 방법에 대한 자세한 내용은 [빌드 명령 및 속성 매크로](../ide/common-macros-for-build-commands-and-properties.md)를 참조하십시오.  
  
         '%' 문자는 MSBuild에 예약되어 있으므로 환경 변수를 지정하는 경우 각 **%** 이스케이프 문자를 **%25** 16진수 이스케이프 시퀀스로 바꿉니다.  예를 들어 **%WINDIR%**는 **%25WINDIR%25**로 바꿉니다.  MSBuild는 환경 변수에 액세스하기 전에 각 **%25** 시퀀스를 **%** 문자로 바꿉니다.  
  
    -   **설명**에 이 이벤트에 대한 설명을 입력합니다.  설명은 이 이벤트가 발생할 때 **출력** 창에 표시됩니다.  
  
    -   이 이벤트를 실행하지 않으려면 **빌드에서 제외**에서 **예**를 지정합니다.  
  
## 참고 항목  
 [사용자 지정 빌드 단계 및 빌드 이벤트 이해](../ide/understanding-custom-build-steps-and-build-events.md)   
 [빌드 명령 및 속성 매크로](../ide/common-macros-for-build-commands-and-properties.md)   
 [빌드 사용자 지정 문제 해결](../ide/troubleshooting-build-customizations.md)