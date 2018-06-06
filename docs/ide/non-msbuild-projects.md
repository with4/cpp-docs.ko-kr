---
title: Visual C++의 폴더 열기 프로젝트 | Microsoft Docs
ms.custom: ''
ms.date: 08/02/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Open Folder Projects in Visual C++
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0fe4eba09f06b987ab11f35429e13796fe6baafb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337287"
---
# <a name="open-folder-projects-in-visual-c"></a>Visual C++의 폴더 열기 프로젝트
Visual Studio 2017에는 소스 파일의 폴더를 열고 IntelliSense, 검색, 리팩터링, 디버깅 등의 지원을 통해 코딩을 즉시 시작할 수 있는 "폴더 열기" 기능이 도입되었습니다. .sln 또는 .vcxproj 파일이 로드되지 않습니다. 필요한 경우 간단한 .json 파일을 통해 매개 변수를 작성하고 시작할 수 있을 뿐만 아니라 사용자 지정 작업을 지정할 수도 있습니다. 폴더 열기로 구동되는 Visual C++는 이제 느슨한 파일 모음뿐만 아니라 CMake, Ninja, QMake(Qt 프로젝트 용), gyp, SCons, Gradle, Buck, make 등을 포함한 모든 빌드 시스템도 지원할 수 있습니다. 

폴더 열기를 사용하려면 주 메뉴에서 *파일 | 열기 | 폴더*를 차례대로 선택하거나 *Ctrl +Shift+Alt+O*를 누릅니다. 솔루션 탐색기에서 폴더의 모든 파일이 즉시 표시됩니다. 파일을 클릭하여 편집을 시작할 수 있습니다. 백그라운드에서 Visual Studio는 IntelliSense, 탐색 및 리팩터링 기능을 사용할 수 있도록 파일 인덱싱을 시작합니다. 파일을 편집, 생성, 이동 또는 삭제하면 Visual Studio는 변경 내용을 자동으로 추적하고 해당 IntelliSense 인덱스를 계속해서 업데이트합니다. 
  
## <a name="cmake-projects"></a>CMake 프로젝트
CMake는 C++ 데스크톱 워크로드의 구성 요소인 Visual C++용 CMake 도구로 Visual Studio IDE에 통합되어 있습니다. 자세한 내용은 [Visual C++용 CMake 도구](cmake-tools-for-visual-cpp.md)를 참조하세요.
 
## <a name="qmake-projects-that-target-the-qt-framework"></a>Qt 프레임워크를 대상으로 하는 QMake 프로젝트
Visual C++용 CMake 도구를 사용하여 Qt를 대상으로 하는 Qt 프로젝트를 만들거나 Qt Visual Studio 확장을 사용할 수 있습니다. 참고: 2017년 8월 현재, [Visual Studio 2017용 Qt Visual Studio 확장 지원](https://download.qt.io/development_releases/vsaddin/)은 베타 버전으로 사용할 수 있습니다.

## <a name="gyp-cons-scons-buck-etc"></a>gyp, Cons, SCons, Buck 등
Visual C++에서 모든 빌드 시스템을 사용할 수 있으며 Visual C++ IDE 및 디버거의 장점을 이용할 수 있습니다. 프로젝트의 루트 폴더를 열면 Visual C++에서 추론을 사용하여 IntelliSense 및 검색 대상인 소스 파일을 인덱싱합니다. CppProperties.json 파일을 편집하여 코드 구조에 대한 힌트를 제공할 수 있습니다. 이와 비슷한 방식으로 launch.vs.json 파일을 편집하여 빌드 프로그램을 구성할 수 있습니다. 

## <a name="configuring-open-folder-projects"></a>폴더 열기 프로젝트 구성
3개의 JSON 파일을 통해 폴더 열기 프로젝트를 사용자 지정할 수 있습니다.
|||
|-|-|
|CppProperties.json|검색에 대한 사용자 지정 구성 정보를 지정합니다. 필요한 경우 이 파일을 루트 프로젝트 폴더에 만듭니다.|
|launch.vs.json|명령줄 인수를 지정합니다. **솔루션 탐색기**의 상황에 맞는 메뉴 항목 **디버그 및 시작 설정**을 통해 액세스합니다.|
|tasks.vs.json|사용자 지정 빌드 명령 및 컴파일러 스위치를 지정합니다. **솔루션 탐색기**의 상황에 맞는 메뉴 항목 **작업 구성**을 통해 액세스합니다.|

### <a name="configure-intellisense-with-cpppropertiesjson"></a>CppProperties.json으로 IntelliSense 구성
IntelliSense 및 검색 동작은 #include 경로, 컴파일러 스위치 및 다른 매개 변수를 정의하는 활성 빌드 구성에 따라 부분적으로 다릅니다. 기본적으로 Visual Studio는 디버그 및 릴리스 구성을 제공합니다. 일부 프로젝트의 경우 IntelliSense 및 검색 기능에서 코드를 완전히 인식할 수 있도록 사용자 지정 구성을 만드는 것이 좋습니다. 새 구성을 정의하려면 루트 폴더에 CppProperties.json이라는 파일을 만듭니다. 예를 들면 다음과 같습니다.

```json
{
  "configurations": [
    {
      "name": "Windows x64",
      "includePath": [ "include" ],
      "defines": [ "_DEBUG" ],
      "compilerSwitches": "/std:c++17",
      "intelliSenseMode": "msvc-x64",
      "forcedInclude": [ "pch.h" ],
      "undefines": []
    }
  ]
}
```
구성에는 다음 속성 중 하나가 있을 수 있습니다.

|||  
|-|-| 
|`name`|C++ 구성 드롭다운에 표시되는 구성 이름|
|`includePath`|include 경로에 지정해야 하는 폴더 목록(대부분의 컴파일러에서 /I에 매핑됨)|
|`defines`|정의해야 하는 매크로 목록(대부분의 컴파일러에서 /D에 매핑됨)|
|`compilerSwitches`|IntelliSense 동작에 영향을 줄 수 있는 하나 이상의 추가 스위치|
|`forcedInclude`|모든 컴파일 단위에 자동으로 포함될 헤더(MSVC에서 /FI에 매핑되거나 clang에서 -include에 매핑됨)|
|`undefines`|정의되지 않은 매크로 목록(MSVC에서 /U에 매핑됨)|
|`intelliSenseMode`|사용할 IntelliSense 엔진. MSVC, gcc 또는 Clang에 대한 아키텍처 특정 변형을 지정할 수 있습니다.
- msvc-x86(기본값)
- msvc-x64
- msvc-arm
- windows-clang-x86
- windows-clang-x64
- windows-clang-arm
- Linux-x64
- Linux-x86
- Linux-arm
- gccarm

#### <a name="environment-variables"></a>환경 변수
CppProperties.json은 include 경로 및 다른 속성 값에 대한 시스템 환경 변수 확장을 지원합니다. 구문은 `%FOODIR%` 환경 변수를 확장하는 `${env.FOODIR}`입니다. 다음 시스템 정의 변수도 지원됩니다.

|변수 이름|설명|  
|-----------|-----------------|
|vsdev|기본 Visual Studio 환경|
|msvc_x86|x86 도구를 사용하여 x86용으로 컴파일|
|msvc_arm|x86 도구를 사용하여 ARM용으로 컴파일|
|msvc_arm64|x86 도구를 사용하여 ARM64용으로 컴파일|
|msvc_x86_x64|x86 도구를 사용하여 AMD64용으로 컴파일|
|msvc_x64_x64|64비트 도구를 사용하여 AMD64용으로 컴파일|
|msvc_arm_x64|64비트 도구를 사용하여 ARM용으로 컴파일|
|msvc_arm64_x64|64비트 도구를 사용하여 ARM64용으로 컴파일|

Linux 워크로드가 설치되면 원격으로 Linux 및 WSL을 대상으로 지정하는 데 사용할 수 있는 환경은 다음과 같습니다.

|변수 이름|설명|  
|-----------|-----------------|
|linux_x86|원격으로 x86 Linux를 대상 지정|
|linux_x64|원격으로 x64 Linux를 대상 지정|
|linux_arm|원격으로 ARM Linux를 대상 지정|

사용자 지정 환경 변수는 CppProperties.json에서 전역으로 또는 구성별로 정의할 수 있습니다. 다음 예제에서는 기본 및 사용자 지정 환경 변수를 선언하고 사용하는 방법을 보여 줍니다. 전역 **environments** 속성은 모든 구성에서 사용할 수 있는 **INCLUDE**라는 변수를 선언합니다.

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\\src\\includes"
    }
  ],
 
  "configurations": [
    {
      "inheritEnvironments": [
        // Inherit the MSVC 32-bit environment and toolchain.
        "msvc_x86"
      ],
      "name": "x86",
      "includePath": [
        // Use the include path defined above.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "msvc-x86"
    },
    {
      "inheritEnvironments": [
        // Inherit the MSVC 64-bit environment and toolchain.
        "msvc_x64"
      ],
      "name": "x64",
      "includePath": [
        // Use the include path defined above.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "msvc-x64"
    }
  ]
}
```
또한 구성 내에 **environments** 속성을 정의하여 해당 구성에만 적용하고 동일한 이름의 전역 변수를 재정의할 수 있습니다. 다음 예제에서 x64 구성은 전역 값을 재정의하는 지역 **INCLUDE** 변수를 정의합니다.

```json
{
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\\src\\includes"
    }
  ],
 
  "configurations": [
    {
      "inheritEnvironments": [
        "msvc_x86"
      ],
      "name": "x86",
      "includePath": [
        // Use the include path defined in the global environments property.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "msvc-x86"
    },
    {
      "environments": [
        {
          // Append 64-bit specific include path to env.INCLUDE.
          "INCLUDE": "${env.INCLUDE};${workspaceRoot}\\src\\includes64"
        }
      ],
 
      "inheritEnvironments": [
        "msvc_x64"
      ],
      "name": "x64",
      "includePath": [
        // Use the include path defined in the local environments property.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "msvc-x64"
    }
  ]
}
```

모든 custom 및 default 환경 변수는 tasks.vs.json 및 launch.vs.json에서도 사용할 수 있습니다.

#### <a name="macros"></a>매크로
CppProperties.json 내에서 액세스할 수 있는 기본 제공 매크로는 다음과 같습니다.
|||
|-|-|
|`${workspaceRoot}`| 작업 영역 폴더의 전체 경로|
|`${projectRoot}`| CppProperties.json이 있는 폴더의 전체 경로|
|`${vsInstallDir}`| 실행되는 VS 2017 인스턴스가 설치된 폴더의 전체 경로|

예를 들어 프로젝트에 include 폴더가 있고 windows.h 및 Windows SDK의 다른 일반 헤더가 포함되어 있으면, CppProperties.json 구성 파일을 다음과 같은 include로 업데이트할 수 있습니다.

```json
{
  "configurations": [
    {
      "name": "Windows",
      "includePath": [
        // local include folder
        "${workspaceRoot}\\include",
        // Windows SDK and CRT headers
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\ucrt",
        "${env.NETFXSDKDir}\\include\\um",
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\um",
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\shared",
        "${env.VCToolsInstallDir}include"
      ]
    }
  ]
}
```

**참고:** `%WindowsSdkDir%` 및 `%VCToolsInstallDir%`는 전역 환경 변수로 설정되지 않으므로 devenv.exe는 이러한 변수를 정의하는 "VS 2017용 개발자 명령 프롬프트"에서 시작해야 합니다.

include 경로 누락으로 인한 IntelliSense 오류 문제를 해결하려면, **오류 목록**을 열고, 출력을 "IntelliSense 전용" 및 E1696 오류 코드("소스 파일을 열 수 없습니다. ...")로 필터링합니다. 

CppProperties.json에서 임의 개수의 구성을 만들 수 있습니다. 각 구성은 드롭다운에 표시됩니다.

```json
{
  "configurations": [
    {
      "name": "Windows",
      ...
    },
    {
      "name": "with EXTERNAL_CODECS",
      ...
    }
  ]
}
```
### <a name="define-tasks-with-tasksvsjson"></a>tasks.vs.json으로 작업 정의
현재 작업 영역에 있는 파일에 대한 빌드 스크립트 또는 기타 외부 작업을 IDE에서 직접 작업으로 실행하여 자동화할 수 있습니다. 파일 또는 폴더를 마우스 오른쪽 단추로 클릭하고 **작업 구성**을 선택하여 새 작업을 구성할 수 있습니다. 

![폴더 열기 구성 작업](media/open-folder-config-tasks.png)

이 작업은 Visual Studio에서 루트 프로젝트 폴더에 만드는 .vs 폴더에서 `tasks.vs.json` 파일을 만들거나 엽니다. 이 파일에서 임의의 작업을 정의한 다음, 상황에 맞는 **솔루션 탐색기** 메뉴에서 호출할 수 있습니다. 다음 예제에서는 단일 작업을 정의하는 tasks.vs.json 파일을 보여 줍니다. `taskName`은 상황에 맞는 메뉴에 표시되는 이름을 정의합니다. `appliesTo`는 명령을 수행할 수 있는 파일을 정의합니다. `command` 속성은 콘솔에 대한 경로(Windows의 경우 cmd.exe)를 식별하는 COMSPEC 환경 변수를 참조합니다. CppProperties.json 또는 CMakeSettings.json에 선언된 환경 변수를 참조할 수도 있습니다. `args` 속성은 호출할 명령줄을 지정합니다. `${file}` 매크로는 **솔루션 탐색기**에서 선택한 파일을 검색합니다. 다음 예제에서는 현재 선택된 .cpp 파일의 파일 이름을 표시합니다.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskName": "Echo filename",
      "appliesTo": "*.cpp",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": ["echo ${file}"]
    }
  ]
}
```
tasks.vs.json이 저장되면 폴더의 .cpp 파일을 마우스 오른쪽 단추로 클릭하고, 상황에 맞는 메뉴에서 **Echo filename(파일 이름 화면 표시)** 을 선택하여 [출력 창]에 표시된 파일 이름을 확인할 수 있습니다.



#### <a name="appliesto"></a>appliesTo
`appliesTo` 필드에 이름을 지정하여 모든 파일 또는 폴더에 대한 작업을 만들 수 있습니다(예: `"appliesTo" : "hello.cpp"`). 다음 파일 마스크를 값으로 사용할 수 있습니다.
|||
|-|-|
|`"*"`| 작업 영역의 모든 파일 및 폴더에서 작업을 사용할 수 있음|
|`"*/"`| 작업 영역의 모든 폴더에서 작업을 사용할 수 있음|
|`"*.cpp"`| 작업 영역에서 확장명이 .cpp인 모든 파일에 작업을 사용할 수 있음|
|`"/*.cpp"`| 작업 영역 루트에서 확장명이 .cpp인 모든 파일에 작업을 사용할 수 있음|
|`"src/*/"`| "src" 폴더의 모든 하위 폴더에 작업을 사용할 수 있음|
|`"makefile"`| 작업 영역의 모든 메이크파일 파일에 작업을 사용할 수 있음|
|`"/makefile"`| 작업 영역 루트의 메이크파일에만 작업을 사용할 수 있음|

#### <a name="output"></a>출력
`output` 속성을 사용하여 **F5** 키를 누르면 시작할 실행 파일을 지정합니다. 예:

```json
      "output": "${workspaceRoot}\\bin\\hellomake.exe" 
```

#### <a name="macros-for-tasksvsjson"></a>tasks.vs.json의 매크로

|||
|-|-|
|`${env.<VARIABLE>}`| 개발자 명령 프롬프트에 대해 설정된 환경 변수(예: ${env.PATH}, ${env.COMSPEC} 등)를 지정합니다. 자세한 내용은 [Visual Studio용 개발자 명령 프롬프트](/dotnet/framework/tools/developer-command-prompt-for-vs)를 참조하세요.|
|`${workspaceRoot}`| 작업 영역 폴더의 전체 경로(예: "C:\sources\hello")|
|`${file}`| 이 작업을 실행하기 위해 선택한 파일 또는 폴더의 전체 경로(예: "C:\sources\hello\src\hello.cpp")|
|`${relativeFile}`| 파일 또는 폴더의 상대 경로(예: "src\hello.cpp")|
|`${fileBasename}`| 경로 또는 확장명이 없는 파일 이름(예: "hello")|
|`${fileDirname}`| 파일 이름을 제외한 파일의 전체 경로(예: "C:\sources\hello\src")|
|`${fileExtname}`| 선택한 파일의 확장명(예: ".cpp")|

#### <a name="custom-macros"></a>사용자 지정 매크로
tasks.vs.json에서 사용자 지정 매크로를 정의하려면 작업 블록 앞에 이름:값 쌍을 추가합니다. 다음 예제에서는 `args` 속성에서 사용되는 `outDir`이라는 매크로를 정의합니다.

```json
{
"version": "0.2.1",
  "outDir": "${workspaceRoot}\\bin",
  "tasks": [
    {
      "taskName": "List outputs",
      "*",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": [
        "dir ${outDir}"
      ]
    }
  ]
```

### <a name="configure-debugging-parameters-with-launchvsjson"></a>launch.vs.json으로 디버깅 매개 변수 구성
프로그램의 명령줄 인수를 사용자 지정하려면 **솔루션 탐색기**에서 실행 파일을 마우스 오른쪽 단추로 클릭하고 **디버그 및 시작 설정**을 선택합니다. 이렇게 하면 기존 `launch.vs.json` 파일이 열리거나, 이 파일이 없는 경우 선택한 프로그램에 대한 정보가 미리 채워진 새 파일이 만들어집니다. 

추가 인수를 지정하려면 다음 예제와 같이 `args` JSON 배열에 추가합니다.

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "project": "CPP\\7zip\\Bundles\\Alone\\O\\7za.exe",
      "name": "7za.exe list content of helloworld.zip",
      "args": [ "l", "d:\\sources\\helloworld.zip" ]
    }
  ]
}
```

이 파일을 저장하면 [디버그 대상] 드롭다운에 새 구성이 표시되고 이 구성을 선택하여 디버거를 시작할 수 있습니다. 실행 파일의 개수에 관계없이 원하는 만큼 많은 수의 디버그 구성을 만들 수 있습니다. 이제 **F5** 키를 누르면 디버거가 시작되고 이미 설정한 모든 중단점에 적중됩니다. 그리고 친숙한 모든 디버거 창과 해당 기능을 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목
[IDE 및 Visual C++ 개발 도구](ide-and-tools-for-visual-cpp-development.md)

