---
title: "Visual C++ 파일 재배포 | Microsoft Docs"
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
  - "응용 프로그램 배포[C++], 파일 재배포"
  - "응용 프로그램 배포[C++], 파일 재배포"
  - "파일 재배포[C++]"
  - "응용 프로그램 재배포[C++]"
  - "응용 프로그램 재배포[C++], 응용 프로그램 재배포 정보"
ms.assetid: d201b2ce-36f1-44e5-a96c-0db81a1ba652
caps.latest.revision: 50
caps.handback.revision: 48
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Visual C++ 파일 재배포
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

응용 프로그램을 배포할 때 이 응용 프로그램을 지원하는 데 필요한 파일도 배포해야 합니다.  Microsoft에서 이러한 파일을 제공하는 경우 파일을 다시 배포할 수 있는지 여부를 확인합니다.  Microsoft 소프트웨어 사용 약관을 검토하려면 Visual Studio가 설치된 디렉터리 또는 Visual Studio 설치 미디어에 있는 License.htm을 참조하십시오.  특정 버전의 Visual Studio에 대한 Microsoft 소프트웨어 사용 약관의 "배포 가능 코드" 단원에 언급된 "REDIST 목록"을 보려면 Microsoft 웹 사이트에서 [Microsoft Visual Studio 2013 및 Microsoft Visual Studio 2013 SDK용 재배포 가능 코드](http://go.microsoft.com/fwlink/p/?LinkId=313603)를 참조하세요.  재배포 가능 파일에 대한 자세한 내용은 [재배포할 DLL 확인](../ide/determining-which-dlls-to-redistribute.md) 및 [배포 예제](../ide/deployment-examples.md)를 참조하세요.  
  
 재배포 가능한 Visual C\+\+ 파일을 배포하려면 Visual Studio에 포함된 Visual C\+\+ 재배포 가능 패키지\(VCRedist\_x86.exe, VCRedist\_x64.exe 또는 VCRedist\_arm.exe\)를 사용할 수 있습니다.  이러한 파일은 Program Files \[\(x86\)\]\\Microsoft Visual Studio *version*\\VC\\redist\\*locale*\\의 Visual Studio 설치 디렉터리 아래에 있습니다.  다른 옵션은 Program Files \[\(x86\)\]\\Common Files\\Merge Modules\\에 있는 재배포 가능 병합 모듈\(.msm 파일\)을 사용하는 것입니다.  응용 프로그램 실행 파일이 들어 있는 폴더인 *응용 프로그램 로컬 폴더*에 재배포 가능한 Visual C\+\+ DLL을 직접 설치할 수도 있습니다.  서비스 편의를 위해 이 설치 위치를 사용하지 않는 것이 좋습니다.  
  
 Visual C\+\+ 재배포 가능 패키지는 모든 Visual C\+\+ 라이브러리를 설치하고 등록합니다.  재배포 가능 패키지를 사용하는 경우 응용 프로그램 설치의 필수 구성 요소로 대상 시스템에서 실행되도록 설정해야 합니다.  Visual C\+\+ 라이브러리의 자동 업데이트를 사용하기 때문에 이러한 배포 패키지를 사용하는 것이 좋습니다.  이러한 패키지를 사용하는 방법에 대한 예제는 [연습: Visual C\+\+ 재배포 가능 패키지를 사용하여 Visual C\+\+ 응용 프로그램 배포](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md)를 참조하세요.  
  
 각 Visual C\+\+ 재배포 가능 패키지는 컴퓨터에 최신 버전이 있는지 여부를 확인합니다.  최신 버전이 있는 경우 패키지가 설치되지 않습니다.  Visual Studio 2015부터 재배포 가능 패키지에 설치 실패를 알리는 오류 메시지가 표시됩니다.  **\/quiet** 플래그를 사용하여 패키지를 실행하는 경우 오류 메시지가 표시되지 않습니다.  어떤 경우든 오류가 Microsoft Installer에 기록되며, 오류 결과가 호출자에게 반환됩니다.  Visual Studio 2015 패키지부터 레지스트리 값에서 최신 버전이 설치되어 있는지 확인할 수 있습니다.  현재 설치된 버전은 HKEY\_LOCAL\_MACHINE\\SOFTWARE\[\\Wow6432Node\]\\Microsoft\\DevDiv\\vc\\Servicing\\14.0\\RuntimeMinimum에 버전 키의 REG\_SZ 값으로 저장됩니다.  현재 설치된 버전이 최신인 경우 재배포 가능 패키지를 설치하지 않아도 됩니다.  
  
 Visual C\+\+ DLL이 들어 있는 병합 모듈을 사용하는 경우 응용 프로그램을 배포하는 데 사용할 Windows Installer 패키지\(또는 유사한 설치 패키지\)에 해당 모듈을 포함해야 합니다.  자세한 내용은 [병합 모듈을 사용하여 재배포](../ide/redistributing-components-by-using-merge-modules.md)를 참조하세요.  예제는 [연습: 설치 프로젝트를 사용하여 Visual C\+\+ 응용 프로그램 배포](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)를 참조하세요. 여기에서는 InstallShield Limited Edition을 사용하여 설치 패키지를 만드는 방법도 보여 줍니다.  
  
## 발생 가능한 런타임 오류  
 Visual C\+\+ 라이브러리 DLL에 연결할 수 없고 Windows에서 응용 프로그램에 대해 DLL을 로드할 수 없는 경우 다음 메시지가 표시될 수 있습니다. **MSVCR\<version number\>.dll을 찾을 수 없어 응용 프로그램을 시작하지 못했습니다. 응용 프로그램을 다시 설치하면 이 문제가 해결될 수 있습니다.**  
  
 이러한 종류의 오류를 해결하려면 응용 프로그램이 올바르게 빌드되었는지, Visual C\+\+ 라이브러리가 대상 시스템에 올바르게 배포되었는지 확인합니다.  자세한 내용은 [Visual C\+\+ 응용 프로그램의 종속성 이해](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)를 참조하세요.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[병합 모듈을 사용하여 재배포](../ide/redistributing-components-by-using-merge-modules.md)|[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 재배포 가능 병합 모듈을 사용하여 Visual C\+\+ 런타임 라이브러리를 공유 DLL로 %windir%\\system32\\ 폴더에 설치하는 방법에 대해 설명합니다.|  
|[Visual C\+\+ ActiveX 컨트롤 재배포](../ide/redistributing-visual-cpp-activex-controls.md)|ActiveX 컨트롤을 사용하는 응용 프로그램을 재배포하는 방법에 대해 설명합니다.|  
|[데이터베이스 지원 파일 재배포](../ide/redistributing-database-support-files.md)|DAO\(Data Access Objects\) 및 Microsoft Data Access SDK에 포함된 데이터베이스 기술을 위한 지원 파일을 다시 배포하는 방법에 대해 설명합니다.|  
|[MFC 라이브러리 재배포](../ide/redistributing-the-mfc-library.md)|MFC를 사용하는 응용 프로그램을 재배포하는 방법에 대해 설명합니다.|  
|[ATL 응용 프로그램 재배포](../ide/redistributing-an-atl-application.md)|ATL을 사용하는 응용 프로그램을 재배포하는 방법에 대해 설명합니다.  Visual Studio 2012부터 ATL에 대한 재배포 가능 라이브러리가 필요하지 않습니다.|  
|[배포 예제](../ide/deployment-examples.md)|Visual C\+\+ 응용 프로그램을 배포하는 방법을 보여 주는 예제에 대한 링크입니다.|  
|[데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)|Visual C\+\+ 배포 개념과 기술을 소개합니다.|