---
title: "배포 방법 선택 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- redistributing DLLs
- manifests [C++]
- DLLs [C++], redistributing
- side-by-side assemblies [C++]
- dynamic linking [C++]
- application deployment [C++], methods
- deploying applications [C++], methods
- static linking [C++]
- libraries [C++], application deployment issues
ms.assetid: fd8eb956-f4a0-4ffb-b401-328c73e66986
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9b30bea93163549373759ea8980650717d49bbac
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="choosing-a-deployment-method"></a>배포 방법 선택
Visual c + + 응용 프로그램은 독립적 이며 복사 명령을 사용 하 여 배포할 수 있습니다, 하지 않는 한 배포에 대 한 Windows Installer를 사용 하는 것이 좋습니다. Windows Installer는 설치, 수리 및 제거를 지원하고 응용 프로그램 파일, 종속성 및 레지스트리 항목의 원자성 업데이트도 지원합니다.  
  
> [!NOTE]
>  하지만 [ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) Visual c + + 네이티브 응용 프로그램에 대 한 배포는 Visual Studio에서 가능, 추가 단계가 필요 합니다. 자세한 내용은 [ClickOnce Deployment for Visual C++ Applications](../ide/clickonce-deployment-for-visual-cpp-applications.md)를 참조하세요.  
  
## <a name="visual-c-libraries-are-shared-dlls"></a>공유 DLL로서의 Visual C++ 라이브러리  
 Visual C++ 라이브러리는 Visual Studio 설치 관리자에 의해 %windir%\system32\ 디렉터리에 설치되기 때문에 종속된 Visual C++ 응용 프로그램을 개발하면 예상대로 실행됩니다. 그러나 Visual Studio가 설치되지 않은 컴퓨터에 응용 프로그램을 배포하려면 라이브러리가 응용 프로그램과 함께 해당 컴퓨터에 설치되어야 합니다.  
  
## <a name="redistributing-visual-c-libraries"></a>Visual C++ 라이브러리 재배포  
 배포 시 재배포 권한이 있는 모든 버전의 Visual C++ 라이브러리를 재배포할 수 있습니다. 배포 방법은 다음 세 가지가 있습니다.  
  
-   중앙 배포-재배포 가능 패키지를 사용 하 여 Visual c + + 라이브러리를 공유 Dll로 %windir%\system32 설치는\\합니다. (이 폴더에 설치하려면 관리자 권한이 필요합니다.) 대상 컴퓨터에 응용 프로그램을 설치하기 전에 재배포 가능 패키지를 실행하는 스크립트 또는 설치 프로그램을 만들 수 있습니다. 재배포 가능 패키지는 x86, x64 및 ARM 플랫폼(VCRedist_x86.exe, VCRedist_x64.exe 또는 VCRedist_arm.exe)에 사용할 수 있습니다. %ProgramFiles (x86) %\Microsoft Visual Studio에서에서 visual Studio는 이러한 패키지 `version`\VC\Redist\\`locale ID`\\합니다. 다운로드할 수도 있습니다는 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/p/?linkid=132793)합니다. (다운로드 센터에서 검색 상자를 사용 하 여 검색할는 "Visual c + + 재배포 가능 패키지 *Visual Studio 버전 및 업데이트*"과 일치 하는 응용 프로그램입니다. 예를 들어 응용 프로그램을 빌드하려면 Visual Studio 2015 업데이트 3을 사용한 경우 다음 검색에 대 한 "Visual c + + 재배포 가능 패키지 2015 업데이트 3"입니다.) 재배포 가능 패키지를 사용 하는 방법에 대 한 정보를 참조 하십시오. [연습: Visual c + + 재배포 가능 패키지는 Visual c + + 응용 프로그램 사용 하 여 배포](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md)합니다.  
  
-   중앙 배포-병합 모듈을 사용 하며 각 특정 Visual c + + 라이브러리를 공유 DLL로 %windir%\system32 설치\\합니다. (이 폴더에 설치하려면 관리자 권한이 필요합니다.) 병합 모듈은 응용 프로그램의 .msi 설치 관리자의 일부가 됩니다. Visual c + + 재배포 가능 병합 모듈이 \Program Files (x86) \common 모듈의에서 Visual Studio에 포함 됩니다\\합니다. 자세한 내용은 참조 [하 여 사용 하 여 병합 모듈을 재배포](../ide/redistributing-components-by-using-merge-modules.md)합니다.  
  
-   Visual Studio 설치에서 특정 Visual c + + Dll을 복사 하는 로컬 배포-\Program (x86) Files \Microsoft Visual Studio에서 일반적으로 `version`\VC\Redist\\`platform`\\`library`\—and 응용 프로그램 실행 파일과 같은 폴더에 있는 대상 컴퓨터에 설치 합니다. 관리자 권한이 없는 사용자가 설치하려는 경우 또는 네트워크 공유에서 실행할 수 있는 응용 프로그램의 경우 이 배포 메서드를 사용할 수 있습니다.  
  
 배포에 재배포 가능 병합 모듈이 사용 하는 경우 사용자가 관리자 권한이 없는 설치를 실행 하는 Visual c + + Dll이 설치 되지 않은 및 응용 프로그램은 실행 되지 않습니다. 또한 사용자별로 설치할 수 있는 병합 모듈로 빌드된 응용 프로그램 설치 관리자는 시스템의 모든 사용자에게 영향을 주는 공유 위치에 라이브러리를 설치합니다. 다른 사용자가에 영향을 주지 않거나 관리자 권한 없이도 특정 사용자 애플리케이션의 디렉터리에 필요한 Visual c + + Dll을 설치 하려면 로컬 배포를 사용할 수 있습니다. 이 서비스 효율성 문제가 발생할 수 있습니다, 때문에 Visual c + + 재배포 가능 Dll의 로컬 배포를 권장 하지는 않습니다.  
  
 Visual C++ 라이브러리를 잘못 배포하면 이러한 라이브러리에 의존하는 응용 프로그램을 실행할 때 런타임 오류가 발생할 수 있습니다. 에 설명 된 검색 순서는 운영 체제는 응용 프로그램 로드 될 때 사용 하 여 [LoadLibraryEx](http://go.microsoft.com/fwlink/p/?linkid=132792)  
  
## <a name="dynamic-linking-is-better-than-static-linking"></a>정적 연결보다 나은 동적 연결  
 Visual c + + 라이브러리를 재배포할 때는 정적 연결을 방지 하는 것이 좋습니다. 정적 연결은 응용 프로그램 성능을 상당히 개선하는 경우는 거의 없으면서도 서비스 제공 비용은 거의 항상 높아집니다. 예를 들어 업데이트로 보안이 향상된 라이브러리에 정적으로 연결된 응용 프로그램을 고려하면 응용 프로그램을 다시 컴파일 및 다시 배포하지 않는 한 그 응용 프로그램은 개선되지 않습니다. 대신에 라이브러리를 배포되는 경우에 항상 업데이트할 수 있도록 응용 프로그램을 종속되는 라이브러리에 동적으로 연결하는 것이 좋습니다.  
  
## <a name="see-also"></a>참고 항목  
 [데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [ClickOnce 보안 및 배포](/visualstudio/deployment/clickonce-security-and-deployment)   
 [배포 예제](../ide/deployment-examples.md)