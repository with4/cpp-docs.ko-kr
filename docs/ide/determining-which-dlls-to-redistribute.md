---
title: "재배포할 Dll 확인 | Microsoft Docs"
ms.custom: 
ms.date: 09/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- redistributing DLLs
- DLLs [C++], redistributing
- dependencies [C++], application deployment and
- application deployment [C++], DLL redistribution
- deploying applications [C++], DLL redistribution
ms.assetid: f7a2cb42-fb48-42ab-abd2-b35e2fd5601a
caps.latest.revision: "31"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ae47ec92ecea46aba5f0e1bf144a34fd5532af9d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="determining-which-dlls-to-redistribute"></a>재배포할 DLL 확인

Visual Studio에서 제공 하는 라이브러리 Dll을 사용 하는 응용 프로그램을 빌드할 때 응용 프로그램의 사용자는 자신의 응용 프로그램을 실행할 컴퓨터에 이러한 Dll도 있어야 합니다. 대부분의 사용자는 Visual Studio가 설치되어 있지 않기 때문에 이러한 DLL을 제공해야 합니다. Visual Studio에서는 이러한 Dll로 제공 *재배포 가능 파일* 있는 응용 프로그램 설치 관리자에 포함할 수 있습니다.

독립 실행형으로 사용할 수 있는 설치 관리자와 재배포 가능 Dll을 포함 하도록 쉽게 *재배포 가능 패키지*합니다. 이들은 중앙 배포를 사용 하 여 사용자의 컴퓨터에 재배포 가능 파일을 설치 하는 아키텍처별 실행 파일입니다. 예를 들어 vcredist\_x86.exe x86 32 비트 라이브러리를 설치 합니다. 컴퓨터, vcredist\_x64.exe x64에 대 한 32 비트 및 64 비트 라이브러리를 설치 합니다. 컴퓨터 및 vcredist\_ARM.exe ARM에 대 한 라이브러리 설치 컴퓨터입니다. 이러한 라이브러리를 독립적으로 업데이트 하려면 Microsoft Windows Update 서비스를 사용할 수 있는 중앙 배포를 권장 합니다. Visual Studio 설치에 대 한 복사, 외에도 현재 재배포 가능 패키지는에서 다운로드할 수 있는 [VisualStudio.com/Downloads](https://www.visualstudio.com/downloads/) 다른 도구 및 프레임 워크 섹션에 있습니다.

배포 재배포 가능 패키지의 주 버전 번호는 응용 프로그램을 만드는 데 사용 하는 Visual Studio 도구 집합의 버전과 일치 해야 합니다. Visual Studio 2017 및 Visual Studio 2015 호환 도구 집합 버전 번호가, 즉는 Visual Studio 2017 2015 도구 집합을 사용 하 여 빌드한 앱에서 재배포 가능 파일을 사용할 수 있습니다. 호환 될 수 있습니다, 2017 도구 집합을 사용 하 여 만든 앱의 2015 재배포 가능 파일을 사용 하 여 지원 하지 않습니다. 동일 하거나 도구 집합 버전 보다 최신 재배포 가능 패키지를 사용 하 여 지원 합니다. 최신 지원 되는 재배포 가능 패키지가 이전 도구 집합에 대 한 링크를 참조 [최신 지원 Visual c + + 다운로드](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads)합니다. 검색 하 여 특정 이전 버전의 재배포 가능 패키지를 찾을 수 있습니다는 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/p/?LinkId=158431) "Visual c + + 재배포 가능 패키지"에 대 한 합니다.

설치 관리자와 재배포 가능 Dll을 포함 하는 다른 방법은 사용 하는 것 *병합 모듈*합니다. 이러한 Microsoft Installer 모듈에 포함 되어 있고 응용 프로그램 설치 관리자에서 설치 합니다. 재배포 가능 Dll에 대 한 병합 모듈에서 Visual Studio 설치 디렉터리에서 발견 되 \\VC\\Redist\MSVC\\*버전*\\MergeModules\\ . 이전 버전의 Visual Studio에서는 이러한 파일을 찾을 수에서 프로그램 \\Program Files 또는 \\Program Files (x86) 디렉터리 공용 파일의\\병합 모듈을 하위 디렉터리입니다. 이러한 파일의 사용에 대 한 자세한 내용은 참조 [병합 모듈을 사용 하 여 구성 요소 재배포](../ide/redistributing-components-by-using-merge-modules.md)합니다.

개별 재배포 가능 Dll은 Visual Studio의 설치에서도 포함 됩니다. 기본적으로 Visual Studio 설치 디렉터리에 설치 되는 \\VC\\Redist\\MSVC\\*버전* 폴더입니다. *버전* 번호는 하나의 공통 집합이 재배포 가능 파일의 다른 부 빌드 번호를 나타낼 수 있습니다. 라이브러리 DLL 파일, 재배포 가능 패키지 또는 이러한 디렉터리에 병합 모듈의 최신 버전을 사용 합니다. 응용 프로그램과 같은 디렉터리에 설치 하 여 로컬 배포에 대 한 이러한 라이브러리를 사용할 수 있습니다. 로컬 배포를 사용 만들므로 하면 배포 된 응용 프로그램에 업데이트를 제공 하는 일을 담당 합니다. 중앙 배포-재배포 가능 패키지를 사용 하는 것이 좋습니다.

응용 프로그램과 함께 다시 배포해야 하는 DLL을 결정하려면 응용 프로그램에서 사용되는 DLL 목록을 수집합니다. 이러한 라이브러리 입력 링커로 가져올 때 일반적으로 나열 됩니다. 특정 라이브러리 vcruntime 및 유니버설 C 런타임 라이브러리 (UCRT), 예: 기본적으로 포함 됩니다. 응용 프로그램 또는 해당 종속성 중 하나가 DLL을 동적으로 로드 하려면 LoadLibrary를 사용 하 여, 해당 DLL 링커에 대 한 입력에 나열 되지 않을 수 있습니다. 에 설명 된 대로 Dependency Walker (depends.exe) 응용 프로그램을 실행 하는 동적으로 로드 된 Dll 목록을 수집 하는 한 가지 방법은입니다 [Visual c + + 응용 프로그램의 종속성 이해](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)합니다. 그러나이 도구는 오래 된 하 고 특정 Dll을 찾을 수 없다고 보고할 수 있습니다.

종속성 목록이 있는 경우 비교 "REDIST 목록" 재배포 가능 Dll의 "배포 가능 코드 파일" 섹션에서 참조 되는 또는 Microsoft Visual Studio 설치 디렉터리에서 찾은 Redist.txt 파일에서 연결 된 목록에 Visual Studio에 대 한 Microsoft 소프트웨어 사용 조건. Visual Studio 2017 참조 [Microsoft Visual Studio 2017 (포함 유틸리티, 확장성 및 BuildServer 파일) 용 배포 가능 코드](http://go.microsoft.com/fwlink/?LinkId=823098)합니다. Visual Studio 2015에 대 한 참조 [Microsoft Visual Studio 2015 및 Microsoft Visual Studio 2015 SDK (포함 유틸리티 및 BuildServer 파일)에 대 한 배포 가능한 코드](http://go.microsoft.com/fwlink/?LinkId=799794)합니다. Visual Studio 2013에 대 한 목록 중인 사용 가능한 온라인 [Microsoft Visual Studio 2013 및 Microsoft Visual Studio 2013 SDK 용 배포 가능 코드](http://go.microsoft.com/fwlink/p/?LinkId=313603)합니다.

Visual Studio 2015 이전 버전 Visual Studio에서는 C 런타임 라이브러리 (CRT) msvc에서 재배포 가능 DLL로 포함 되어*버전*.dll입니다. Visual Studio 2015부터 CRT에서 함수 UCRT 및 vcruntime 개로 리팩터링 되었습니다. UCRT는 이제 Windows 10에서 Windows 업데이트에 의해 관리 되는 시스템 구성 요소입니다. 모든 Windows 10 운영 체제에서 제공 됩니다. 이전 운영 체제에 응용 프로그램을 배포 하려면도 UCRT를 재배포 합니다. UCRT의 초기 버전을만 설치 되는 운영 체제에서 Windows 10 이전, Visual Studio 재배포 가능 파일에 포함 UCRT의 버전이 이미 설치 된 경우만 합니다. Microsoft System 업데이트 패키지로 하위 시스템을 위한 UCRT의 설치 가능한 버전을 참조 하십시오. [Windows 10 유니버설 C 런타임](https://www.microsoft.com/en-us/download/details.aspx?id=48234) Microsoft 다운로드 센터에서.

Visual Studio에 포함된 모든 파일을 다시 배포할 수는 없습니다. Redist.txt 또는 온라인 "REDIST 목록"에 지정된 파일만 다시 배포할 수 있습니다. 디버그 버전의 응용 프로그램 및 다양한 Visual C++ 디버그 DLL은 다시 배포할 수 없습니다. 자세한 내용은 참조 [배포 방법 선택](../ide/choosing-a-deployment-method.md)합니다.

다음 표에서는 응용 프로그램에서 사용될 수 있는 일부 Visual C++ DLL에 대해 설명합니다.

|Visual C++ 라이브러리|설명|적용 대상|
|--------------------------|-----------------|----------------|
|vcruntime*버전*.dll|네이티브 코드에 대 한 런타임 라이브러리입니다.|일반 C 및 c + + 언어 startup 및 termination 서비스를 사용 하는 응용 프로그램입니다.|
|vccorlib*버전*.dll|관리 코드에 대 한 런타임 라이브러리입니다.|관리 코드에 대 한 c + + 언어 서비스를 사용 하는 응용 프로그램입니다.|
|msvcp*버전*.dll|네이티브 코드에 대 한 c + + 표준 라이브러리|사용 하는 응용 프로그램의 [c + + 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)합니다.|
|concrt*버전*.dll|네이티브 코드에 대 한 동시성 런타임 라이브러리입니다.|사용 하는 응용 프로그램의 [동시성 런타임](../parallel/concrt/concurrency-runtime.md)합니다.|
|mfc*버전*.dll|MFC(Microsoft Foundation Class) 라이브러리|사용 하는 응용 프로그램의 [MFC 라이브러리](../mfc/mfc-desktop-applications.md)합니다.|
|mfc*버전* *언어*.dll|Microsoft Foundation Class 라이브러리 리소스 (MFC).|MFC에 대 한 특정 언어 리소스를 사용 하는 응용 프로그램입니다.|
|mfc*버전*u.dll|유니코드를 지원하는 MFC 라이브러리|사용 하는 응용 프로그램의 [MFC 라이브러리](../mfc/mfc-desktop-applications.md) 및 유니코드를 지원 해야 합니다.|
|mfcmifc80.dll|MFC 관리되는 인터페이스 라이브러리|사용 하는 응용 프로그램의 [MFC 라이브러리](../mfc/mfc-desktop-applications.md) 와 [Windows Forms 컨트롤](/dotnet/framework/winforms/controls/index)합니다.|
|mfcm*버전*.dll|MFC 관리되는 라이브러리|사용 하는 응용 프로그램의 [MFC 라이브러리](../mfc/mfc-desktop-applications.md) 와 [Windows Forms 컨트롤](/dotnet/framework/winforms/controls/index)합니다.|
|mfcm*버전*u.dll|유니코드를 지원하는 MFC 관리되는 라이브러리|사용 하는 응용 프로그램의 [MFC 라이브러리](../mfc/mfc-desktop-applications.md) 와 [Windows Forms 컨트롤](/dotnet/framework/winforms/controls/index) 및 유니코드를 지원 해야 합니다.|
|vcamp*버전*.dll|네이티브 코드에 대 한 AMP 라이브러리입니다.|사용 하는 응용 프로그램의 [c + + AMP 라이브러리](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md) 코드입니다.|
|vcomp*버전*.dll|네이티브 코드에 대 한 OpenMP 라이브러리입니다.|사용 하는 응용 프로그램의 [c + +의 OpenMP 라이브러리](../parallel/openmp/openmp-in-visual-cpp.md) 코드입니다.|

> [!NOTE]
> 더 이상 Active Template Library를 별도의 DLL로 재배포할 필요가 없습니다. 해당 기능은 헤더 및 정적 라이브러리로 이동되었습니다.

응용 프로그램과 함께 이러한 Dll을 재배포 하는 방법에 대 한 자세한 내용은 참조 [Visual c + + 파일 재배포](../ide/redistributing-visual-cpp-files.md)합니다. 예제를 보려면 [배포 예제](../ide/deployment-examples.md)합니다.

일반적으로 시스템 DLL은 운영 체제의 일부이므로 재배포할 필요가 없습니다. 하지만 응용 프로그램이 여러 버전의 Microsoft 운영 체제에서 실행되는 경우와 같은 예외도 있을 수 있습니다. 이 경우 해당 사용 약관을 참조해야 합니다. 또한 Windows 업데이트, 서비스 팩 또는 Microsoft에서 제공하는 재배포 가능 패키지를 통해 업그레이드된 시스템 DLL을 가져오세요.

## <a name="see-also"></a>참고 항목

[배포 방법 선택](../ide/choosing-a-deployment-method.md)

[데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)
