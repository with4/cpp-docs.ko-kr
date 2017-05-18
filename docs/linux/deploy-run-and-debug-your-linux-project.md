---
title: "Linux 프로젝트 배포, 실행 및 디버그 | Microsoft 문서"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7084cdb-17b1-4960-b522-f84981bea879
author: BrianPeek
ms.author: brpeek
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: dff1e9e03911f65dfcffcd078e0739224f73f4aa
ms.openlocfilehash: db868094a8f10ad05ed6f95bf8a4c8a29a2c941e
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---

# <a name="deploy-run-and-debug-your-project"></a>프로젝트 배포, 실행 및 디버그

프로젝트가 만들어졌으므로 코드가 컴파일, 실행 및 디버그될 Linux 컴퓨터에 연결해야 합니다.

1. 그림과 같이 Visual Studio에서 표준 드롭다운을 사용하여 원격 대상 아키텍처를 설정합니다. ![원격 아키텍처](media/architecture.png)

Linux 프로젝트를 조작하고 디버그할 수 있는 여러 가지 방법이 있습니다.

* 중단점, 조사식 창, 변수 가리키기와 같은 기존 Visual Studio 기능이 모두 예상대로 작동하므로 일반적인 방법으로 디버그할 수 있습니다.
* 특별한 [Linux 콘솔] 창은 **디버그 > Linux 콘솔** 메뉴 항목을 통해 열 수 있습니다.

  ![Linux 콘솔 메뉴](media/consolemenu.png)

  이 콘솔에서는 대상 컴퓨터의 콘솔 출력을 표시하고 입력을 받아들이고 대상 컴퓨터로 보냅니다.

  ![Linux 콘솔 창](media/consolewindow.png)

* 프로젝트의 **디버깅** 속성 페이지에서 **프로그램 인수** 항목을 사용하여 명령줄 인수를 실행 파일에 전달할 수 있습니다.
  
  ![프로그램 인수](media/settings_programarguments.png)

* GDB는 Linux에서 실행되는 응용 프로그램을 디버그하는 데 사용됩니다.  그러나 GDB는 두 가지 모드에서 실행할 수 있고, 모드는 프로젝트의 **디버깅** 속성 페이지에 있는 **디버깅 모드**에서 선택할 수 있습니다.

  ![GDB 옵션](media/settings_debugger.png)

  | 선택 항목 | 설명
  | --------- | ---
  | gdbserver | 원격 시스템에서 실행되는 gdbserver에 연결된 GDB는 로컬에서 실행됩니다.  [Linux 콘솔] 창이 지원하는 모드는 이 모드뿐입니다. 
  | gdb       | Visual Studio 디버거는 로컬 버전의 GDB가 대상 컴퓨터에 설치된 버전과 호환되지 않을 경우 더 호환성이 높은 원격 시스템에서 GDB를 실행합니다.

* 특정 디버거 옵션은 **추가 디버거 명령** 항목을 통해 GDB에 전달될 수 있습니다.  예를 들어 SIGILL(잘못된 명령) 신호를 무시하고자 할 경우  **handle** 명령을 사용하여 신호를 무시할 수 있습니다.  위 그림처럼 **추가 디버거 명령** 항목에 다음 내용을 추가하면 됩니다.

  ```handle SIGILL nostop noprint```

