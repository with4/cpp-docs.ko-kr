---
title: "Windows XP용 C++ 11 프로그램 구성 | Microsoft Docs"
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
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Windows XP용 C++ 11 프로그램 구성
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에서는 여러 플랫폼 도구 집합을 지원하므로 기본 도구 집합에서 지원하지 않는 운영 체제 및 런타임 라이브러리를 대상으로 지정할 수 있습니다.  예를 들어 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에서 구현되는 향상된 C\+\+11 언어, 컴파일러, 라이브러리 및 기타 기능을 사용하여 [!INCLUDE[winxp](../build/includes/winxp_md.md)] 및 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]을 대상으로 하는 앱을 만들 수 있습니다.  이전 플랫폼 도구 집합을 사용하면 이진 호환 레거시 코드를 유지 관리하는 동시에 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] IDE의 최신 기능도 활용할 수 있습니다.  
  
> [!NOTE]
>  [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] 및 [!INCLUDE[winxp](../build/includes/winxp_md.md)]에 대한 플랫폼 도구 집합 지원을 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]에 추가하려면 [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] 업데이트 4를 설치해야 합니다.  [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] 업데이트 4를 다운로드하여 설치하려면 Microsoft 다운로드 센터에서 [Microsoft Visual Studio Express 2012 for Windows Desktop](http://go.microsoft.com/fwlink/?LinkID=265464)을 참조하세요.  그런 다음 [Visual Studio 2012 업데이트 4](http://go.microsoft.com/fwlink/?LinkID=335900)를 설치하면 v110\_xp 플랫폼 도구 집합을 사용할 수 있습니다.  설치 후에는 Windows 업데이트에서 최신 소프트웨어 업데이트를 받습니다.  
  
## Windows XP 대상 환경  
 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에 포함되어 있는 Windows XP 플랫폼 도구 집합은 [!INCLUDE[win7](../build/includes/win7_md.md)]에 포함된 [!INCLUDE[vs_dev10_long](../build/includes/vs_dev10_long_md.md)] SDK의 한 버전이지만 최신 C\+\+ 컴파일러를 사용합니다.  또한 이 도구 집합은 프로젝트 속성을 적합한 기본값\(예: 하위 수준 대상 지정을 위한 호환 링커의 사양\)으로 구성합니다.  Windows XP 플랫폼 도구 집합을 사용하여 만든 Windows 데스크톱 앱만이 [!INCLUDE[winxp](../build/includes/winxp_md.md)] 및 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]에서 실행되지만 Windows Vista, [!INCLUDE[win7](../build/includes/win7_md.md)], [!INCLUDE[winsvr08](../build/includes/winsvr08_md.md)], [!INCLUDE[win8](../build/includes/win8_md.md)] 또는 [!INCLUDE[winserver8](../build/includes/winserver8_md.md)]와 같은 최신 운영 체제에서도 이러한 앱을 실행할 수 있습니다.  
  
#### Windows XP를 대상으로 지정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.  
  
2.  프로젝트 **속성 페이지** 대화 상자의 **구성 속성**, **일반**에서 **플랫폼 도구 집합** 속성을 원하는 Windows XP 도구 집합으로 설정합니다.  예를 들어 Microsoft Visual C\+\+ 2012 재배포 가능 라이브러리와 이진 호환되는 코드를 만들려면 **Visual Studio 2012 – Windows XP\(v110\_xp\)**를 선택합니다.  
  
### C\+\+ 런타임 지원  
 Windows XP 플랫폼 도구 집합과 함께 CRT\(C 런타임 라이브러리\), STL\(표준 템플릿 라이브러리\), ATL\(액티브 템플릿 라이브러리\), ConCRT\(동시성 런타임 라이브러리\), PPL\(병렬 패턴 라이브러리\), MFC\(Microsoft Foundation Class\) 라이브러리 및 C\+\+ AMP\(C\+\+ Accelerated Massive Programming\) 라이브러리에도 [!INCLUDE[winxp](../build/includes/winxp_md.md)] 및 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]에 대한 런타임 지원이 포함되어 있습니다.  이러한 운영 체제에 대해 지원되는 버전은 x86의 경우 [!INCLUDE[winxp](../build/includes/winxp_md.md)] SP3\(서비스 팩 3\), x64의 경우 [!INCLUDE[winxp](../build/includes/winxp_md.md)] SP2\(서비스 팩 2\)이며 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] SP2\(서비스 팩 2\)는 x86\/x64 둘 다에 지원됩니다.  
  
 이러한 라이브러리는 대상에 따라 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에서 설치하는 플랫폼 도구 집합을 통해 지원됩니다.  
  
|라이브러리|Windows 데스크톱 앱을 대상으로 하는 기본 플랫폼 도구 집합|[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 앱을 대상으로 하는 기본 플랫폼 도구 집합|[!INCLUDE[winxp](../build/includes/winxp_md.md)], [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]을 대상으로 하는 Windows XP 플랫폼 도구 집합|  
|-----------|------------------------------------------|-----------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|  
|CRT|X|X|X|  
|STL|X|X|X|  
|ATL|X|X|X|  
|ConCRT\/PPL|X|X|X|  
|MFC|X||X|  
|C\+\+ AMP|X|X||  
  
> [!NOTE]
>  C\+\+\/CLI로 작성되며 .NET Framework 4를 대상으로 하는 앱은 [!INCLUDE[winxp](../build/includes/winxp_md.md)] 및 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]에서 실행됩니다.  
  
### 도구 집합 간의 차이점  
 플랫폼 및 라이브러리 지원의 차이로 인해 Windows XP 플랫폼 도구 집합을 사용하는 앱의 개발 환경은 기본 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 플랫폼 도구 집합을 사용하는 앱처럼 완전하지 않습니다.  
  
-   **C\+\+ 언어 기능**  
  
     v110\_xp 플랫폼 도구 집합을 사용하는 앱에서는 [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)]에서 구현되는 C\+\+11 언어 기능만이 지원됩니다.  v120\_xp 플랫폼 도구 집합을 사용하는 앱에서는 [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)]에서 구현되는 C\+\+11 기능만 지원됩니다.  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에서는 이전 플랫폼 도구 집합을 사용하여 빌드할 때 해당 컴파일러를 사용합니다.  최신 Windows XP 버전에서 구현되는 추가 C\+\+11 기능을 활용하려면 해당 Windows XP 플랫폼 도구 집합을 사용하세요.  
  
-   **원격 디버깅**  
  
     [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]용 원격 도구는 [!INCLUDE[winxp](../build/includes/winxp_md.md)] 또는 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]에서 원격 디버깅을 지원하지 않습니다.  [!INCLUDE[winxp](../build/includes/winxp_md.md)] 또는 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]에서 실행되는 앱을 디버그하려면 이전 버전 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]의 디버거를 사용하여 로컬 또는 원격으로 앱을 디버그하면 됩니다.  이러한 디버그 환경은 플랫폼 도구 집합의 런타임 대상이지만 원격 디버깅 대상은 아닌 Windows Vista에서 앱을 디버그하는 환경과 비슷합니다.  
  
-   **정적 분석**  
  
     [!INCLUDE[win7](../build/includes/win7_md.md)] SDK의 SAL 주석과 런타임 라이브러리는 호환되지 않으므로 Windows XP 플랫폼 도구 집합은 정적 분석을 지원하지 않습니다.  [!INCLUDE[winxp](../build/includes/winxp_md.md)] 또는 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]을 지원하는 앱에서 정적 분석을 수행하려면 분석을 수행할 기본 플랫폼 도구 집합을 대상으로 하도록 솔루션을 일시적으로 전환했다가 다시 Windows XP 플랫폼 도구 집합으로 전환해 앱을 빌드할 수 있습니다.  
  
-   **DirectX 그래픽 디버깅**  
  
     그래픽 디버거는 Direct3D 9 API를 지원하지 않으므로 [!INCLUDE[winxp](../build/includes/winxp_md.md)] 또는 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]에서 Direct3D를 사용하는 앱을 디버그하는 데 사용할 수는 없습니다.  그러나 앱이 Direrct3D 10 또는 Direct3D 11 API를 사용하는 대체 렌더러를 구현하는 경우 그래픽 디버거를 사용하여 해당 API 사용 시 발생하는 문제를 진단할 수 있습니다.  
  
-   **HLSL 빌드**  
  
     Windows XP 도구 집합은 기본적으로 HSLS 소스 코드 파일을 컴파일하지 않습니다.  HLSL 파일을 컴파일하려면 2010년 6월 DirectX SDK를 다운로드하여 설치한 다음 해당 SDK를 포함하도록 프로젝트의 VC 디렉터리를 설정합니다.  자세한 내용은 [2010년 6월 DirectX SDK 다운로드 페이지](http://www.microsoft.com/download/details.aspx?displaylang=en&id=6812)의 "DirectX SDK가 Visual Studio 2010에 포함\/라이브러리 경로를 등록하지 않음" 섹션을 참조하세요.