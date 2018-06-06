---
title: Visual C++의 CMake 프로젝트 | Microsoft Docs
ms.custom: ''
ms.date: 08/08/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3a65ae6cc58f649fee5f47b33a146263a3b6c55
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337433"
---
# <a name="cmake-projects-in-visual-c"></a>Visual C++의 CMake 프로젝트

이 문서에서는 여러 플랫폼에서 실행되는 빌드 프로세스를 정의하는 플랫폼 간 오픈 소스 도구인 CMake에 익숙하다고 가정합니다.

최근까지 Visual Studio 사용자는 CMake를 사용하여 MSBuild 프로젝트 파일을 생성한 다음, IDE에서 IntelliSense, 검색 및 컴파일을 수행하는 데 이 파일을 사용했습니다. Visual Studio 2017부터 **CMake용 Visual C++ 도구** 구성 요소에서 **폴더 열기** 기능을 사용하여 IDE에서 IntelliSense 및 검색을 수행하는 데 CMake 프로젝트 파일(예: CMakeLists.txt)을 직접 사용할 수 있습니다. Visual Studio 생성기를 사용하는 경우 임시 프로젝트 파일이 생성되어 msbuild.exe에 전달되지만 IntelliSense 또는 검색을 위해 로드되지는 않습니다. 

**Visual Studio 2017 버전 15.3**: Ninja 및 Visual Studio 생성기 모두에 대한 지원이 제공됩니다.

**Visual Studio 2017 버전 15.4**: Linux에서 CMake에 대한 지원이 추가되었습니다. 자세한 내용은 [Linux CMake 프로젝트 구성](../linux/cmake-linux-project.md)을 참조하세요.

**Visual Studio 2017 버전 15.5**: 기존 CMake 캐시 가져오기에 대한 지원이 추가되었습니다. Visual Studio는 자동으로 사용자 지정 변수를 추출하고 미리 채워진 CMakeSettings.json 파일을 만듭니다.


## <a name="installation"></a>설치

**CMake용 Visual C++ 도구**는 기본적으로 **C++를 사용한 데스크톱 개발** 워크로드의 일부로 설치됩니다.

![C++ 데스크톱 워크로드의 CMake 구성 요소](media/cmake-install.png)
 
## <a name="ide-integration"></a>IDE 통합

**파일 | 열기 | 폴더**를 차례로 사용하여 CMakeLists.txt 파일이 포함된 폴더를 열면 다음과 같이 수행됩니다.

- Visual Studio에서 CMake 스크립트를 보고 편집하는 명령이 있는 **CMake** 메뉴 항목이 주 메뉴에 추가됩니다.
- **솔루션 탐색기**에서 폴더 구조와 파일이 표시됩니다.
- Visual Studio에서 CMake.exe를 실행하고 x86 디버그인 기본 *구성*에 대한 CMake 캐시를 생성합니다. CMake 명령줄이 CMake의 추가 출력과 함께 **출력 창**에 표시됩니다.
- IntelliSense, 검색 정보, 리팩터링 등을 사용할 수 있도록 하기 위해 Visual Studio에서 백그라운드로 소스 파일을 인덱싱합니다. 작업하는 동안 Visual Studio에서 편집기와 디스크의 변경 내용을 모니터링하여 인덱스가 소스와 동기화되도록 유지합니다.
 
여러 CMake 프로젝트가 포함된 폴더를 열 수 있습니다. Visual Studio에서는 작업 영역의 모든 "루트" CMakeLists.txt 파일을 검색하고 구성합니다. C++ IntelliSense 및 검색뿐만 아니라 CMake 작업(구성, 빌드, 디버그)도 작업 영역의 모든 CMake 프로젝트에서 사용할 수 있습니다.

![여러 루트가 있는 CMake 프로젝트](media/cmake-multiple-roots.png) 

## <a name="import-an-existing-cache"></a>기존 캐시 가져오기

기존 CMakeCache.txt 파일을 가져오면 Visual Studio에서 자동으로 사용자 지정 변수를 추출하고 이에 따라 미리 채워진 CMakeSettings.json 파일을 만듭니다. 원래 캐시는 어떤 방식으로든 수정되지 않으며, 명령줄 또는 생성하는 데 사용된 도구 또는 IDE를 통해 계속 사용할 수 있습니다. 새 CMakeSettings.json 파일은 프로젝트의 루트 CMakeLists.txt와 함께 배치됩니다. Visual Studio에서는 설정 파일을 기반으로 하여 새 캐시를 생성합니다. 캐시의 모든 항목을 가져오지는 않습니다.  생성기 및 컴파일러 위치와 같은 속성은 IDE에서 제대로 작동하는 것으로 알려진 기본값으로 대체됩니다.

### <a name="to-import-an-existing-cache"></a>기존 캐시를 가져오려면

1. 주 메뉴에서 **파일 | 열기 | CMake**를 차례로 선택합니다.

   ![CMake 열기](media/cmake-file-open.png "파일, 열기, CMake") 

   **캐시에서 CMake 가져오기** 마법사가 표시됩니다. 
   
2. 가져오려는 CMakeCache.txt 파일로 이동한 다음, **확인**을 클릭합니다. **캐시에서 CMake 프로젝트 가져오기** 마법사가 표시됩니다.

   ![CMake 캐시 가져오기](media/cmake-import-wizard.png "캐시에서 CMake 프로젝트 가져오기 마법사 열기") 

   마법사가 완료되면 프로젝트의 루트 CMakeLists.txt 파일 옆에 있는 **솔루션 탐색기**에서 새 CMakeCache.txt 파일이 표시됩니다.


## <a name="building-cmake-projects"></a>CMake 프로젝트 빌드

CMake 프로젝트를 빌드하려면 다음과 같이 선택할 수 있습니다.

1. **디버그** 드롭다운에서 대상을 선택하고, **F5** 키를 누르거나 **실행**(녹색 삼각형) 단추를 클릭합니다. Visual Studio 솔루션과 마찬가지로 프로젝트가 자동으로 먼저 빌드됩니다.
1. CMakeLists.txt를 마우스 오른쪽 단추로 클릭하고, 상황에 맞는 메뉴에서 **빌드**를 선택합니다. 폴더 구조에 여러 대상이 있는 경우 모든 대상 또는 특정 대상만 빌드하도록 선택할 수 있습니다.
1. 주 메뉴에서 **빌드 | 솔루션 빌드**(**F7** 또는 **Ctrl+Shift+B**)를 선택합니다. **일반** 도구 모음의 **시작 항목** 드롭다운에서 CMake 대상이 이미 선택되어 있는지 확인합니다.

![CMake 빌드 메뉴 명령](media/cmake-build-menu.png "CMake 빌드 명령 메뉴") 

Visual Studio 생성기가 활성 구성으로 선택되면 `-m -v:minimal` 인수를 사용하여 MSBuild.exe가 호출됩니다. CMakeSettings.json 파일 내에서 빌드를 사용자 지정하려면 `buildCommandArgs` 속성을 통해 빌드 시스템에 전달할 추가 명령줄 인수를 지정할 수 있습니다.

```json
"buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
```

빌드 결과가 예상한 대로 **출력 창** 및 **오류 목록**에 표시됩니다.
 
![CMake 빌드 오류](media/cmake-build-errors.png "CMake 빌드 오류")

여러 빌드 대상이 있는 폴더의 **CMake** 메뉴 또는 상황에 맞는 **CMakeLists.txt** 메뉴에서 **빌드** 항목을 선택하여 빌드할 CMake 대상을 지정할 수 있습니다. CMake 프로젝트에서 **Ctrl+Shift+B**를 누르면 현재 활성 문서가 빌드됩니다.

## <a name="debug-the-project"></a>프로젝트 디버그

CMake 프로젝트를 디버그하려면 원하는 구성을 선택하고 **F5** 키를 누르거나 도구 모음에서 **실행** 단추를 누릅니다. **실행** 단추에서 "시작 항목 선택"이라고 표시되면 드롭다운 화살표를 선택하고 실행할 대상을 선택합니다. (CMake 프로젝트에서 "현재 문서" 옵션은 .cpp 파일에만 유효합니다.) 

![CMake 실행 단추](media/cmake-run-button.png "Cmake 실행 단추")


**실행** 또는 **F5** 명령은 이전 빌드 이후 변경된 경우 프로젝트를 먼저 빌드합니다.

## <a name="configure-cmake-debugging-sessions"></a>CMake 디버깅 세션 구성

실행 가능한 모든 CMake 대상은 **일반** 도구 모음의 **시작 항목** 드롭다운에 표시됩니다. 디버깅 세션을 시작하려면 하나를 선택하고 디버거를 시작하기만 하면 됩니다.

![CMake 시작 항목 드롭다운](media/cmake-startup-item-dropdown.png "CMake 시작 항목 드롭다운")


CMake 메뉴에서 디버그 세션을 시작할 수도 있습니다.

프로젝트의 실행 가능한 CMake 대상에 대한 디버거 설정을 사용자 지정하려면, 특정 CMakeLists.txt 파일을 마우스 오른쪽 단추로 클릭하고 **디버그 및 시작 설정**을 선택합니다. 하위 메뉴에서 CMake 대상을 선택하면 launch.vs.json이라는 파일이 만들어집니다. 이 파일은 선택한 CMake 대상에 대한 정보로 미리 채워져 있으며 프로그램 인수자 또는 디버거 형식과 같은 추가 매개 변수를 지정할 수 있습니다. CMakeSettings.json 파일의 모든 키를 참조하려면 launch.vs.json 앞에 "cmake."를 붙입니다. 다음 예제에서는 CMakeSettings.json 파일에서 현재 선택한 구성에 대한 "remoteCopySources" 키 값을 가져오는 간단한 launch.vs.json 파일을 보여 줍니다.

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
   {
      "type": "default",
      "project": "CMakeLists.txt",
      "projectTarget": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "name": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "args": ["${cmake.remoteCopySources}"]
    }
  ]
}
```

launch.vs.json 파일을 저장하는 즉시 **시작 항목** 드롭다운에 새 이름의 항목이 만들어집니다. launch.vs.json 파일을 편집하여 임의 개수의 CMake 대상에 대해 원하는 만큼 많은 디버그 구성을 만들 수 있습니다.

**Visual Studio 2017 버전 15.4**: launch.vs.json은 CMakeSettings.json(아래 참조)에서 선언되고 현재 선택한 구성에 적용된 변수를 지원합니다. 또한 시작하는 응용 프로그램의 현재 디렉터리를 설정하는 "currentDir"이라는 키가 있습니다.


```json
{
"type": "default",
"project": "CMakeLists.txt",
"projectTarget": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"name": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"currentDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}"
}
```

응용 프로그램을 실행할 때 `currentDir` 값은 다음과 비슷합니다.

```cmd
C:\Users\satyan\7f14809a-2626-873e-952e-cdf038211175\
```

## <a name="editing-cmakeliststxt-files"></a>CMakeLists.txt 파일 편집

CMakeLists.txt 파일을 편집하려면 **솔루션 탐색기**에서 파일을 마우스 오른쪽 단추로 클릭하고 **열기**를 선택합니다. 파일을 변경하면 노란색 상태 표시줄이 표시되고, IntelliSense가 업데이트됨을 알리고, 업데이트 작업을 취소할 수 있는 기회를 제공합니다. CMakeLists.txt에 대한 자세한 내용은 [CMake 설명서](https://cmake.org/documentation/)를 참조하세요.

   ![CMakeLists.txt 파일 편집](media/cmake-cmakelists.png "CMakeLists.txt 파일 편집")


파일을 저장하는 즉시 구성 단계가 자동으로 다시 실행되고 **출력** 창에 정보가 표시됩니다. 오류와 경고가 **오류 목록** 또는 **출력** 창에 표시됩니다. **오류 목록**에서 오류를 두 번 클릭하여 CMakeLists.txt에서 잘못된 줄로 이동합니다.

   ![CMakeLists.txt 파일 오류](media/cmake-cmakelists-error.png "CMakeLists.txt 파일 오류")

## <a name="cmake_settings"></a> CMake 설정 및 사용자 지정 구성

기본적으로 Visual Studio에서는 6가지 기본 CMake 구성("x86-Debug", "x86-Release", "x64-Debug", "x64-Release", "Linux-Debug" 및 "Linux-Release")을 제공합니다. 이러한 구성은 CMake.exe를 호출하여 지정된 프로젝트에 대한 CMake 캐시를 만드는 방법을 정의합니다. 이러한 구성을 수정하거나 새 사용자 지정 구성을 만들려면 **CMake | CMake 설정 변경**을 차례로 선택한 다음, 설정이 적용되는 CMakeLists.txt 파일을 선택합니다. **CMake 설정 변경** 명령은 **솔루션 탐색기**의 상황에 맞는 파일 메뉴에서도 사용할 수 있습니다. 이 명령은 프로젝트 폴더에 CMakeSettings.json 파일을 만듭니다. 이 파일은 예를 들어 **정리** 작업 후에 CMake 캐시 파일을 다시 만드는 데 사용됩니다. 

   ![설정 변경에 대한 CMake 주 메뉴 명령](media/cmake-change-settings.png)


JSON IntelliSense를 사용하면 CMakeSettings.json 파일을 편집할 수 있습니다.

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

다음 예제에서는 CMakeSettings.json에서 직접 만들기 위한 시작 지점으로 사용할 수 있는 샘플 구성을 보여 줍니다.

```json
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "-v",
      "ctestCommandArgs": ""
    },

```

1. **name**: C++ 구성 드롭다운에 표시되는 이름입니다. 이 속성 값은 매크로(`${name}`)로 사용되어 다른 속성 값을 지정할 수 있습니다. 예를 들어 CMakeSettings.json의 **buildRoot** 정의를 참조합니다.
1. **generator**: **-G** 스위치에 매핑되고 사용할 생성기를 지정합니다. 이 속성도 매크로(`${generator}`)로 사용되어 다른 속성 값을 지정할 수 있도록 합니다. Visual Studio에서 현재 지원하는 CMake 생성기는 다음과 같습니다.


    - "Ninja"
    - "Visual Studio 14 2015"
    - "Visual Studio 14 2015 ARM"
    - "Visual Studio 14 2015 Win64"
    - "Visual Studio 15 2017"
    - "Visual Studio 15 2017 ARM"
    - "Visual Studio 15 2017 Win64"

Ninja는 유연성과 기능 대신 빠른 속도를 구현하도록 설계되었으므로 기본값으로 설정됩니다. 그러나 일부 CMake 프로젝트는 Ninja를 사용하여 올바르게 빌드하지 못할 수도 있습니다. 이 경우 CMake에서 Visual Studio 프로젝트를 대신 생성하도록 지시할 수 있습니다.

Visual Studio 생성기를 지정하려면 주 메뉴에서 **CMake | CMake 설정 변경**을 차례로 선택하여 CMakeSettings.json을 엽니다. "Ninja"를 삭제하고 "V"를 입력합니다. 이렇게 하면 원하는 생성기를 선택할 수 있도록 IntelliSense가 활성화됩니다.

1. **buildRoot**: **-DCMAKE_BINARY_DIR** 스위치에 매핑하고 CMake 캐시가 만들어질 위치를 지정합니다. 폴더가 없으면 해당 폴더가 만들어집니다.
1. **variables**: **-D**_이름_**=**_값_으로 CMake에 전달되는 CMake 변수의 이름-값 쌍이 포함됩니다. CMake 프로젝트 빌드 지침에서 CMake 캐시 파일에 변수를 직접 추가하도록 지정하는 경우 여기에 대신 추가하는 것이 좋습니다.
1. **cmakeCommandArgs**: CMake.exe에 전달하려는 추가 스위치를 지정합니다.
1. **configurationType**: 선택한 생성기에 대한 빌드 구성 형식을 정의합니다. 현재 지원되는 값은 "Debug", "MinSizeRel", "Release" 및 "RelWithDebInfo"입니다.

### <a name="environment-variables"></a>환경 변수

CMakeSettings.json은 위에서 언급한 속성 중 하나에서 환경 변수를 사용하는 것도 지원합니다. 사용되는 구문은 %FOO% 환경 변수를 확장한 `${env.FOO}`입니다.
또한 이 파일에 기본 제공된 매크로에 액세스할 수 있습니다.

- `${workspaceRoot}` - 작업 영역 폴더의 전체 경로를 제공합니다.
- `${workspaceHash}` - 작업 영역 위치의 해시입니다. 현재 작업 영역에 대한 고유 식별자를 만드는 데 유용합니다(예: 폴더 경로에서 사용).
- `${projectFile}` - 루트 CMakeLists.txt 파일의 전체 경로
- `${projectDir}` - 루트 CMakeLists.txt 파일의 폴더에 대한 전체 경로
- `${thisFile}` - CMakeSettings.json 파일의 전체 경로
- `${name}` - 구성의 이름
- `${generator}` - 이 구성에 사용된 CMake 생성기의 이름

### <a name="ninja-command-line-arguments"></a>Ninja 명령줄 인수

대상이 지정되지 않으면 'default(기본)' 대상을 빌드합니다(설명서 참조).

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|옵션|설명|
|--------------|------------|
| --version  | Ninja 버전("1.7.1")을 출력합니다.|
|   -C DIR   | 다른 작업을 수행하기 전에 DIR로 변경합니다.|
|   -f FILE  | 입력 빌드 파일을 지정합니다(기본값 = build.ninja)|
|   -j N     | N개의 작업을 병렬로 실행합니다(기본값 = 14, 사용 가능한 CPU에서 파생됨).|
|   -k N     | N개의 작업이 실패할 때까지 계속 수행됩니다(기본값 = 1)|
|   -l N     | 부하 평균이 N보다 큰 경우 새 작업을 시작하지 않습니다.|
|   -n      | 시험 실행을 수행합니다(명령을 실행하지 않고 성공한 것처럼 작동함)|
|   -v       | 빌드하는 동안 모든 명령줄을 표시합니다.|
|   -d MODE  | 디버깅을 사용하도록 설정합니다(-d list를 사용하여 모드를 나열함).|
|   -t TOOL  | 하위 도구를 실행합니다(-t list를 사용하여 하위 도구를 나열함). 최상위 옵션을 종료합니다. 추가 플래그가 도구에 전달됩니다.| 
|   -w FLAG  | 경고를 조정합니다(-w list를 사용하여 경고를 표시함).|

### <a name="inherited-environments-visual-studio-2017-version-155"></a>상속된 환경(Visual Studio 2017 버전 15.5)
이제 CMakeSettings.json은 상속된 환경을 지원합니다. 이 기능을 사용하면 (1) 기본 환경을 상속하고, (2) 실행될 때 CMake.exe에 전달되는 사용자 지정 환경 변수를 만들 수 있습니다.

```json
  "inheritEnvironments": [ "msvc_x64_x64" ]
```

위의 예제는 **-arch=amd64 -host_arch=amd64** 인수를 사용하여 **VS 2017용 개발자 명령 프롬프트**를 실행하는 것과 같습니다.

다음 표에서는 기본값과 이에 해당하는 명령줄을 보여 줍니다.

|컨텍스트 이름|설명|
|-----------|-----------------|
|vsdev|기본 Visual Studio 환경|
|msvc_x86|x86 도구를 사용하여 x86용으로 컴파일|
|msvc_arm| x86 도구를 사용하여 ARM용으로 컴파일|
|msvc_arm64|x86 도구를 사용하여 ARM64용으로 컴파일|
|msvc_x86_x64|x86 도구를 사용하여 AMD64용으로 컴파일|
|msvc_x64_x64|64비트 도구를 사용하여 AMD64용으로 컴파일|
|msvc_arm_x64|64비트 도구를 사용하여 ARM용으로 컴파일|
|msvc_arm64_x64|64비트 도구를 사용하여 ARM64용으로 컴파일|

### <a name="custom-environment-variables"></a>사용자 지정 환경 변수
CMakeSettings.json에서는 **environments** 속성에서 전역으로 또는 구성별로 사용자 지정 환경 변수를 정의할 수 있습니다. 다음 예제에서는 x86-Debug 및 x64-Debug 구성 모두에서 상속된 하나의 **BuildDir** 전역 변수를 정의합니다. 각 구성에서 변수를 사용하여 해당 구성에 대한 **buildRoot** 속성 값을 지정합니다. 또한 각 구성에서 **inheritEnvironments** 속성을 사용하여 해당 구성에만 적용되는 변수를 지정하는 방법도 참조하세요.

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x86 compiler.
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.BuildDir}\\${name}"    },
    {
      "name": "x64-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x64 compiler.
      "inheritEnvironments": [ "msvc_x64" ],
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

다음 예제에서 x86-Debug 구성은 **BuildDir** 속성에 대한 자체 값을 정의하며, 이 값은 전역 **BuildDir** 속성에 설정된 값을 재정의하므로 **BuildRoot**에서 `D:\custom-builddir\x86-Debug`로 평가합니다.

```json
{
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",

      // The syntax for this property is the same as the global one above.
      "environments": [
        {
          // Replace the global property entirely.
          "BuildDir": "D:\\custom-builddir",
        }
      ],

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      // Evaluates to "D:\custom-builddir\x86-Debug"
      "buildRoot": "${env.BuildDir}\\${name}"
    },
    {
      "name": "x64-Debug",

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x64" ], 
      // Since this configuration doesn’t modify BuildDir, it inherits
      // from the one defined globally.
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

## <a name="cmake-configure-step"></a>CMake 구성 단계

CMakeSettings.json 또는 CMakeLists.txt 파일을 크게 변경하면 Visual Studio에서 자동으로 CMake 구성 단계를 다시 실행합니다. 구성 단계가 오류 없이 완료되는 경우 수집된 정보는 C++ IntelliSense 및 언어 서비스와 빌드/디버그 작업에서 사용할 수 있습니다.

여러 CMake 프로젝트에서 동일한 CMake 구성 이름(예: x86-Debug)을 사용하는 경우, 해당 구성을 선택할 때 해당 CMake 프로젝트 모두가 자체 빌드 루트 폴더에 빌드되고 구성됩니다. 해당 CMake 구성에 참여하는 모든 CMake 프로젝트에서 대상을 디버그할 수 있습니다.

   ![CMake 빌드 전용 메뉴 항목](media/cmake-build-only.png "CMake 빌드 전용 메뉴 항목")

빌드 및 디버그 세션을 작업 영역에 있는 프로젝트의 하위 집합으로 제한하려면, 새 구성을 CMakeSettings.json 파일에 고유한 이름으로 만들어 해당 프로젝트에만 적용합니다. 해당 구성을 선택하면 지정된 프로젝트에 대해서만 IntelliSense 및 빌드/디버그 명령이 사용됩니다.

## <a name="troubleshooting-cmake-cache-errors"></a>CMake 캐시 오류 문제 해결

문제를 진단하는 데 CMake 캐시의 상태에 대한 추가 정보가 필요하면, **CMake** 주 메뉴 또는 **솔루션 탐색기**의 상황에 맞는 **CMakeLists.txt** 메뉴를 열어 다음 명령 중 하나를 실행합니다.

- **캐시 보기**는 편집기의 빌드 루트 폴더에서 CMakeCache.txt 파일을 엽니다. 캐시를 정리하면 CMakeCache.txt에 대해 여기서 편집한 내용이 모두 지워집니다. 캐시를 정리한 후에도 계속 변경하려면 이 문서의 앞부분에 나오는 [CMake 설정 및 사용자 지정 구성](#cmake_settings)을 참조하세요.
- **캐시 폴더 열기**는 빌드 루트 폴더에 대한 탐색기 창을 엽니다.  
- **캐시 정리**는 다음 CMake 구성 단계를 정리된 캐시에서 시작하도록 빌드 루트 폴더를 삭제합니다.
- **캐시 생성**은 Visual Studio에서 최신 환경으로 간주하는 경우에도 생성 단계를 강제로 수행합니다.
