---
title: C/c + + 코드를 명령줄에서 빌드 | Microsoft Docs
ms.custom: conceptual
ms.date: 06/21/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command-line builds [C++]
- compiling source code [C++], command line
- builds [C++], command-line
- command line [C++], building from
- command line [C++], compilers
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 241a7ae0d7f6c1adf269370301b39a3267440995
ms.sourcegitcommit: e013acba70aa29fed60ae7945162adee23e19c3b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36322318"
---
# <a name="build-cc-code-on-the-command-line"></a>C/c + + 코드를 명령줄에서 빌드

Visual Studio에 포함 된 도구를 사용 하 여 명령줄에서 C 및 c + + 응용 프로그램을 빌드할 수 있습니다.

## <a name="how-to-get-the-command-line-tools"></a>명령줄 도구를 다운로드 하는 방법

Visual Studio 설치 관리자에서 c + + 작업 중 하나를 선택할 때 Visual Studio 설치 *플랫폼 도구 집합*합니다. 플랫폼 도구 집합에 일치 하는 라이브러리 뿐만 아니라 C/c + + 컴파일러, 링커, 어셈블러 및 기타 빌드 도구를 포함 하 여 특정 Visual Studio 버전에 대 한 모든 C 및 c + + 도구가 있습니다. 이러한 도구는 명령줄에서 사용할 수 있습니다 및은 또한 Visual Studio IDE에서 내부적으로 사용 합니다. 별도 호스팅 x86 및 x64 호스팅 컴파일러, x86, x64, ARM에 대 한 코드를 작성 하는 도구 및 ARM64 대상 있습니다. 각 도구 집합을 특정 호스트 및 대상 빌드 아키텍처에 대 한 자체 디렉터리에 저장 됩니다.

도구는 제대로 작동 하려면 몇 가지 특정 환경 변수를 설정할 필요 합니다. 이러한 경로 추가 하는 데 사용 됩니다 설정 파일, 라이브러리 파일 및 SDK 위치를 포함 합니다. 설치 프로그램을 쉽게 이러한 환경 변수 설정 사용자 지정 된 만듭니다 *명령 파일*, 배치 파일을 설치 하는 동안 또는 합니다. 특정 호스트 및 대상 빌드 아키텍처, Windows SDK 버전, 대상 플랫폼 및 플랫폼 도구 집합을 설정 하려면 명령 프롬프트 창에서 이러한 명령 파일 중 하나를 실행할 수 있습니다. 편의 위해 설치 관리자도 바로 가기를 만듭니다. 시작 메뉴에 (또는 시작 페이지로 windows 8.x) 모든 필수 환경 변수는 설정된 사용할 준비가 됩니다. 이러한 명령 파일을 사용 하 여 개발자 명령 프롬프트 창을 시작 하는 합니다.

필수 환경 변수는 특정 설치 하 고 빌드 아키텍처를 선택 하 고 제품 업데이트 또는 업그레이드 시 변경 될 수 있습니다. 따라서 사용자가 직접 windows에서 환경 변수를 설정 하는 대신 설치 된 명령 프롬프트 바로 가기 또는 명령 파일 중 하나를 사용 하는 것이 좋습니다. 자세한 내용은 참조 [명령줄 빌드에 맞는 경로 및 환경 변수 설정](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)합니다.

명령줄 도구 집합, 명령 파일 및 설치 된 명령 프롬프트 바로 가기를 사용자 컴퓨터 프로세서 및 설치 중에 선택한 옵션에 따라 달라 집니다. 여기에 최소한 32 비트 x86 네이티브 코드를 빌드 및 64 비트 x64 네이티브 코드를 작성 하는 도구를 교차 하는 32 비트 x86 호스트 도구가 설치 됩니다. 64 비트 Windows를 사용 하도록 설정한 경우 64 비트 네이티브 코드를 빌드 및 32 비트 네이티브 코드를 작성 하는 도구를 교차 하는 64 비트 x64 호스팅 도구도 설치 됩니다. 선택적 c + + 유니버설 Windows 플랫폼 도구를 설치 하려는 경우 32 비트 및 64 비트 네이티브 도구를 ARM 코드 작성도 설치 됩니다. 다른 워크 로드는 추가 도구를 설치할 수 있습니다.

## <a name="developer-command-prompt-shortcuts"></a>개발자 명령 프롬프트 바로 가기 키

명령 프롬프트 바로 가기는 시작 메뉴에는 버전 별로 Visual Studio 폴더에 설치 됩니다. 기본 명령 프롬프트 바로 가기 및 지 원하는 빌드 아키텍처 목록은 다음과 같습니다.

- **개발자 명령 프롬프트** -32 비트, x86 네이티브 코드를 빌드하려면 32 비트, x86 네이티브 도구를 사용 하도록 환경을 설정 합니다.
- **x86 네이티브 도구 명령 프롬프트** -32 비트, x86 네이티브 코드를 빌드하려면 32 비트, x86 네이티브 도구를 사용 하도록 환경을 설정 합니다.
- **x64 네이티브 도구 명령 프롬프트** -64 비트, x64 네이티브 코드를 빌드하려면 64 비트, x64 네이티브 도구를 사용 하도록 환경을 설정 합니다.
- **x86_x64 Cross Tools 명령 프롬프트** -64 비트, x64 네이티브 코드를 빌드하려면 32 비트, x86 네이티브 도구를 사용 하도록 환경을 설정 합니다.
- **x64_x86 Cross Tools 명령 프롬프트** -32 비트, x86 네이티브 코드를 빌드하려면 64 비트, x64 네이티브 도구를 사용 하도록 환경을 설정 합니다.

실제 시작 메뉴 폴더 및 바로 가기 이름을 하나를 설정 하는 경우 설치한 Visual Studio의 버전 및 설치 애칭에 따라 달라 집니다. 예를 들어 Visual Studio 2017 설치 되어 있는 경우 한 것을 지정한 설치 별칭의 *미리 보기*, 개발자 명령 프롬프트 바로 가기를 라는 **VS 2017 (미리 보기)용개발자명령프롬프트**, 명명 된 폴더에 **Visual Studio 2017**합니다.

이전에 설치한 경우는 [Visual Studio 2017 용 빌드 도구](https://go.microsoft.com/fwlink/p/?linkid=875721) (도 포함 하는 Visual Studio 2015 업데이트 3 컴파일러 도구 집합), 아키텍처별 네이티브 또는 크로스 도구 옵션 설치 된 개발자 명령 프롬프트 를 일반 하지 **개발자 명령 프롬프트** 바로 가기 합니다.

<a name="developer_command_prompt"></a>
### <a name="to-open-a-developer-command-prompt-window"></a>개발자 명령 프롬프트 창을 열려면

1. 바탕 화면에서 창을 열 **시작** 메뉴, 및를 찾아서 예를 들어 Visual Studio 버전에 대 한 폴더를 열고 다음 스크롤 **Visual Studio 2017**합니다. 일부 이전 버전의 Visual Studio에서 바로 가기 키 라는 하위 폴더에는 **Visual Studio Tools**합니다.

1. 폴더를 선택 하 고 **개발자 명령 프롬프트** 의 Visual Studio 버전에 대 한 합니다. 이 바로 가기 기본 빌드 아키텍처의 32 비트, x86 네이티브 도구를 사용 하 여 32 비트, x86 네이티브 코드를 빌드하려면 개발자 명령 프롬프트 창을 시작 합니다. 기본이 아닌 빌드 아키텍처를 선호 하는 경우 네이티브 중 하나를 선택 또는 크로스 도구 명령 프롬프트는 호스트 및 대상 아키텍처를 지정할 수 있습니다.

빨리 개발자 명령 프롬프트 창을 열고를 입력 하는 것 *개발자 명령 프롬프트* 데스크톱 검색 상자에 원하는 결과 선택 합니다.

## <a name="developer-command-files-and-locations"></a>개발자 명령 파일 및 위치

기존 명령 프롬프트 창에서 빌드 아키텍처 환경을 설정 하는 것을 선호 하는 경우 필요한 환경을 설정 하려면 설치 관리자가 만든 명령 파일 (일괄 처리 파일) 중 하나를 사용할 수 있습니다. 만 좋습니다 새 명령 프롬프트 창에서이 작업을 수행 하 고 권장 하지는 않습니다 하면 동일한 명령 창에서 이상의 스위치 환경입니다. 이러한 파일의 위치와 위치 및 이름 지정 선택한 설치 하는 동안 내용을 설치 하면 Visual Studio의 버전에 따라 다릅니다. Visual Studio 2017 64 비트 컴퓨터에 일반적인 설치 위치는 \Program 파일 (x86) \Microsoft Visual Studio\2017에\\*edition*여기서 *edition* 커뮤니티 될 수 있습니다 Professional, Enterprise, BuildTools, 또는 다른 이름을 입력 합니다. Visual Studio 2015에 대 한 일반적인 설치 위치는 \Program (x86) Files \microsoft Visual Studio 14.0입니다.

VsDevCmd.bat, 기본 개발자 명령 프롬프트 명령 파일은 설치 디렉터리의 Common7\Tools 하위 디렉터리에 있으며 매개 변수가 지정 된,이 환경을 설정 하 고, 호스트 및 대상 32 비트 x86를 작성 하는 32 비트 x86 네이티브 도구를 사용 하는 아키텍처를 빌드할 때 코드입니다.

추가 명령 파일 프로세서 아키텍처용 Visual Studio 작업 부하 및 설치 옵션에 따라 특정 빌드 아키텍처를 설정할 수 있습니다. Visual Studio 2017 년에서 이러한 권장 사항은 Visual Studio 설치 디렉터리의 VC\Auxiliary\Build 하위 디렉터리입니다. Visual Studio 2015에서 이러한 권장 사항은 VC, VC\bin, 또는 VC\bin\\*아키텍처* 설치 디렉터리의 하위 디렉터리를 *아키텍처* 네이티브 중 하나 또는 크로스 컴파일러 옵션입니다. 이러한 명령 파일 기본 매개 변수를 설정 하 고 지정 된 빌드 아키텍처 환경을 설정 하는 VsDevCmd.bat 호출. 일반 설치의 경우 이러한 명령 파일을 포함할 수 있습니다.

|명령 파일|호스트 및 대상 아키텍처|
|---|---|
|**vcvars32.bat**| 32 비트 x86 네이티브 도구를 사용 하 여 32 비트 x86 만들려는 코드입니다.|
|**vcvars64.bat**| 64 비트 x64 네이티브 도구를 사용 하 여 64 비트 x64 만들려는 코드입니다.|
|**vcvarsx86_amd64.bat**| 32 비트 x86 네이티브 크로스 도구를 사용 하 여 64 비트 x64 만들려는 코드입니다.|
|**vcvarsamd64_x86.bat**| 64 비트 x64 네이티브 크로스 도구를 사용 하 여 32 비트 x86 만들려는 코드입니다.|
|**vcvarsx86_arm.bat**| 32 비트 x86 네이티브 크로스 도구를 사용 하 여 ARM 코드를 작성 합니다.|
|**vcvarsamd64_arm.bat**| 64 비트 x64 네이티브 크로스 도구를 사용 하 여 ARM 코드를 작성 합니다.|
|**vcvarsall.bat**| 매개 변수를 사용 하는 호스트 및 대상 아키텍처도 SDK 및 플랫폼 선택 항목을 지정 합니다. 목록은 지원 되는 옵션을 사용 하 여 호출 된 **/h** 매개 변수입니다.|

> [!CAUTION]
> Vcvarsall.bat 파일 및 기타 Visual Studio 명령 파일 컴퓨터 마다 다를 수 있습니다. 누락되거나 손상된 vcvarsall.bat 파일을 다른 컴퓨터의 파일로 바꾸지 마세요. 누락 된 파일을 대체 하려면 Visual Studio 설치 관리자를 다시 실행 합니다.
>
> 또한 vcvarsall.bat 파일은 버전별로 다릅니다. 또한 Visual Studio의 이전 버전을 보유 하는 컴퓨터에서 현재 버전의 Visual Studio가 설치 되어 실행 하지 마십시오 vcvarsall.bat 또는 다른 Visual Studio 명령 파일 같은 명령 프롬프트 창에서 서로 다른 버전의.

## <a name="use-the-developer-tools-in-an-existing-command-window"></a>개발자 도구를 사용 하 여 기존 명령 창에서

기존 명령 창에서 특정 빌드 아키텍처를 지정 하는 가장 간단한 방법은 vcvarsall.bat 파일을 사용 하는 합니다. Vcvarsall.bat를 사용 하 여 네이티브 32 비트 또는 64 비트 컴파일 또는 x86, x64 또는 ARM 프로세서;에 크로스 컴파일을 위한 명령줄을 구성 하려면 환경 변수를 설정 하려면 Microsoft 저장소 대상, 유니버설 Windows 플랫폼 또는 Windows 바탕 화면 플랫폼; Windows SDK; 사용 하도록 지정 하려면 및 플랫폼 도구 집합 버전을 지정할 수 있습니다. Vcvarsall.bat x86에 대 한 현재 32 비트 네이티브 컴파일러를 사용 하는 것에 대 한 환경 변수를 구성 하지 인수를 제공 하는 경우 Windows 바탕 화면을 대상으로 합니다. 그러나 네이티브 조인, 크로스 컴파일러 도구 하나를 구성 하려면 사용할 수 있습니다. 설치 되어 있지 않거나 빌드 컴퓨터 아키텍처에서 사용할 수 없는 컴파일러 구성을 지정 하면 오류 메시지가 표시 됩니다.

### <a name="vcvarsall-syntax"></a>vcvarsall 구문

> **vcvarsall.bat** [*architecture*] [*platform_type*] [*winsdk_version*] [**-vcvars_ver=**_vcversion_]

*architecture*<br/>
이 선택적 인수를 사용 하 여 호스트와 대상 아키텍처를 지정 합니다. 경우 *아키텍처* 를 지정 하지 않으면 기본 빌드 환경을 사용 합니다. 이 인수는 지원 됩니다.

|*architecture*|컴파일러|호스트 컴퓨터 아키텍처|(대상) 출력 아키텍처 빌드|
|----------------------------|--------------|----------------------------------|-------------------------------|
|**x86**|x86 32비트 네이티브|x86, x64|x86|
|**x86\_amd64** 또는 **x86\_x64**|x86 x64 cross|x86, x64|X64|
|**x86_arm**|x86용 ARM 크로스|x86, x64|ARM|
|**x86_arm64**|ARM64 x86 크로스|x86, x64|ARM64|
|**amd64** 또는 **x64**|x64 64 비트 네이티브|X64|X64|
|**amd64\_x86** 또는 **x64\_x86**|x64 x86 cross|X64|x86|
|**amd64\_arm** 또는 **x64\_arm**|용 ARM 크로스 x64|X64|ARM|
|**amd64\_arm64** 또는 **x64\_arm64**|ARM64 x64 크로스|X64|ARM64|

*platform_type*<br/>
이 선택적 인수를 지정할 수 있습니다. **저장** 또는 **uwp** 플랫폼 형식으로. 기본적으로 데스크톱 또는 콘솔 응용 프로그램을 빌드하는 환경 설정 됩니다.

*winsdk_version*<br/>
필요에 따라 사용 하는 Windows SDK의 버전을 지정 합니다. 설치 된 최신 Windows SDK는 기본적으로 사용 됩니다. Windows SDK 버전을 지정 하려면 사용할 수 있습니다 전체 Windows 10 SDK 번호와 같은 **10.0.10240.0**를 지정 하거나 **8.1** Windows 8.1 SDK를 사용 하도록 합니다.

*vcversion*<br/>
필요에 따라 사용 하는 Visual Studio 컴파일러 도구 집합을 지정 합니다. 기본적으로 환경은 현재 Visual Studio 2017 컴파일러 도구 집합을 사용 하도록 설정 됩니다. 사용 하 여 **-vcvars_ver = 14.0** Visual Studio 2015 컴파일러 도구 집합을 지정할 수 있습니다.

<a name="vcvarsall"></a>
#### <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a>기존 명령 프롬프트 창에서 빌드 환경을 설정 하려면

1. 명령 프롬프트에서 CD 명령을 사용 하 여 Visual Studio 설치 디렉터리를 변경 합니다. 그런 다음 다시 사용 하 여 CD 구성 관련 명령 파일을 포함 하는 하위 디렉터리를 변경 합니다. Visual Studio 2017 VC\Auxiliary\Build 하위 디렉터리입니다. Visual Studio 2015에 대 한 VC 하위 디렉터리를 사용 합니다.

1. 선호 하는 개발자 환경에 대 한 명령을 입력 합니다. 예를 들어 ARM 코드를 작성 하려면 UWP에 대 한 64 비트 플랫폼에서 최신 Windows SDK 및 Visual Studio 2017 RTM 컴파일러 도구 집합을 사용 하 여 명령줄을 사용 합니다.

   `vcvarsall.bat amd64_arm uwp -vcvars_ver=14.10`

## <a name="create-your-own-command-prompt-shortcut"></a>명령 프롬프트 바로 가기 만들기

기존 개발자 명령 프롬프트 바로 가기 중 하나에 대 한 속성 대화 상자를 열면 사용 하는 명령 대상을 볼 수 있습니다. 대상에 대 한 예를 들어는 **x64 네이티브 도구 명령 프롬프트에 대 한 VS 2017** 바로 가기는 다음과 같은 내용이:

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvars64.bat"`

아키텍처 관련 배치 파일 집합의 *아키텍처* vcvarsall.bat 매개 변수를 호출 합니다. Vcvarsall.bat를로 전달할 수 하거나 호출 하면 vcvarsall.bat 직접이 배치 파일을 같은 추가 옵션을 전달할 수 있습니다. 사용자 고유의 명령 바로 가기에 대 한 매개 변수를 지정 하려면 큰따옴표 안에 명령 끝에 추가 합니다. 예를 들어를 설정 하려면 코드를 빌드하려면 ARM UWP에 대 한 64 비트 플랫폼에서 최신 Windows SDK 및 Visual Studio 2017 RTM 컴파일러 도구 집합을 사용 하 여 바로 가기를 다음과 같이 사용할이 명령 대상에서 프로그램 바로 가기.

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvarsall.bat amd64_arm uwp -vcvars_ver=14.10"`

Visual Studio 설치 디렉터리를 반영 하도록 경로 조정 해야 합니다.

## <a name="command-line-tools"></a>명령줄 도구

명령줄에서 C/c + + 프로젝트를 빌드하려면 Visual Studio에서는 이러한 명령줄 도구를 제공 합니다.

[CL](../build/reference/compiling-a-c-cpp-program.md)<br/>
컴파일러(cl.exe)를 사용하여 소스 코드 파일을 컴파일한 다음 앱, 라이브러리 및 DLL에 연결합니다.

[링크](../build/reference/linking.md)<br/>
링커(link.exe)를 사용하여 컴파일된 개체 파일 및 라이브러리를 앱 및 DLL에 연결합니다.

[MSBuild(Visual C++)](../build/msbuild-visual-cpp.md)<br/>
MSBuild (msbuild.exe)를 사용 하 여 Visual c + + 프로젝트와 Visual Studio 솔루션을 작성 합니다. 이 실행에 해당 하는 **빌드** 프로젝트 또는 **솔루션 빌드** Visual Studio IDE에서 명령을 합니다.

[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)<br/>
명령줄 스위치와 함께 DEVENV (devenv.exe)를 사용 하 여-예를 들어 **/빌드** 또는 **/clean**-수행 하려면 특정 빌드 명령을 Visual Studio IDE를 표시 하지 않고 있습니다.

[NMAKE](../build/nmake-reference.md)<br/>
NMAKE (nmake.exe)를 사용 하 여 기존 메이크파일을 사용 하 여 Visual c + + 프로젝트를 빌드 작업을 자동화 합니다.

명령줄에서 빌드할 때 F1 명령에 대 한 인스턴트 도움말 ´ ù. 대신, 경고, 오류 및 메시지에 대 한 정보 검색 엔진을 사용할 수 있습니다 또는 오프 라인 도움말 파일을 사용할 수 있습니다. 검색을 사용 하려면 [docs.microsoft.com](https://docs.microsoft.com/cpp/), 페이지 맨 위에 있는 검색 상자에 검색 문자열을 입력 합니다.

## <a name="in-this-section"></a>섹션 내용

설명서의 이 섹션에 있는 문서는 명령줄에서 앱을 빌드하는 방법을 보여주고, 64비트 도구 집합을 사용하고 x86, x64 및 ARM 플랫폼을 대상으로 하도록 명령줄 빌드 환경을 사용자 지정하는 방법에 대해 설명하고, 명령줄 빌드 도구인 MSBuild 및 NMAKE를 사용하는 방법을 보여줍니다.

[연습: 명령줄에서 네이티브 C++ 프로그램 컴파일](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)<br/>
명령줄에서 간단한 C++ 프로그램을 만들고 컴파일하는 방법을 보여주는 예제를 제공합니다.

[연습: 명령줄에서 C 프로그램 컴파일](../build/walkthrough-compile-a-c-program-on-the-command-line.md)<br/>
C 프로그래밍 언어로 작성한 프로그램을 컴파일하는 방법에 대해 설명합니다.

[연습: 명령줄에서 C++/CLI 프로그램 컴파일](../build/walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)<br/>
.NET Framework를 사용하는 C++/CLI 프로그램을 만들어 컴파일하는 방법에 대해 설명합니다.

[연습: 명령줄에서 C++-CX 프로그램 컴파일](../build/walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)<br/>
Windows 런타임을 사용하는 C++/CX 프로그램을 만들어 컴파일하는 방법에 대해 설명합니다.

[명령줄 빌드에 맞는 경로 및 환경 변수 설정](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)<br/>
필수 환경 변수 및 32 비트 또는 64 비트 도구 집합을 사용 하 여 ARM 플랫폼을 대상으로 하는 x86, x64, 명령줄 빌드에 설정 된 명령 프롬프트 창을 시작 하는 방법에 설명 합니다.

[NMAKE 참조](../build/nmake-reference.md)<br/>
Microsoft Program Maintenance Utility(NMAKE.EXE)에 대해 설명하는 문서의 링크를 제공합니다.

[MSBuild(Visual C++)](../build/msbuild-visual-cpp.md)<br/>
MSBuild.EXE를 사용하는 방법에 대해 설명하는 문서의 링크를 제공합니다.

## <a name="related-sections"></a>관련 단원

[/MD, /MT, /LD(런타임 라이브러리 사용)](../build/reference/md-mt-ld-use-run-time-library.md)<br/>
컴파일러 옵션을 사용하여 디버그 또는 릴리스 런타임 라이브러리를 사용하는 방법에 대해 설명합니다.

[C/c + + 컴파일러 옵션](../build/reference/compiler-options.md)<br/>
C 및 C++ 컴파일러 옵션과 CL.exe에 대해 설명하는 문서에 대한 링크를 제공합니다.

[링커 옵션](../build/reference/linker-options.md)<br/>
링커 옵션 및 LINK.exe에 대해 설명하는 문서에 대한 링크를 제공합니다.

[ 빌드 도구](../build/reference/c-cpp-build-tools.md)<br/>
C/c + +에 대 한 링크 빌드 Visual Studio에 포함 된 도구를 제공 합니다.

## <a name="see-also"></a>참고자료

[C/C++ 프로그램 빌드](../build/building-c-cpp-programs.md)