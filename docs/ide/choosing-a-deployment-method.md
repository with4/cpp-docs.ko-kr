---
title: "배포 방법 선택 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "응용 프로그램 배포[C++], 메서드"
  - "응용 프로그램 배포[C++], 메서드"
  - "DLL[C++], 재배포"
  - "동적 링크[C++]"
  - "라이브러리[C++], 응용 프로그램 배포 문제"
  - "매니페스트[C++]"
  - "DLL 재배포"
  - "side-by-side 어셈블리[C++]"
  - "정적 링크[C++]"
ms.assetid: fd8eb956-f4a0-4ffb-b401-328c73e66986
caps.latest.revision: 35
caps.handback.revision: 35
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 배포 방법 선택
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 응용 프로그램이 독립적이고 복사 명령을 사용하는 경우가 아니면 Windows Installer를 사용하여 배포하는 것이 좋습니다.  Windows Installer는 설치, 수리 및 제거를 지원하고 응용 프로그램 파일, 종속성 및 레지스트리 항목의 원자성 업데이트도 지원합니다.  
  
> [!NOTE]
>  Visual Studio에서 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 네이티브 응용 프로그램에 대한 [ClickOnce](../Topic/ClickOnce%20Security%20and%20Deployment.md) 배포가 가능하지만 추가 단계가 필요합니다.  자세한 내용은 [Visual C\+\+ 응용 프로그램의 ClickOnce 배포](../ide/clickonce-deployment-for-visual-cpp-applications.md)을 참조하십시오.  
  
## 공유 DLL로서의 Visual C\+\+ 라이브러리  
 Visual C\+\+ 라이브러리는 Visual Studio 설치 관리자에 의해 %windir%\\system32\\ 디렉터리에 설치되기 때문에 종속된 Visual C\+\+ 응용 프로그램을 개발하면 예상대로 실행됩니다.  그러나 Visual Studio가 설치되지 않은 컴퓨터에 응용 프로그램을 배포하려면 라이브러리가 응용 프로그램과 함께 해당 컴퓨터에 설치되어야 합니다.  
  
## Visual C\+\+ 라이브러리 재배포  
 배포 시 재배포 권한이 있는 모든 버전의 Visual C\+\+ 라이브러리를 재배포할 수 있습니다.  배포 방법은 다음 세 가지가 있습니다.  
  
-   중앙 배포 \- 재배포 가능 패키지를 사용하며 %windir%\\system32\\에 Visual C\+\+ 라이브러리를 공유 DLL로 설치합니다. \(이 폴더에 설치하려면 관리자 권한이 필요합니다.\) 대상 컴퓨터에 응용 프로그램을 설치하기 전에 재배포 가능 패키지를 실행하는 스크립트 또는 설치 프로그램을 만들 수 있습니다.  재배포 가능 패키지는 x86, x64 및 ARM 플랫폼\(VCRedist\_x86.exe, VCRedist\_x64.exe 또는 VCRedist\_arm.exe\)에 사용할 수 있습니다.  Visual Studio는 이러한 패키지를 %ProgramFiles\(x86\)%\\Microsoft Visual Studio `version`\\VC\\Redist\\`locale ID`\\에 포함합니다.  [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/?LinkId=132793)에서도 이러한 파일을 다운로드할 수 있습니다. \(다운로드 센터에서 응용 프로그램과 일치하는 "[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 재배포 가능 패키지 *Visual Studio version and update*"를 검색합니다.\)  예를 들어 Visual Studio 2012 업데이트 4를 사용하여 응용 프로그램을 빌드한 경우 "Visual C\+\+ 재배포 가능 패키지 2012 업데이트 4"를 검색합니다.\) 재배포 가능 패키지를 사용하는 방법에 대한 자세한 내용은 [연습: Visual C\+\+ 재배포 가능 패키지를 사용하여 Visual C\+\+ 응용 프로그램 배포](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md)를 참조하십시오.  
  
-   중앙 배포 \- 병합 모듈을 사용하며 각 모듈이 %windir%\\system32\\에 특정 Visual C\+\+ 라이브러리를 공유 DLL로 설치합니다. \(이 폴더에 설치하려면 관리자 권한이 필요합니다.\) 병합 모듈은 응용 프로그램의 .msi 설치 관리자의 일부가 됩니다.  Visual C\+\+ 재배포 가능 병합 모듈은 Visual Studio의 \\Program Files \(x86\)\\Common Files\\Merge Modules\\에 포함됩니다.  자세한 내용은 [병합 모듈을 사용하여 재배포](../ide/redistributing-components-by-using-merge-modules.md)을 참조하십시오.  
  
-   로컬 배포 \- Visual Studio 설치, 보통 \\Program Files \(x86\)\\Microsoft Visual Studio `version`\\VC\\Redist\\`platform`\\`library`\\에서 특정 Visual C\+\+ DLL을 복사하고 대상 컴퓨터의 같은 폴더에 응용 프로그램 실행 파일로 설치합니다.  관리자 권한이 없는 사용자가 설치하려는 경우 또는 네트워크 공유에서 실행할 수 있는 응용 프로그램의 경우 이 배포 메서드를 사용할 수 있습니다.  
  
 배포에 재배포 가능 병합 모듈이 사용되거나 관리자 권한이 없는 사용자가 설치를 실행하면 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] DLL이 설치되지 않고 응용 프로그램이 실행되지 않습니다.  또한 사용자별로 설치할 수 있는 병합 모듈로 빌드된 응용 프로그램 설치 관리자는 시스템의 모든 사용자에게 영향을 주는 공유 위치에 라이브러리를 설치합니다.  로컬 배포를 사용하면 다른 사용자에게 영향을 주지 않거나 관리자 권한 없이도 특정 사용자 애플리케이션의 디렉터리에 필수 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] DLL을 설치할 수 있습니다.  서비스 효율성 문제가 발생할 수 있으므로 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 재배포 가능 DLL을 로컬 배포하지 않는 것이 좋습니다.  
  
 Visual C\+\+ 라이브러리를 잘못 배포하면 이러한 라이브러리에 의존하는 응용 프로그램을 실행할 때 런타임 오류가 발생할 수 있습니다.  운영 체제에서 응용 프로그램을 로드할 때 [LoadLibraryEx](http://go.microsoft.com/fwlink/?LinkId=132792)에 설명된 검색 순서를 사용합니다.  
  
## 정적 연결보다 나은 동적 연결  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 라이브러리를 재배포할 때는 정적 연결을 사용하지 않는 것이 좋습니다.  정적 연결은 응용 프로그램 성능을 상당히 개선하는 경우는 거의 없으면서도 서비스 제공 비용은 거의 항상 높아집니다.  예를 들어 업데이트로 보안이 향상된 라이브러리에 정적으로 연결된 응용 프로그램을 고려하면 응용 프로그램을 다시 컴파일 및 다시 배포하지 않는 한 그 응용 프로그램은 개선되지 않습니다.  대신에 라이브러리를 배포되는 경우에 항상 업데이트할 수 있도록 응용 프로그램을 종속되는 라이브러리에 동적으로 연결하는 것이 좋습니다.  
  
## 참고 항목  
 [데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Not in Build: Choosing a Deployment Strategy](http://msdn.microsoft.com/ko-kr/ecd632d8-063c-4028-b785-81bba045107b)   
 [Windows Installer Deployment Overview](http://msdn.microsoft.com/ko-kr/3ce4610a-b54f-404e-b650-42f4a55dfc3b)   
 [ClickOnce 보안 및 배포](../Topic/ClickOnce%20Security%20and%20Deployment.md)   
 [배포 예제](../ide/deployment-examples.md)