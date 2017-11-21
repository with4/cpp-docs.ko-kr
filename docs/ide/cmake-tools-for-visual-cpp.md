---
title: "Visual c + +에서 프로젝트 CMake | Microsoft Docs"
ms.custom: 
ms.date: 08/08/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 770b7f70e52859b1489b984d8aef3c3876a9ca83
ms.sourcegitcommit: 1b480aa74886930b3bd0435d71cfcc3ccda36424
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="cmake-projects-in-visual-c"></a>Visual c + +에서 CMake 프로젝트
이 문서에서는 CMake, 여러 플랫폼에서 실행 되는 빌드 프로세스를 정의 하기 위한 플랫폼 간, 오픈 소스 도구에 익숙한 가정 합니다.  

최근까지 Visual Studio를 사용 하 CMake IDE IntelliSense에 대 한 다음 사용, MSBuild 프로젝트 파일을 생성, 검색 및 컴파일입니다. Visual Studio 2017 년부터 **CMake에 대 한 Visual c + + 도구** 구성 요소는 IntelliSense 및 검색을 위해 직접 CMake 프로젝트 파일 (예: CMakeLists.txt) 사용에 대 한 IDE를 사용할 수 있도록 "폴더 열기" 기능을 사용 합니다. Visual Studio 생성기를 사용 하면 임시 프로젝트 파일 생성 되 고 IntelliSense 또는 검색을 목적으로 로드 되지 않습니다는 하지만 msbuild.exe에 전달 합니다. 

**Visual Studio 2017 버전 15.3**: 닌자와 Visual Studio 생성기에 대 한 지원이 제공 됩니다.

**Visual Studio 2017 버전 15.4**: Linux에서 CMake에 대 한 지원이 추가 됩니다. 자세한 내용은 참조 [Linux CMake 프로젝트 구성](../linux/cmake-linux-project.md)합니다.

## <a name="installing"></a>설치
CMake에 대 한 visual c + + 도구는 작업의 c + + 데스크톱 개발의 일부로 기본적으로 설치 됩니다.

![C + + 데스크톱 작업에서 CMake 구성 요소](media/cmake-install.png)
 
## <a name="ide-integration"></a>IDE 통합
선택 하는 경우 **파일 | 열기 | 폴더** CMakeLists.txt 파일이 들어 있는 폴더를 열려면 다음 작업이 수행 됩니다.
- Visual Studio 추가 **CMake** CMake 스크립트 편집 및 보기에 대 한 명령 사용 하 여 주 메뉴에 메뉴 항목입니다. 
- **솔루션 탐색기** 폴더 구조 및 파일을 표시 합니다. 
- Visual Studio CMake.exe를 실행 하 고 기본 CMake 캐시를 생성 *구성*, x86은 디버그 합니다. CMake 명령줄에 표시 됩니다는 **출력 창**, 추가 출력 CMake에서 함께 합니다.
- 백그라운드에서 Visual Studio는 소스 파일을 인덱싱하는 정보를 검색, 리팩터링, IntelliSense를 사용할 수 있도록 하기 시작 합니다. 작업 하는 동안 Visual Studio 편집기를 해당 항목이 있는 인덱스, 소스와 동기화 상태를 유지 하기 위해 디스크에서 변경 내용을 모니터링 합니다. 여러 CMake 프로젝트를 포함 하는 폴더를 열 수 있습니다. Visual Studio 검색 하 고 작업 영역에서 모든 "root" CMakeLists.txt 파일을 구성 합니다. CMake 작업 (구성, 빌드, 디버깅) 뿐만 아니라 c + + IntelliSense 및 검색은 모든 CMake 프로젝트 작업 영역에서 사용할 수 있습니다.

![여러 루트를 사용 하 여 CMake 프로젝트](media/cmake-multiple-roots.png) 

## <a name="building-cmake-projects"></a>CMake 프로젝트 빌드
CMake 프로젝트를 작성 하려면 이러한 선택 옵션이 있습니다.
1. 디버그 드롭다운 및 키를 눌러에서 대상을 선택 **F5** 하거나 "실행" 단추를 클릭 합니다. 프로젝트는 자동으로 빌드 먼저 마찬가지로 Visual Studio 솔루션으로 합니다.
2.  CMakeLists.txt 마우스 오른쪽 단추로 클릭 하 고 상황에 맞는 메뉴에서 빌드를 선택 합니다. 폴더 구조에 대상이 여러 개 있을 경우 모든 또는 하나의 특정 대상 빌드 하도록 선택할 수 있습니다 또는
  
3. 주 메뉴에서 선택 **빌드 | 솔루션 빌드** (**F7** 또는 **Ctrl + Shift + B**) (CMake 대상에 이미 선택 되어 있는지 확인은 **시작 항목** 는 에드롭다운에서**일반** 도구 모음).

![CMake 빌드 메뉴 명령](media/cmake-build-menu.png) 
 
Visual Studio 생성기 활성 구성에 대 한 확인란이 함께 MSBuild.exe가 호출 `-m -v:minimal` 인수입니다. CMakeSettings.json 파일 내 빌드 사용자 지정 하려면 빌드 시스템을 통해에 전달할 추가 명령줄 인수를 지정할 수 있습니다는 `buildCommandArgs` 속성:

```json
"buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
```
빌드 결과에 표시 됩니다, 예상 된 **출력 창** 및 **오류 목록**합니다.
 
![CMake 빌드 오류](media/cmake-build-errors.png)

여러 빌드 대상이 있는 폴더에 CMake 메뉴 또는 빌드에 어떤 CMake 대상을 지정 하려면 CMakeLists.txt 상황에 맞는 메뉴에서 빌드 항목을 선택할 수 있습니다. 키를 누르면 **Ctrl + Shift + B** 프로젝트는 CMake에서 현재 활성 문서를 작성 합니다. 

## <a name="debugging-the-project"></a>프로젝트 디버깅
CMake 프로젝트를 디버깅 하려면 원하는 구성 및 키를 눌러 선택 **F5**, 하거나 도구 모음에서 [실행] 단추를 누릅니다. 실행 단추에 "시작 항목 선택" 라고 표시 되 면의 아래쪽 화살표를 클릭 하 고 실행 하려면 대상을 선택 합니다. (CMake 프로젝트에서는 "현재 문서" 옵션은.cpp 파일에 대 한 유효 합니다.) 

 ![CMake 실행 단추](media/cmake-run-button.png)

 키를 누르면 **F5** 이전 빌드 이후 변경 된 경우 첫 번째 빌드 프로젝트 됩니다.

## <a name="configuring-cmake-debugging-sessions"></a>CMake 디버깅 세션 구성
모든 실행 CMake 대상 일반 도구 모음에서 시작 항목 드롭다운에 표시 됩니다. 디버깅 세션을 시작 하려면 방금 하나 선택한 디버거를 시작 합니다.

 ![CMake 시작 항목 드롭다운](media/cmake-startup-item-dropdown.png)

또한 CMake 메뉴에서 디버그 세션을 시작할 수 있습니다.

프로젝트의 모든 실행 CMake 대상에 대 한 디버거 설정을 사용자 지정 하려면 특정 CMakeLists.txt 파일을 마우스 오른쪽 단추로 클릭 하 고 선택 **디버그 및 시작 설정을**CMake 대상 하위 메뉴 라는 파일에서에서 선택 하는 경우 launch.vs.json이 만들어집니다. 이 미리 선택한 CMake 대상에 대 한 정보로 채워진 파일과 프로그램 인수 또는 디버거 형식이 같은 추가 매개 변수를 지정할 수 있습니다. 아무 키나 CMakeSettings.json 파일에서을 참조 하려면 명령 앞에 "cmake."와 launch.vs.json에. 다음 예제에서는 현재 선택 된 구성에 대 한 CMakeSettings.json 파일에 "remoteCopySources" 키의 값에 가져오는 간단한 launch.vs.json 파일을 보여 줍니다.

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
Launch.vs.json 파일을 저장 하면 항목이 새 이름으로 시작 항목 드롭다운에 생성 됩니다. Launch.vs.json 파일을 편집 하 여 임의 개수의 CMake 대상에 대해 원하는 만큼 디버그 구성으로 만들 수 있습니다.

**Visual Studio 2017 버전 15.4**: Launch.vs.json CMakeSettings.json (아래 참조)의 선언 된 변수를 지원 합니다. 또한는 "currentDir", 시작 응용 프로그램의 현재 디렉터리로 설정의 독립 프로세스:

```json
{
"type": "default",
"project": "CMakeLists.txt",
"projectTarget": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"name": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"currentDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}"
}
```
응용 프로그램의 값을 실행 하면 `currentDir` 은 

```cmd
C:\Users\satyan\7f14809a-2626-873e-952e-cdf038211175\
```
 

## <a name="editing-cmakeliststxt-files"></a>CMakeLists.txt 파일 편집
파일 CMakeLists.txt 파일을 편집 하려면 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택 **열려**합니다. 파일을 변경한 경우 노란색 상태 표시줄이 나타나고 IntelliSense 업데이트 되며와 업데이트 작업을 취소할 수 있도록 사용자에 게 알려줍니다. CMakeLists.txt에 대 한 정보를 참조 하십시오.는 [CMake 설명서](https://cmake.org/documentation/)합니다.

  ![CMakeLists.txt 파일 편집](media/cmake-cmakelists.png)

파일을 저장 하는 즉시 구성 단계 자동으로 다시 실행 되며 출력 창에 정보를 표시 합니다. 오류와 경고가 오류 목록 또는 출력 창에 표시 됩니다. CMakeLists.txt에 잘못 된 줄으로 이동 하 여 오류 목록에 있는 오류를 두 번 클릭 합니다.

  ![CMakeLists.txt 파일 오류](media/cmake-cmakelists-error.png)
 
## <a name="cmake_settings"></a>CMake 설정 및 사용자 지정 구성
기본적으로 Visual Studio는 6 개의 기본 CMake 구성 ("x86 디버그", "x86 릴리스", "x64 디버그", "x64-릴리스", "Linux 디버그" 및 "Linux 릴리스")을 제공합니다. 이러한 구성은 지정된 된 프로젝트에 대 한 CMake 캐시를 만드는 데 CMake.exe은 호출 하는 방법을 정의 합니다. 를 이러한 구성을 수정 하거나 새 사용자 지정 구성을 선택 **CMake | CMake 설정을 변경**에 설정을 적용할 CMakeLists.txt 파일을 선택 합니다. CMake 설정 변경에는 파일의 상황에 맞는 메뉴에서 사용할 수 있는 이기도 **솔루션 탐색기**합니다. 이 명령은 프로젝트 폴더의 CMakeSettings.json 파일을 만듭니다. 이 파일은 다시 만들려고 CMake 캐시 파일을 예를 들어 "정리" 작업이 완료 된 후 사용 합니다. 

  ![설정 변경에 대 한 CMake 주 메뉴 명령](media/cmake-change-settings.png)
 
JSON IntelliSense CMakeSettings.json 파일을 편집할 수 있습니다.

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png)

다음 예제에서는 CMakeSettings.json에서 직접 만들 시작 지점으로 사용할 수 있는 예제 구성을에서는 보여 줍니다.
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
1.  이름: c + + 구성 드롭다운 목록에 나타나는 이름입니다. 이 속성 값이 매크로로 사용할 수도 있습니다 `${name}` 다른 속성 값을 지정 합니다. 예를 들어 CMakeSettings.json에 "buildRoot" 정의 참조 합니다.
2.  생성기:-G 스위치에 매핑되고 사용할 생성자를 지정 합니다. 매크로로이 속성을 사용할 수도 있습니다 `${generator}` 다른 속성 값을 지정할 수 있도록 합니다. Visual Studio는 현재 다음 CMake 생성기를 지원합니다.
    - "닌자"
    - "Visual Studio 2015 14"
    - "Visual Studio 2015 14 ARM"
    - "Visual Studio 2015 14 Win64"
    - "Visual Studio 15 2017"
    - "Visual Studio 15 2017 팔"
    - "Visual Studio 15 2017 Win64"
    - 
닌자 유연성 및 기능 대신 빠른 빌드 속도 디자인 하기 때문에 기본적으로 설정 됩니다. 그러나 일부 CMake 프로젝트 올바르게 닌자를 사용 하 여 만들 수 수 있습니다. 이 경우 대신 Visual Studio 프로젝트를 생성 하려면 CMake 지시할 수 있습니다. 

Visual Studio 생성기를 지정 하려면는 CMakeSettings.json 주 메뉴에서 선택 하 여 열 **CMake | CMake 설정 변경**합니다. "닌자"를 삭제 하 고 "V"를 입력 합니다. 원하는 생성자를 선택할 수 있습니다는 IntelliSense를 활성화 합니다.
3.  buildRoot:-DCMAKE_BINARY_DIR 스위치에 매핑하고 CMake 캐시를 만들 위치를 지정 합니다. 폴더가 생성 됩니다.
4.  변수:-Dname로 전달 되는 CMake 변수의 이름과 값 쌍이 포함 되어 = CMake 하는 값입니다. CMake 프로젝트 빌드 지침 CMake 캐시 파일에 직접 변수를 추가 데이터를 지정 하 여 추가한 여기 대신 것이 좋습니다.
5.  cmakeCommandArgs: CMake.exe에 전달 하려는 추가 스위치를 지정 합니다.
6.  configurationType: 선택한 생성기에 대 한 빌드 구성 유형을 정의 합니다. 현재 지원 되는 값은 "Debug", "MinSizeRel", "릴리스" 및 "RelWithDebInfo"입니다.

### <a name="environment-variables"></a>환경 변수
또한 CMakeSettings.json 위에서 언급 한 속성에서 사용 중인 환경 변수를 지원 합니다. 사용 하는 구문은 `${env.FOO}` 환경 변수 % FOO % 확장 합니다.
이 파일 내의 기본 매크로에 대 한 액세스 구성 요소도 필요.
- `${workspaceRoot}`– 작업 영역 폴더의 전체 경로 제공 합니다.
- `${workspaceHash}`– 작업 영역 위치;의 해시 현재 작업 영역 (예: 폴더 경로에 사용)에 대 한 고유 식별자를 만드는 데 유용
- `${projectFile}`– 루트 CMakeLists.txt 파일의 전체 경로
- `${projectDir}`– 루트 CMakeLists.txt 파일의 폴더의 전체 경로
- `${thisFile}`– CMakeSettings.json 파일의 전체 경로
- `${name}`– 구성의 이름
- `${generator}`-이 구성에 사용 된 CMake 생성기의 이름

### <a name="ninja-command-line-arguments"></a>닌자 명령줄 인수

대상을 지정 하지 않은 경우 'default' 대상을 빌드합니다 (설명서 참조).

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|옵션|설명|  
|--------------|------------|  
| -버전  | 닌자 버전 ("1.7.1")를 인쇄 합니다.| 
|   -C DIR   | 다른 작업을 수행 하기 전에 디렉터리를 변경| 
|   -f 파일  | 빌드 입력된 파일 [default=build.ninja]를 지정 합니다.| 
|   -j N     | N 작업이 동시에 실행할 [기본값 = 사용 가능한 Cpu에서 파생 된 14]| 
|   -k N     | N 작업이 실패 될 때까지 계속 진행 [기본 = 1]| 
|   -l N     | 부하 평균 N 보다 큰 경우 새 작업을 시작 하지 않습니다| 
|   -n      | 실행 드라이 (명령을 실행 하지 마십시오 하지만 성공 처럼 동작)| 
|   -v       | 빌드하는 동안 모든 명령줄 표시| 
|   -d 모드  | 디버깅 (-d 목록에 목록 모드 사용)을 사용 하도록 설정| 
|   -t 도구  | subtool (사용-t 목록에 목록 사용 하위 도구가)를 실행 합니다. toplevel 옵션; 종료 플래그는 도구에 전달 되는 추가| 
|   -w 플래그  | 경고 (-w 목록에 목록 경고 사용)를 조정 합니다.| 


### <a name="inherited-environments-visual-studio-2017-version-155"></a>상속 된 환경 (Visual Studio 2017 15.5 버전)

이제 CmakeSettings.json inherted 환경을 지원합니다. 이 기능을 사용 하는 사용자 지정 변수를 만듭니다.

```json
  "inheritEnvironments": [ "msvc_x64_x64" ]
```

이 필드는 실행 될 때 CMake.exe에 자동으로 전달 되는 변수를 설정 합니다. 위의 예제와 같습니다 실행 "개발자 명령 프롬프트 VS 2017에 대 한"와 `-arch=amd64 -host_arch=amd64` 인수입니다.

다음 표에서 지원 되는 값 및 명령줄 상응 보여 줍니다.

|컨텍스트 이름|설명|  
|-----------|-----------------|
|vsdev|기본 Visual Studio 환경|
|msvc_x86|X86를 사용 하 여 x86 컴파일 도구|
|msvc_arm| X86를 사용 하 여 ARM에 대 한 컴파일 도구|
|msvc_arm64|X86를 사용 하 여 arm64 컴파일 도구|
|msvc_x86_x64|X86를 사용 하 여 AMD64에 대 한 컴파일 도구|
|msvc_x64_x64|64 비트 도구를 사용 하 여 AMD64에 대 한 컴파일|
|msvc_arm_x64|64 비트 도구를 사용 하 여 ARM에 대 한 컴파일|
|msvc_arm64_x64|64 비트 도구를 사용 하 여 arm64 컴파일|


중요 한 변경 사항이 있을 경우 또는 CMakeLists.txt 파일을 Visual Studio는 CMakeSettings.json에 자동으로 CMake를 다시 실행 단계를 구성 합니다. 구성 단계는 오류 없이 완료 되 면 경우 수집 된 정보를 c + + IntelliSense 및 언어 서비스 및 빌드에 사용할 수 작업을 디버그 합니다.

구성 되 고 (자신의 빌드 루트 폴더)에 빌드된 모든 대상 여러 CMake 프로젝트는 동일한 CMake 구성 이름 (예: x86-디버그)을 사용 하는 경우 해당 구성을 선택 하면 됩니다. 모든 해당 CMake 구성에 참여 하는 CMake 프로젝트에서 대상 디버깅할 수 있습니다.

   ![CMake만 빌드 메뉴 항목](media/cmake-build-only.png)

빌드를 제한 하 고 디버그 세션을 작업 영역에서 프로젝트의 하위 집합을 CMakeSettings.json 파일에 고유한 이름으로 새 구성을 만들고 해당 프로젝트에만 적용 합니다. 해당 구성을 경우 IntelliSense, 건물을 선택 하 고 프로젝트를 지정 하는 것에 대해서만 디버깅을 사용할 수는 있습니다.

## <a name="troubleshooting-cmake-cache-errors"></a>CMake 캐시 오류 문제 해결
문제를 진단 하려면 CMake 캐시의 상태에 대 한 자세한 내용은 해야 할 경우 CMake 주 메뉴 또는 CMakeLists.txt 상황에 맞는 메뉴에서 열고 **솔루션 탐색기** 이러한 명령 중 하나를 실행 하려면:
- **캐시를 볼** CMakeCache.txt 파일 편집기에서 빌드 루트 폴더에서 열립니다. (편집한 내용이 여기 CMakeCache.txt에 캐시를 정리 하는 경우 초기화 됩니다. 캐시를 정리 하는 후에 유지 되는 변경 작업을 수행 하려면 참조 [CMake 설정 및 사용자 지정 구성](#cmake_settings) 이 문서의 앞부분에.)
- **캐시 폴더를 열고** 빌드 루트 폴더에 탐색기 창이 열립니다.  
- **캐시를 정리** 다음 CMake 정리 캐시에서 빌드 단계가 구성 빌드 루트 폴더를 삭제 합니다.
- **캐시 생성** Visual Studio 최신 환경을 고려 하는 경우에 실행 하는 생성 단계를 수행 합니다.

