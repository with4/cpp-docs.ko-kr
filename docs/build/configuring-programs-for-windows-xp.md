---
title: "Windows XP에 대 한 프로그램을 구성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ff80109c1f3a5e03ecb85406cdaea24804f96783
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2018
---
# <a name="configuring-programs-for-windows-xp"></a>Windows XP 용 프로그램 구성
Visual Studio는 여러 플랫폼 도구 집합을 지원 하므로 운영 체제 및 런타임 라이브러리 기본 도구 집합에서 지원 되지 않는 대상 수 있습니다. 예를 들어 플랫폼 도구 집합을 전환 하 여 있습니다 사용할 수는 C + + 11, C + + 14, 및 Visual Studio에서 Visual c + + 컴파일러에서 지 원하는 향상 된 C + + 17 언어를 대상으로 하는 앱을 만드는 [!INCLUDE[winxp](../build/includes/winxp_md.md)] 및 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]합니다. 또한 이전 플랫폼 도구 집합을 사용 하 여 이진 호환 레거시 코드를 유지 관리할 수 있으며 Visual Studio IDE의 최신 기능도 활용할 수 있습니다.  
  
> [!NOTE]
>  사용 중인 경우 [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)]를 설치 해야 [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] 업데이트 4에 대 한 플랫폼 도구 집합 지원을 추가 하려면 [!INCLUDE[winxp](../build/includes/winxp_md.md)] 및 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]합니다. 다운로드 하 여의 복사본을 설치 [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] 업데이트 4, 참조 [Microsoft Visual Studio Express 2012 for Windows Desktop](http://go.microsoft.com/fwlink/p/?linkid=265464) Microsoft 다운로드 센터에서. 다음 설치 [Visual Studio 2012 업데이트 4](http://go.microsoft.com/fwlink/p/?linkid=335900) v110_xp 플랫폼 도구 집합을 얻으려고 합니다. 설치 후에는 Windows 업데이트에서 최신 소프트웨어 업데이트를 받습니다.  
  
## <a name="windows-xp-targeting-experience"></a>Windows XP 대상 환경  
 Visual Studio에 포함 된 Windows XP 플랫폼 도구 집합의 버전이 [!INCLUDE[win7](../build/includes/win7_md.md)] SDK에 포함 된 [!INCLUDE[vs_dev10_long](../build/includes/vs_dev10_long_md.md)], 이지만 현재 c + + 컴파일러를 사용 합니다. 또한 이 도구 집합은 프로젝트 속성을 적합한 기본값(예: 하위 수준 대상 지정을 위한 호환 링커의 사양)으로 구성합니다. Windows XP 플랫폼 도구 집합을 사용 하 여 만들어진 데스크톱 앱에서 실행 되는 창만 [!INCLUDE[winxp](../build/includes/winxp_md.md)] 및 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], 되지만 최신 Windows 운영 체제에서 해당 앱을 실행할 수도 있습니다.  
  
#### <a name="to-target-windows-xp"></a>Windows XP를 대상으로 지정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.  
  
2.  에 **속성 페이지** 대화 상자의 프로젝트에 대 한 **구성 속성**, **일반**로 설정 된 **플랫폼 도구 집합** 속성을 원하는 Windows XP 도구 집합입니다. 예를 들어 선택 **Visual Studio 2015-Windows XP (v140_xp)** 코드를 만드는 [!INCLUDE[winxp](../build/includes/winxp_md.md)] 및 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] Microsoft Visual c + + 2015 컴파일러를 사용 하 여 합니다.  
  
### <a name="c-runtime-support"></a>C++ 런타임 지원  
 Windows XP 플랫폼 도구 집합, C 런타임 라이브러리 (CRT), c + + 표준 라이브러리, 라이브러리 ATL (액티브 템플릿), 동시성 런타임 라이브러리 (ConCRT), 라이브러리 PPL (병렬 패턴), MFC Microsoft Foundation Class 라이브러리 (), 및 c + + AMP (c + +와 함께 Accelerated Massive 프로그래밍) 라이브러리에 대 한 런타임 지원이 포함 되어 [!INCLUDE[winxp](../build/includes/winxp_md.md)] 및 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]합니다. 이러한 운영 체제에 대 한 지원 되는 최소 버전은 [!INCLUDE[winxp](../build/includes/winxp_md.md)] x86, 서비스 팩 3 (SP3) [!INCLUDE[winxp](../build/includes/winxp_md.md)] x64에 대 한 서비스 팩 2 (SP2) 및 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] x86 및 x64 모두에 대 한 서비스 팩 2 (SP2).  
  
 이러한 라이브러리는 대상에 따라 Visual Studio가 설치 된 플랫폼 도구 집합에서 지원 됩니다.  
  
|라이브러리|Windows 데스크톱 앱을 대상으로 하는 기본 플랫폼 도구 집합|[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 앱을 대상으로 하는 기본 플랫폼 도구 집합|[!INCLUDE[winxp](../build/includes/winxp_md.md)], [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]을 대상으로 하는 Windows XP 플랫폼 도구 집합|  
|-------------|-------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|  
|CRT|X|X|X|  
|C++ 표준 라이브러리|X|X|X|  
|ATL|X|X|X|  
|ConCRT/PPL|X|X|X|  
|MFC|X||X|  
|C++ AMP|X|X||  
  
> [!NOTE]
>  C++/CLI로 작성되며 .NET Framework 4를 대상으로 하는 앱은 [!INCLUDE[winxp](../build/includes/winxp_md.md)] 및 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]에서 실행됩니다.  
  
### <a name="differences-between-the-toolsets"></a>도구 집합 간의 차이점  
 플랫폼 및 라이브러리 지원의 차이로 인해 Windows XP 플랫폼 도구 집합을 사용 하는 앱의 개발 환경은 기본 Visual Studio 플랫폼 도구 집합을 사용 하는 앱 처럼 완전 하지 않습니다.  
  
-   **C + + 언어 기능**  
  
     구현 되는 c + + 언어 기능만 [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] v110_xp 플랫폼 도구 집합을 사용 하는 앱에서 지원 됩니다. 구현 되는 c + + 언어 기능만 [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] v120_xp 플랫폼 도구 집합을 사용 하는 앱에서 지원 됩니다. 이전 플랫폼 도구 집합을 사용 하 여 빌드할 때 visual Studio에서 해당 컴파일러를 사용 합니다. 해당 버전의 컴파일러에서 구현 되는 추가 c + + 언어 기능을 활용 하는 최신 Windows XP 플랫폼 도구 집합을 사용 합니다.  
  
-   **원격 디버깅**  
  
     Visual Studio 용 원격 도구에 원격 디버깅을 지원 하지 않습니다 [!INCLUDE[winxp](../build/includes/winxp_md.md)] 또는 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]합니다. 실행 되는 응용 프로그램을 디버깅 하려면 [!INCLUDE[winxp](../build/includes/winxp_md.md)] 또는 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], 로컬 또는 원격으로 디버깅 하려면 이전 버전의 Visual Studio에서 디버거를 사용할 수 있습니다. 이러한 디버그 환경은 플랫폼 도구 집합의 런타임 대상이지만 원격 디버깅 대상은 아닌 Windows Vista에서 앱을 디버그하는 환경과 비슷합니다.  
  
-   **정적 분석**  
  
     [!INCLUDE[win7](../build/includes/win7_md.md)] SDK의 SAL 주석과 런타임 라이브러리는 호환되지 않으므로 Windows XP 플랫폼 도구 집합은 정적 분석을 지원하지 않습니다. [!INCLUDE[winxp](../build/includes/winxp_md.md)] 또는 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]을 지원하는 앱에서 정적 분석을 수행하려면 분석을 수행할 기본 플랫폼 도구 집합을 대상으로 하도록 솔루션을 일시적으로 전환했다가 다시 Windows XP 플랫폼 도구 집합으로 전환해 앱을 빌드할 수 있습니다.  
  
-   **DirectX 그래픽 디버깅**  
  
     그래픽 디버거는 Direct3D 9 API를 지원하지 않으므로 [!INCLUDE[winxp](../build/includes/winxp_md.md)] 또는 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]에서 Direct3D를 사용하는 앱을 디버그하는 데 사용할 수는 없습니다. 그러나 앱이 Direrct3D 10 또는 Direct3D 11 API를 사용하는 대체 렌더러를 구현하는 경우 그래픽 디버거를 사용하여 해당 API 사용 시 발생하는 문제를 진단할 수 있습니다.  
  
-   **HLSL 빌드**  
  
     Windows XP 도구 집합은 기본적으로 HSLS 소스 코드 파일을 컴파일하지 않습니다. HLSL 파일을 컴파일하려면 2010년 6월 DirectX SDK를 다운로드하여 설치한 다음 해당 SDK를 포함하도록 프로젝트의 VC 디렉터리를 설정합니다. 자세한 내용은 참조는 "DirectX SDK를 등록 하지 않습니다 포함/라이브러리 경로를 Visual Studio 2010"의 섹션은 [2010 년 6 월 DirectX SDK 다운로드 페이지](http://www.microsoft.com/download/details.aspx?displaylang=en&id=6812)합니다.