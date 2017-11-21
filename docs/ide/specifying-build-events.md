---
title: "빌드 이벤트 지정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.IVCEventTool.CommandLine
- VC.Project.IVCEventTool.ExcludedFromBuild
- VC.Project.IVCEventTool.Description
dev_langs: C++
helpviewer_keywords:
- Pre-Link event
- build events [C++], specifying
- custom build steps [C++], build events
- builds [C++], events
- events [C++], build
- builds [C++], customizing C++
- build events [C++]
- post-build events
ms.assetid: 788a6c18-2dbe-4a49-8cd6-86c1ad7a95cc
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 43f12e28487a4e162a88eaf0881ac9e50391e1f4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="specifying-build-events"></a>빌드 이벤트 지정
빌드가 완료 된 후 또는 링크 프로세스 전에 빌드를 시작 하기 전에 실행 하는 명령을 지정 하려면 빌드 이벤트를 사용할 수 있습니다.  
  
 빌드 이벤트는 빌드가 빌드 프로세스의 해당 지점에 성공적으로 도달할 경우에만 실행됩니다. 빌드, 오류가 발생 하는 경우는 *빌드 후* 이벤트가 발생 하지 것입니다; 둘 다 연결 단계 전에 오류가 발생 한 경우는 *링크 전* 와 *빌드 후* 이벤트 됩니다 발생 합니다. 또한 파일 필요가 없으면를 연결 하는 경우는 *링크 전* 이벤트가 발생 하지 것입니다. *링크 전* 도 이벤트는 연결 단계를 포함 하지 않는 프로젝트에서 사용할 수 없습니다.  
  
 없는 파일을 빌드해야 필요가 빌드 이벤트가 발생 합니다.  
  
 빌드 이벤트에 대 한 일반적인 정보를 참조 하십시오. [이해 사용자 지정 빌드 단계 및 빌드 이벤트](../ide/understanding-custom-build-steps-and-build-events.md)합니다.  
  
### <a name="to-specify-a-build-event"></a>빌드 이벤트를 지정하려면  
  
1.  **솔루션 탐색기**에서 빌드 이벤트를 지정할 프로젝트를 선택합니다.  
  
2.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../ide/working-with-project-properties.md)합니다.  
  
3.  에 **빌드 이벤트** 폴더, 빌드 이벤트 속성 페이지를 선택 합니다.  
  
4.  빌드 이벤트와 연결 된 속성을 지정 합니다.  
  
    -   **명령줄**, 명령 프롬프트에서 지정 된 경우에 따라 명령을 지정 합니다. 올바른 명령 또는 배치 파일을 지정 하 고 필수 입력 또는 출력 파일입니다. 지정 된 **호출** 이후 모든 명령은 실행은 보장 하려면 배치 파일의 이름 앞에 명령을 배치 합니다.  
  
         여러 입력 및 출력 파일은 MSBuild 매크로 함께 기호로 지정할 수 있습니다. [!INCLUDE[crabout](../build/reference/includes/crabout_md.md)]참조 파일의 위치 또는 파일 집합의 이름을 지정 하 [빌드 명령 및 속성에 대 한 일반적인 매크로](../ide/common-macros-for-build-commands-and-properties.md)합니다.  
  
         각 환경 변수 대체를 지정 하는 경우 '%' 문자가 MSBuild에 의해 예약 되어 있으므로  **%**  이스케이프 문자는 **%25** 16 진수 이스케이프 시퀀스입니다. 예를 들어 대체 **% WINDIR %** 와 **%25WINDIR %25**합니다. 각 MSBuild 대체 **%25** 가진 시퀀스는  **%**  환경 변수에 액세스 하기 전에 문자입니다.  
  
    -   **설명**를이 이벤트에 대 한 설명을 입력 합니다. 설명에 표시 됩니다는 **출력** 창이이 이벤트가 발생 합니다.  
  
    -   **빌드에서 제외**, 지정 **예** 이벤트를 실행 하지 않도록 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 빌드 단계 및 빌드 이벤트 이해](../ide/understanding-custom-build-steps-and-build-events.md)   
 [빌드 명령 및 속성에 대 한 일반적인 매크로](../ide/common-macros-for-build-commands-and-properties.md)   
 [빌드 사용자 지정 문제 해결](../ide/troubleshooting-build-customizations.md)