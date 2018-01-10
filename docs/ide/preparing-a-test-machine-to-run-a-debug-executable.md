---
title: "디버그 실행 파일을 실행 하려면 테스트 컴퓨터 준비 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: debug executable, preparing a test machine to run
ms.assetid: f0400989-cc2e-4dce-9788-6bdbe91c6f5a
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 344f413eb2325156996700b6975826600ab997f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="preparing-a-test-machine-to-run-a-debug-executable"></a>디버그 실행 파일을 실행하기 위한 테스트 컴퓨터 준비
Visual C++로 빌드한 응용 프로그램의 디버그 버전을 테스트하기 위해 컴퓨터를 준비하려면 응용 프로그램이 종속된 Visual C++ 라이브러리 DLL의 디버그 버전을 배포해야 합니다. 단계에 따라 Dll을 배포 해야 하는 문제를 식별 하려면 [Visual c + + 응용 프로그램의 종속성 이해](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)합니다. Visual C++ 라이브러리 DLL의 디버그 버전에는 일반적으로 "d"로 끝나는 이름이 부여됩니다. 예를 들어 msvcr100.dll의 디버그 버전 이름은 msvcr100d.dll입니다.  
  
> [!NOTE]
>  응용 프로그램의 디버그 버전은 재배포할 수 없으며 Visual C++ 라이브러리 DLL의 디버그 버전도 재배포할 수 없습니다. 응용 프로그램과 Visual C++ DLL의 디버그 버전은 Visual Studio가 설치되지 않은 컴퓨터에서 응용 프로그램을 디버깅 및 테스트하기 위한 목적으로만 다른 컴퓨터에 배포할 수 있습니다. 자세한 내용은 [Redistributing Visual C++ Files](../ide/redistributing-visual-cpp-files.md)을 참조하세요.  
  
 세 가지 방법으로 응용 프로그램의 디버그 버전과 Visual C++ 라이브러리 DLL의 디버그 버전을 함께 배포할 수 있습니다.  
  
-   올바른 라이브러리 버전과 응용 프로그램의 아키텍처에 대한 병합 모듈을 포함한 설치 프로젝트를 사용하고 중앙 배포를 이용하여 특정 Visual C++ DLL 디버그 버전을 %windir%\system32\ 디렉터리에 설치합니다. 병합 모듈은 Program Files 또는 Program Files (x86) 디렉터리의 \common 모듈에서 발견 되\\합니다. 병합 모듈의 디버그 버전에는 Microsoft_VC110_DebugCRT_x86.msm과 같이 이름에 Debug가 있습니다. 이 배포의 예제에서 확인할 수 있습니다 [연습: 설치 프로젝트는 Visual c + + 응용 프로그램 사용 하 여 배포](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)합니다.  
  
-   Program Files 또는 Program Files (x86) 디렉터리 \microsoft Visual Studio에서 제공 되는 파일을 사용 하 여 응용 프로그램의 설치 디렉터리에 특정 Visual c + + DLL의 디버그 버전을 설치 하려면 로컬 배포를 사용 하 여 \<버전 > \VC\redist\Debug_NonRedist\\합니다.  
  
    > [!NOTE]
    >  다른 컴퓨터에서 Visual C++ 2005 또는 Visual C++ 2008로 빌드한 응용 프로그램을 원격으로 디버깅하려면 Visual C++ 라이브러리 DLL 디버그 버전을 공유 side-by-side 어셈블리로 배포해야 합니다. 설치 프로젝트 또는 Windows Installer를 사용하여 해당 병합 모듈을 설치할 수 있습니다.  
  
-   출력물을 사용 하 여**배포** 옵션에 **Configuration Manager** 프로젝트 출력 및 다른 파일을 원격 컴퓨터에 복사 하는 Visual Studio에서 대화 상자. 
  
 Visual C++ DLL이 설치되었으면 네트워크 공유를 통해 원격 디버거를 실행할 수 있습니다. 원격 디버깅에 대 한 자세한 내용은 참조 [원격 디버깅](/visualstudio/debugger/remote-debugging.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 
 [Visual c + + 배포](../ide/deployment-in-visual-cpp.md)   
 [Windows Installer 명령 줄 옵션](http://msdn.microsoft.com/library/windows/desktop/aa367988.aspx)   
 [배포 예제](../ide/deployment-examples.md) [원격 디버깅](/visualstudio/debugger/remote-debugging.md)