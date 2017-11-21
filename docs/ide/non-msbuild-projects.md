---
title: "Visual c + +에서 프로젝트 폴더를 열고 | Microsoft Docs"
ms.custom: 
ms.date: 08/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Open Folder Projects in Visual C++
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: da81f8731be97c69a73eddb96e9e56e49c59c91b
ms.sourcegitcommit: 1b480aa74886930b3bd0435d71cfcc3ccda36424
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="open-folder-projects-in-visual-c"></a>Visual c + +에서 폴더 프로젝트 열기
Visual Studio 2017 소스 파일의 폴더를 열고 즉시 IntelliSense, 검색, 리팩터링, 디버깅을 지원 하 여 코딩을 시작 및 등을 사용할 수 있는 "폴더 열기" 기능을 소개 합니다. .Sln 또는.vcxproj 파일이 로드 됩니다. 필요에 따라 빌드 및 간단한.json 파일을 통해 매개 변수를 시작 하는 것은 물론 사용자 지정 작업을 지정할 수 있습니다. 열려 있는 폴더에서 구동, Visual c + + 이제 지원할 수 파일의 느슨한 컬렉션 뿐만 아니라도 거의 모든 빌드 시스템을 CMake, 등 닌자, QMake (하 프로젝트)의 경우, gyp, SCons, Gradle, 프로세스, 만들기. 

열려 있는 폴더를 사용 하려면 주 메뉴에서 선택 *파일 | 열기 | 폴더* 하거나 키를 눌러 *Ctrl + Shift + Alt + O*합니다. 솔루션 탐색기는 즉시 폴더에 있는 모든 파일을 표시합니다. 편집을 시작할 수 있는 모든 파일을 클릭할 수 있습니다. 백그라운드에서 Visual Studio IntelliSense, 탐색 및 리팩터링 기능을 사용 하도록 설정 하려면 파일을 시작 합니다. 편집, 만들기, 이동 하거나 파일을 삭제, Visual Studio에서 변경 내용을 자동으로 추적 하 고 지속적으로 IntelliSense 해당 항목이 있는 인덱스를 업데이트 합니다. 
  
## <a name="cmake-projects"></a>CMake 프로젝트
CMake Visual c + +, c + + 데스크톱 작업 부하의 구성 요소에 대 한 Visual Studio IDE에서 CMake 도구와 통합 되어 있습니다. 자세한 내용은 참조 [Visual c + +에 대 한 CMake 도구](cmake-tools-for-visual-cpp.md)합니다.
 
## <a name="qmake-projects-that-target-the-qt-framework"></a>Framework를 대상으로 하는 QMake 프로젝트
있습니다 사용 CMake 도구 Visual c + +에 대 한 대상 하 하 프로젝트를 빌드하려면 하거나 하 Visual Studio 확장을 사용할 수 있습니다. 참고: 2017 년 1 년 8 월부터는 [Visual Studio 2017에 대 한 Visual Studio Extension 하 지원](https://download.qt.io/development_releases/vsaddin/) 베타 버전으로 사용할 수 있습니다.

## <a name="gyp-cons-scons-buck-etc"></a>gyp, 단점, SCons, 프로세스 등
빌드 시스템을 사용 하 여 Visual c + +에서 수 있으며 여전히 Visual c + + IDE 및 디버거의의 장점을 이용할 수 있습니다. 프로젝트의 루트 폴더를 열 때 Visual c + + 휴리스틱을 사용 하 여 IntelliSense 및 검색에 대 한 소스 파일을 인덱싱할 수 있습니다. CppProperties.json 파일을 편집 하 여 코드의 구조에 대 한 힌트를 제공할 수 있습니다. 이와 비슷한 방식으로 launch.vs.json 파일을 편집 하 여 빌드 프로그램을 구성할 수 있습니다. 

## <a name="configuring-open-folder-projects"></a>폴더 열기 프로젝트 구성
세 JSON 파일을 통해 폴더 열기 프로젝트를 사용자 지정할 수 있습니다.
|||
|-|-|
|CppProperties.json|검색에 대 한 사용자 지정 구성 정보를 지정 합니다. 루트 프로젝트 폴더에 필요한 경우이 파일을 만듭니다.|
|launch.vs.json|명령줄 인수를 지정 합니다. 통해 액세스 되는 **솔루션 탐색기** 상황에 맞는 메뉴 항목 **디버그 및 시작 설정을**합니다.|
|tasks.vs.json|사용자 지정 빌드 명령 및 컴파일러 스위치를 지정 합니다. 통해 액세스 되는 **솔루션 탐색기** 상황에 맞는 메뉴 항목 **구성 작업**합니다.|

### <a name="configure-intellisense-with-cpppropertiesjson"></a>IntelliSense CppProperties.json를 사용 하 여 구성
정의 하는 현재 빌드 구성에 따라 달라 집니다 IntelliSense 및 검색 동작이 부분적으로 #include 경로, 컴파일러 스위치 및 다른 매개 변수입니다. 기본적으로 Visual Studio 디버그 및 릴리스 구성을 제공합니다. 일부 프로젝트에 IntelliSense 및 검색 기능이 완벽 하 게 코드를 이해 하기 위해 사용자 지정 구성을 만들려면 할 수 있습니다. 새 구성을 정의 하려면 루트 폴더에 CppProperties.json 라는 파일을 만듭니다. 예를 들면 다음과 같습니다.

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
구성 속성 중 하나를 가질 수 있습니다.

|||  
|-|-| 
|`name`|c + + 구성 드롭다운에 표시 되는 구성 이름|
|`includePath`|포함 경로 (대부분의 컴파일러에 대 한 맵 /I에)에 지정 해야 하는 폴더 목록이|
|`defines`|되어야 하는 매크로의 목록 정의 (대부분의 컴파일러에 대 한 맵을 /D에)|
|`compilerSwitches`|IntelliSense 동작에 영향을 줄 수 있는 하나 이상의 추가 스위치|
|`forcedInclude`|모든 컴파일 단위에 자동으로 포함 될 헤더 (MSVC에 대 한 /FI 매핑됩니다 또는 clang 포함)|
|`undefines`|정의 되지 않은 (MSVC에 대 한 /U를 maps) 되도록 매크로 목록|
|`intelliSenseMode`|사용할 수 있는 IntelliSense 엔진입니다. MSVC gcc 및 Clang에 대 한 특정 나열 되는 아키텍처를 지정할 수 있습니다.
- msvc x86 (기본값)
- msvc x64
- msvc arm
- clang x86
- clang-x64
- windows-clang-arm
- Linux x64
- Linux x86
- Linux-arm
- gccarm

CppProperties.json 지원 환경 변수 확장에 대 한 경로 다른 속성 값을 포함 합니다. 구문은 `${env.FOODIR}` 환경 변수를 확장 하려면 `%FOODIR%`합니다.

이 파일 내의 다음 기본 제공 매크로에 대 한 액세스 구성 요소도 필요.
|||
|-|-|
|`${workspaceRoot}`| 작업 영역 폴더의 전체 경로|
|`${projectRoot}`| CppProperties.json를 배치할 폴더의 전체 경로|
|`${vsInstallDir}`| VS 2017의 실행 중인 인스턴스를 설치한 폴더에 전체 경로|

예를 들어 프로젝트가 포함 폴더가 있으며 windows.h 및 Windows SDK에서 기타 일반적인 헤더도 포함 되어, 하는 경우 이러한 구성 파일을 포함 하 여 CppProperties.json를 업데이트 하는 것이 좋습니다.

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

**참고:** `%WindowsSdkDir%` 및 `%VCToolsInstallDir%` 는 전역 환경 변수 이므로 시작 하는지 확인 "개발자 명령 프롬프트에서 VS 2017에 대 한" 이러한 변수를 정의 하는 devenv.exe로 설정 되지 않습니다.

IntelliSense 문제를 해결 하려면 없는 경우에 발생 한 오류 포함 경로 열고는 **오류 목록** 및 "IntelliSense에만 해당"에 출력을 필터링 하 고 오류 코드 E1696 "열 수 없습니다... 소스 파일"입니다. 

CppProperties.json에 임의 개수의 구성 만들 수 있습니다. 각 구성 드롭다운에 표시 됩니다.

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
### <a name="define-tasks-with-tasksvsjson"></a>Tasks.vs.json 사용 하 여 작업을 정의 합니다.
빌드 스크립트 또는 기타 IDE에서 직접 작업으로이 실행 하 여 현재 작업 영역에 있는 파일에 대해 외부 작업을 자동화할 수 있습니다. 파일 또는 폴더를 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 새 작업을 구성할 수 있습니다 **구성 작업**합니다. 

![작업을 구성 하는 폴더 열기](media/open-folder-config-tasks.png)

이렇게 (만들거나 엽니다)는 `tasks.vs.json` 파일을 Visual Studio 프로젝트 루트 폴더에 만드는.vs 폴더에 있습니다. 이 파일에 임의 작업을 정의 하 고 다음에서 호출 수는 **솔루션 탐색기** 상황에 맞는 메뉴입니다. 다음 예제에서는 단일 작업을 정의 하는 tasks.vs.json 파일을 보여 줍니다. `taskName`상황에 맞는 메뉴에 표시 되는 이름을 정의 합니다. `appliesTo`명령에서 수행할 수 있는 파일을 정의 합니다. `command` 속성 (Windows에서 cmd.exe) 콘솔에 대 한 경로 식별 하는 COMSPEC 환경 변수를 가리킵니다. `args` 속성 호출할 명령줄을 지정 합니다. `${file}` 매크로에서 선택한 파일을 검색 **솔루션 탐색기**합니다. 다음 예에서는 현재 선택 된.cpp 파일의 파일 이름을 표시 합니다.

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
Tasks.vs.json을 저장 한 후 폴더의 모든.cpp 파일을 마우스 오른쪽 단추로 클릭, 선택할 수 있습니다 **에코 filename** 참조 출력 창에 표시 되는 파일 이름을 확인 하 고 상황에 맞는 메뉴에서 합니다.

#### <a name="appliesto"></a>appliesTo
이름을 지정 하 여 파일이 나 폴더에 대 한 작업을 만들 수 있습니다는 `appliesTo` 예를 들어 필드 `"appliesTo" : "hello.cpp"`합니다. 다음 파일 마스크 값으로 사용할 수 있습니다.
|||
|-|-|
|`"*"`| 작업은 모든 파일 및 폴더 작업 영역에서 사용할 수|
|`"*/"`| 작업은 작업 영역에서 모든 폴더에 사용할 수|
|`"*.cpp"`| 작업은 작업 영역에서 확장명이.cpp 인 파일을 모두 사용할 수 있습니다.|
|`"/*.cpp"`| 작업은 작업 영역 루트에서 확장명이.cpp 인 파일을 모두 사용할 수 있습니다.|
|`"src/*/"`| 작업은 "원본" 폴더의 모든 하위 폴더에 사용할 수|
|`"makefile"`| 작업은 작업 영역에서 모든 메이크파일 파일에 사용할 수|
|`"/makefile"`| 작업은 작업 영역 루트에서 메이크파일에만 사용할 수|

#### <a name="output"></a>출력
사용 하 여는 `output` 를 누를 때 시작 하는 실행 파일을 지정 하는 속성 **F5**합니다. 예:

```json
      "output": "${workspaceRoot}\\bin\\hellomake.exe" 
```

#### <a name="macros-for-tasksvsjson"></a>Tasks.vs.json 매크로

|||
|-|-|
|`${env.<VARIABLE>}`| 모든 환경 변수 (예: ${env 지정합니다. 경로}, {env.COMSPEC} $ 및 기타 등등) 개발자 명령 프롬프트에 대해 설정 된 합니다. 자세한 내용은 참조 [Visual Studio 용 개발자 명령 프롬프트](/dotnet/framework/tools/developer-command-prompt-for-vs)합니다.|
|`${workspaceRoot}`| 작업 영역 폴더 (예: "C:\sources\hello")의 전체 경로|
|`${file}`| 파일 또는 폴더 (예: "C:\sources\hello\src\hello.cpp")에 대해이 태스크를 실행 하기 위해 선택한의 전체 경로|
|`${relativeFile}`| 파일 또는 폴더 (예: "src\hello.cpp")에 상대 경로|
|`${fileBasename}`| 경로 또는 확장명 (예: "hello") 하지 않고 파일의 이름|
|`${fileDirname}`| 파일 이름 (예: "C:\sources\hello\src")을 제외한 파일의 전체 경로|
|`${fileExtname}`| 선택한 파일 (예: ".cpp")의 확장|

#### <a name="custom-macros"></a>사용자 지정 매크로
Tasks.vs.json를 사용자 지정 매크로 정의 하려면 작업 블록 이전 이름: 값 쌍을 추가 합니다. 다음 예제에서는 라는 매크로 정의 `outDir` 에서 사용 하는 `args` 속성:

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

### <a name="configure-debugging-parameters-with-launchvsjson"></a>Launch.vs.json와 디버깅 매개 변수를 구성 합니다.
실행 파일을 마우스 오른쪽 단추로 프로그램의 명령줄 인수를 사용자 지정 하려면 **솔루션 탐색기** 선택 **디버그 및 시작 설정을**합니다. 기존 열립니다 `launch.vs.json` 파일인 하거나 선택한 프로그램에 대 한 정보로 미리 채워졌습니다 새 파일에서 만들 이름이 없는 경우. 

추가 인수를 지정 하려면 추가는 `args` 다음 예제 에서처럼 JSON 배열:

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

이 파일을 저장 하면 새 구성을 디버그 대상 드롭다운 목록에 나타나고 디버거를 시작 하도록 선택할 수 있습니다. 개수에 관계 없이 실행 파일에 대해 원하는 만큼 디버그 구성으로 만들 수 있습니다. 키를 누르면 **F5** 이제 디버거는 실행를 이미 설정한 모든 중단점을 적중 합니다. 모든 친숙 한 디버거 창과 기능은 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목
[IDE 및 Visual C++ 개발 도구](ide-and-tools-for-visual-cpp-development.md)

