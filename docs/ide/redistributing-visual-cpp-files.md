---
title: Visual c + + 파일 재배포 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- application deployment [C++], file redistributing
- redistributing applications [C++]
- deploying applications [C++], file redistributing
- file redistribution [C++]
- redistributing applications [C++], about redistributing applications
ms.assetid: d201b2ce-36f1-44e5-a96c-0db81a1ba652
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e67ad87f1dce47f3d02dcbe907285cf0513a8ce9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="redistributing-visual-c-files"></a>Visual C++ 파일 재배포

> [!NOTE]
> 하기 때문에 여기 되어 Visual c + + 런타임 파일 중 하나의 다운로드를 찾고 있습니까? 로 이동는 [Microsoft](http://www.microsoft.com/) 웹 사이트를 입력 하 고 **Visual c + + 재배포 가능 패키지** 검색 상자에 있습니다. 다운로드 하 여 컴퓨터 (예: x64 64 비트 Windows를 실행 하는 경우)의 아키텍처 및 Visual c + + (예: 2015) 해야 하는 버전에 대 한 재배포 가능 패키지를 설치 합니다.

응용 프로그램을 배포할 때 이 응용 프로그램을 지원하는 데 필요한 파일도 배포해야 합니다. Microsoft에서 이러한 파일을 제공하는 경우 파일을 다시 배포할 수 있는지 여부를 확인합니다. Visual Studio 사용 약관을 검토 하려면 IDE에서 Microsoft Visual Studio 정보 대화 상자에서 사용권 계약 링크를 참조 하거나 다운로드는 [Microsoft 소프트웨어 사용 조건](http://go.microsoft.com/fwlink/p/?LinkId=831114) 파일입니다. 일부 버전의 Visual Studio에 대 한 Microsoft 소프트웨어 사용 조건의 "배포 가능 코드" 섹션에서 참조 하는 "REDIST 목록"을 참조 하십시오 [Microsoft Visual Studio 2017 및 Microsoft Visual Studio 2017 용 배포 가능 코드 SDK (포함 유틸리티 및 BuildServer 파일)](http://go.microsoft.com/fwlink/p/?LinkId=823098), Visual Studio 2015에 대 한 참조 또는 [Microsoft Visual Studio 2015 및 Microsoft Visual Studio 2015 SDK 용 배포 가능 코드](http://go.microsoft.com/fwlink/p/?LinkId=523763)합니다. 재배포 가능 파일에 대 한 자세한 내용은 참조 [재배포할 Dll 확인](../ide/determining-which-dlls-to-redistribute.md) 및 [배포 예제](../ide/deployment-examples.md)합니다.

재배포 가능한 Visual c + + 파일을 배포 하려면 Visual c + + 재배포 가능 패키지를 사용할 수 있습니다 (VCRedist\_x86.exe, VCRedist\_x64.exe, 또는 VCRedist\_arm.exe) 하는 Visual Studio에 포함 됩니다. Visual Studio 2017에 이러한 파일에에서 있습니다 Program Files [(x86)]\\Microsoft Visual Studio\\2017\\_edition_\\VC\\Redist\\ MSVC\\_lib 버전_ 폴더를 여기서 _edition_ 가 설치 된 Visual Studio 버전 및 _lib 버전_ 의 버전이 재배포 하는 라이브러리입니다. Visual Studio 2015에서 이러한 파일에서 Visual Studio 설치 디렉터리에에서 있습니다 Program Files [(x86)] \Microsoft Visual Studio *버전*\VC\redist\\*로캘* \\. Visual Studio 2017에는 Program Files [(x86)]에서 찾을 수 있는 재배포 가능 병합 모듈 (.msm 파일)를 사용 하는 또 다른 옵션은\\Microsoft Visual Studio\\2017\\_edition_ \\ VC\\Redist\\MSVC\\_lib 버전_\\MergeModules\\ 폴더입니다. Visual Studio 2015에서 Program Files [(x86)] \common 모듈에서에서 찾을 수 있습니다\\합니다. 재배포 가능한 Visual c + + Dll을 직접 설치할 수 이기도 *응용 프로그램 로컬 폴더*, 응용 프로그램 실행 파일이 포함 된 폴더입니다. 서비스 편의를 위해 이 설치 위치를 사용하지 않는 것이 좋습니다.

Visual C++ 재배포 가능 패키지는 모든 Visual C++ 라이브러리를 설치하고 등록합니다. 재배포 가능 패키지를 사용하는 경우 응용 프로그램 설치의 필수 구성 요소로 대상 시스템에서 실행되도록 설정해야 합니다. Visual C++ 라이브러리의 자동 업데이트를 사용하기 때문에 이러한 배포 패키지를 사용하는 것이 좋습니다. 이러한 패키지를 사용 하는 방법에 대 한 예제를 보려면 [연습: Visual c + + 재배포 가능 패키지는 Visual c + + 응용 프로그램 사용 하 여 배포](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md)합니다.

각 Visual C++ 재배포 가능 패키지는 컴퓨터에 최신 버전이 있는지 여부를 확인합니다. 최신 버전이 있는 경우 패키지가 설치되지 않습니다. Visual Studio 2015부터 재배포 가능 패키지에 설치 실패를 알리는 오류 메시지가 표시됩니다. 사용 하 여 패키지가 실행 될 경우는 **/quiet** 플래그를 오류 메시지가 표시 됩니다. 어떤 경우든 오류가 Microsoft Installer에 기록되며, 오류 결과가 호출자에게 반환됩니다. Visual Studio 2015 패키지부터 최신 버전이 설치 되어 있는지 확인 하려면 레지스트리를 확인 하 여이 오류를 방지할 수 있습니다. 현재 설치 된 버전은 HKEY_LOCAL_MACHINE\SOFTWARE [\Wow6432Node] \Microsoft\VisualStudio에 저장 된\\_vs 버전_\VC\Runtimes\\{x86 | x64 | ARM} 키 여기서 _vs 버전_ Visual Studio에 대 한 버전 번호입니다 (Visual Studio 2015와 Visual Studio 2017 년에 대 한 14.0 재배포 가능 패키지 업데이트 2017 2015 버전와 이진 호환 이므로), 키가 고 ARM, x86 또는 x64 플랫폼에 대해 vcredist 설치 된 버전에 따라 합니다. (설치 된 x86 버전을 보려면 RegEdit을 사용 하는 경우 Wow6432Node 하위 키 아래에서 확인 하지 않아도 됩니다. x64 패키지 플랫폼.) 버전 번호 REG_SZ 문자열 값에 저장 됩니다 **버전** 및 집합에도 **주요**, **부**, **Bld**, 및 **Rbld** REG_DWORD 값입니다. 설치 중에 오류를 방지 하려면 현재 설치 된 버전 보다 최신 경우 재배포 가능 패키지 설치를 건너뜁니다 해야 합니다.

Visual C++ DLL이 들어 있는 병합 모듈을 사용하는 경우 응용 프로그램을 배포하는 데 사용할 Windows Installer 패키지(또는 유사한 설치 패키지)에 해당 모듈을 포함해야 합니다. 자세한 내용은 참조 [하 여 사용 하 여 병합 모듈을 재배포](../ide/redistributing-components-by-using-merge-modules.md)합니다. 예를 들어 참조 [연습: 설치 프로젝트는 Visual c + + 응용 프로그램 사용 하 여 배포](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md), 설치 패키지를 만들려면 InstallShield Limited Edition을 사용 하는 방법도 설명입니다.

## <a name="potential-run-time-errors"></a>발생 가능한 런타임 오류

Windows Dll 응용 프로그램에 필요한 재배포 가능 라이브러리 중 하나를 찾을 수 없습니다, 다음과 유사한 메시지가 표시 될 수 있습니다: "이 응용이 프로그램 때문에 시작 하지 못했습니다 *라이브러리*.dll을 찾을 수 없습니다. 응용 프로그램을 다시 설치이 문제를 해결 합니다. "

이러한 종류의 오류를 해결 하려면 응용 프로그램 설치 관리자 올바르게 빌드되는지 및 재배포 가능 라이브러리가 대상 시스템에 올바르게 배포 되어 있는지 확인 합니다. 자세한 내용은 참조 [Visual c + + 응용 프로그램의 종속성 이해](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)합니다.

## <a name="related-topics"></a>관련 항목

|제목|설명|
|-----------|-----------------|
|[병합 모듈을 사용 하 여 재배포](../ide/redistributing-components-by-using-merge-modules.md)|Visual c + + 런타임 라이브러리를 공유 Dll로 %windir%\system32\ 폴더에 설치 하려면 Visual c + + 재배포 가능 병합 모듈을 사용 하는 방법을 설명 합니다.|
|[Visual C++ ActiveX 컨트롤 재배포](../ide/redistributing-visual-cpp-activex-controls.md)|ActiveX 컨트롤을 사용하는 응용 프로그램을 재배포하는 방법에 대해 설명합니다.|
|[데이터베이스 지원 파일 재배포](../ide/redistributing-database-support-files.md)|DAO(Data Access Objects) 및 Microsoft Data Access SDK에 포함된 데이터베이스 기술을 위한 지원 파일을 다시 배포하는 방법에 대해 설명합니다.|
|[MFC 라이브러리 재배포](../ide/redistributing-the-mfc-library.md)|MFC를 사용하는 응용 프로그램을 재배포하는 방법에 대해 설명합니다.|
|[ATL 응용 프로그램 재배포](../ide/redistributing-an-atl-application.md)|ATL을 사용하는 응용 프로그램을 재배포하는 방법에 대해 설명합니다. Visual Studio 2012부터 ATL에 대한 재배포 가능 라이브러리가 필요하지 않습니다.|
|[배포 예제](../ide/deployment-examples.md)|Visual C++ 응용 프로그램을 배포하는 방법을 보여 주는 예제에 대한 링크입니다.|
|[데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)|Visual C++ 배포 개념과 기술을 소개합니다.|