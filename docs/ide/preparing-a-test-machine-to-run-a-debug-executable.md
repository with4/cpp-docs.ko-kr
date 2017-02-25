---
title: "디버그 실행 파일을 실행하기 위한 테스트 컴퓨터 준비 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "디버그 실행 파일, 실행할 테스트 컴퓨터 준비"
ms.assetid: f0400989-cc2e-4dce-9788-6bdbe91c6f5a
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# 디버그 실행 파일을 실행하기 위한 테스트 컴퓨터 준비
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+로 빌드한 응용 프로그램의 디버그 버전을 테스트하기 위해 컴퓨터를 준비하려면 응용 프로그램에서 의존하는 Visual C\+\+ 라이브러리 DLL의 디버그 버전을 배포해야 합니다.  배포할 DLL을 식별하려면 [Visual C\+\+ 응용 프로그램의 종속성 이해](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)에 제시된 단계를 따르십시오.  Visual C\+\+ 라이브러리 DLL의 디버그 버전에는 일반적으로 "d"로 끝나는 이름이 부여됩니다. 예를 들어, CRT DLL msvcr100.dll의 디버그 버전 이름은 msvcr100d.dll입니다.  
  
> [!NOTE]
>  응용 프로그램의 디버그 버전은 재배포할 수 없으며 Visual C\+\+ DLL의 디버그 버전도 재배포할 수 없습니다.  응용 프로그램과 Visual C\+\+의 DLL의 디버그 버전은 Visual Studio가 설치되지 않은 컴퓨터에서 응용 프로그램의 디버깅과 테스트를 위한 목적으로만 다른 컴퓨터에 배포할 수 있습니다.  자세한 내용은 [Visual C\+\+ 파일 재배포](../ide/redistributing-visual-cpp-files.md)을 참조하십시오.  
  
 세 가지 방법으로 응용 프로그램의 디버그 버전과 함께 Visual C\+\+ 라이브러리의 디버그 버전을 배포할 수 있습니다.  
  
-   올바른 라이브러리 버전과 응용 프로그램의 아키텍쳐에 대한 병합 모듈을 포함한 프로젝트 설치를 사용하고 중앙 배포를 이용하여 특정 Visual C\+\+ DLL 디버그 버전을 %windir%\\system32\\ 디렉토리에 설치합니다.  병합 모듈은 Program Files 또는 Program Files \(x86\) 디렉토리의 \\Common Files\\Merge Modules\\ 디렉토리에 있습니다.  병합 모듈의 디버그 버전은 Microsoft\_VC110\_DebugCRT\_x86.msm의 namefor 예제의 디버그를 갖고 있습니다.  이러한 배포 예제를 보려면 [연습: 설치 프로젝트를 사용하여 Visual C\+\+ 응용 프로그램 배포](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)를 참조하십시오.  
  
-   응용 프로그램의 설치 디렉토리에 디버그 버전의 특정 Visual C\+\+ DLL을 설치하기 위해서는 Program Files 또는 Program Files \(x86\) 디렉토리 안의 \\Microsoft Visual Studio \<version\>\\VC\\redist\\Debug\_NonRedist\\ 디렉토리에 제공된 파일을 이용하여 로컬 배포를 수행합니다.  
  
    > [!NOTE]
    >  다른 컴퓨터에서 Visual C\+\+ 2005 또는 Visual C\+\+ 2008로 빌드한 응용 프로그램을 원격으로 디버깅하려면, Visual C\+\+ 라이브러리 DLL 디버그 버전을 공유 side\-by\-side 어셈블리로 배포해야 합니다.  해당 병합 모듈을 살치하려면 프로젝트 설치 또는 Windows Installer를 사용할 수 있습니다.  
  
-   Visual Studio의 **구성 관리자** 대화 상자의 **배포** 옵션을 사용하여 프로젝트 출력물 및 기타 파일을 원격 컴퓨터에 복사합니다.  이러한 배포 예제를 보려면 [Visual Studio 프로젝트의 원격 디버깅 설정](../Topic/Set%20Up%20Remote%20Debugging%20for%20a%20Visual%20Studio%20Project.md)를 참조하십시오.  
  
 Visual C\+\+ DLL이 설치되었으면 네트워크 공유를 통해 원격 디버거를 실행할 수 있습니다.  원격 디버깅에 대한 자세한 내용은 [장치에서 원격 도구 설정](../Topic/Set%20Up%20the%20Remote%20Tools%20on%20the%20Device.md)을 참조하십시오.  
  
## 참고 항목  
 [장치에서 원격 도구 설정](../Topic/Set%20Up%20the%20Remote%20Tools%20on%20the%20Device.md)   
 [Visual C\+\+의 개발](../ide/deployment-in-visual-cpp.md)   
 [Windows Installer 명령을 명령줄 옵션](http://msdn.microsoft.com/library/windows/desktop/aa367988.aspx)   
 [배포 예제](../ide/deployment-examples.md)