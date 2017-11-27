---
title: "디버거 속성(Linux C++) | Microsoft Docs"
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c1c0fcc-a49b-451c-a5cb-ce9711fac064
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.RaspberryDebugger.DebuggerType
- VC.Project.IVCLocalDebugPageObject.CommandArguments
- VC.Project.IVCLocalDebugPageObject.WorkingDirectory
- VC.Project.RaspberryDebugger.LaunchActivity
- VC.Project.LinuxDebugger.DebugChildProcesses
ms.openlocfilehash: d47645eab33ffb0ee6a203fdfb0cf30c856ea63f
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="c-debugging-properties-linux-c"></a>C++ 디버깅 속성(Linux C++)

속성 | 설명 | 선택 항목
--- | ---| ---
사전 실행 명령 | 디버깅 시작 전과 디버거 실행 전에 셸에서 실행되는 명령이며 디버깅 환경에 영향을 주기 위해 사용할 수 있습니다.
프로그램 | 원격 시스템에서 디버그할 프로그램에 대한 전체 경로입니다. 원격 시스템의 경로입니다. 비워 두거나 변경하지 않으면 현재 프로젝트 출력이 기본값으로 설정됩니다.
프로그램 인수 | 디버그 중인 프로그램에 전달할 명령줄 인수입니다.
작업 디렉터리 | 원격 응용 프로그램의 작업 디렉터리입니다. 기본적으로 사용자 홈 디렉터리입니다.
추가 디버거 명령 | 디버깅 시작 전에 디버거가 실행할 추가 gdb 명령입니다.
디버거 포트 번호 | 원격 디버거와의 디버거 통신을 위한 포트 번호입니다. 포트는 로컬에서 사용 중이지 않아야 합니다. 이 값은 1에서 65535 사이의 양수여야 합니다. 입력하지 않을 경우 사용 가능한 포트 번호가 사용됩니다.
원격 디버거 포트 번호 | 원격 디버거 서버(gdbserver)가 원격 시스템에서 수신 대기 중인 포트 번호입니다. 포트는 원격 시스템에서 사용 중이지 않아야 합니다. 이 값은 1에서 65535 사이의 양수여야 합니다. 입력하지 않을 경우 4444 이상의 사용 가능한 포트 번호가 사용됩니다.
디버깅 모드 | 디버거가 gdb와 상호 작용하는 방법을 지정합니다. gdb 모드에서 디버거는 원격 시스템의 셸을 통해 gdb를 구동합니다. gdbserver 모드에서 gdb는 로컬에서 실행되고, 원격으로 실행되는 gdbserver에 연결됩니다. | **gdbserver**<br>**gdb**<br>
추가 기호 검색 경로 | 디버그 기호에 대한 추가 검색 경로(solib-search-path)입니다.
자식 프로세스 디버그 | 자식 프로세스 디버그 사용 여부를 지정합니다.
Python 보기 쉽게 인쇄 사용 | 식 값을 보기 쉽게 인쇄하는 기능을 사용합니다. gdb 디버깅 모드에서만 지원됩니다.
시각화 파일 | SLT 형식에 대한 시각화 지시문이 들어 있는 기본 네이티브 시각화 파일(.natvis)입니다. 현재 솔루션에 속하는 다른 .natvis 파일이 자동으로 로드됩니다.
추가 소스 파일 경로 맵 | 디버거에서 Windows 소스 파일 이름을 Linux 소스 파일 이름에 매핑하는 데 사용하는 추가 동등 경로입니다. 형식은 "\<windows-path>=\<linux-path>;..."입니다. Windows 경로에 있는 소스 파일 이름은 Linux 경로에 있는 동일한 상대적 위치에 있는 것처럼 참조됩니다. 로컬 프로젝트에 있는 파일은 추가 매핑이 필요하지 않습니다.