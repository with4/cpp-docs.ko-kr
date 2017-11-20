---
title: "vcpkg-- Windows용 C++ 패키지 관리자 | Microsoft Docs"
description: "vcpkg는 Windows에서 오픈 소스 C++ 라이브러리 획득 및 설치를 크게 간소화하는 명령줄 패키지 관리자입니다."
keywords: vcpkg
author: mikeblome
ms.author: mblome
ms.date: 05/30/2017
ms.technology: cpp-ide
ms.tgt_pltfrm: windows
ms.assetid: f50d459a-e18f-4b4e-814b-913e444cedd6
ms.topic: article
dev_langs: C++
manager: ghogen
ms.openlocfilehash: de5825e64abac210561cb8cbe0dc3320a740cbee
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="vcpkg-c-package-manager-for-windows"></a>vcpkg: Windows용 C++ 패키지 관리자 
vcpkg는 Windows에서 타사 라이브러리 획득 및 설치를 크게 간소화하는 명령줄 패키지 관리자입니다. 프로젝트에서 타사 라이브러리를 사용하는 경우 vcpkg를 사용하여 설치하는 것이 좋습니다. vcpkg는 오픈 소스와 독점 라이브러리를 모두 지원합니다. vcpkg 공용 카탈로그의 모든 라이브러리가 Visual Studio 2015 및 Visual Studio 2017과의 호환성 테스트를 거쳤습니다. 2017년 5월 현재 카탈로그에는 238개 이상의 라이브러리가 있으며 C++ 커뮤니티는 지속해서 더 많은 라이브러리를 추가하고 있습니다.

## <a name="simple-yet-flexible"></a>단순하면서도 유연한
하나의 명령으로 소스를 다운로드하고 라이브러리를 구축할 수 있습니다. vcpkg는 그 자체가 GitHub에서 사용할 수 있는 오픈 소스 프로젝트입니다. 예를 들어 다른 라이브러리 또는 공용 카탈로그에서 발견되는 것과는 다른 버전의 라이브러리를 지정하여 원하는 방식으로 개인 클론을 사용자 지정할 수 있습니다. 단일 컴퓨터에서 각각 라이브러리 및/또는 컴파일 스위치의 사용자 지정 집합을 생성하는 vcpkg 클론을 여러 개 지정할 수 있습니다. 각 복제본은 자체 계층에서만 작동하는 vcpkg.exe의 자체 복사본을 가진 완전히 독립적이고 x 복사 가능한 환경입니다. vcpkg는 어떤 환경 변수에도 추가되지 않으며 Windows 레지스트리 또는 Visual Studio에 종속되지 않습니다.

## <a name="sources-not-binaries"></a>소스는 이진 파일 아님
공용 카탈로그에 있는 라이브러리의 경우 vcpkg는 이진 파일[1] 대신 소스를 다운로드합니다. 이것은 Visual Studio 2017 또는 Visual Studio 2015(2017이 설치되지 않은 경우)를 사용하여 해당 소스를 컴파일합니다. C++에서는 사용하는 라이브러리가 연결된 응용 프로그램 코드와 동일한 컴파일러 및 컴파일러 버전을 사용하여 컴파일되어야 합니다. Vcpkg를 사용하여 이진 파일 불일치 및 이로 인해 발생할 수 있는 문제를 제거하거나 적어도 크게 줄일 수 있습니다. 특정 버전의 Visual C++ 컴파일러에서 표준화된 팀에서는 한 팀 구성원이 vcpkg를 사용하여 소스를 다운로드하고 이진 파일 집합을 컴파일한 다음 내보내기 명령을 사용하여 이진 파일과 헤더를 압축하여 다른 팀 구성원에게 내보낼 수 있습니다. 자세한 내용은 컴파일된 이진 파일 및 헤더 내보내기를 참조하세요. 

포트 컬렉션에 있는 개인 라이브러리로 vcpkg 클론을 만들면 미리 작성된 이진 파일 및 헤더를 다운로드 하는 포트를 추가하고 원하는 위치로 해당 파일을 간단히 복사하는 portfile.cmake 파일을 작성할 수 있습니다.

[1] *참고: 일부 독점 라이브러리에서는 소스를 사용할 수 없습니다. Vcpkg는 이러한 경우에 호환되는 미리 작성된 이진 파일을 다운로드합니다.*

## <a name="installation"></a>설치
vcpkg 리포지토리를 GitHub: https://github.com/Microsoft/vcpkg에서 복제합니다. 원하는 폴더 위치에 다운로드할 수 있습니다.

루트 폴더에서 부트스트래퍼 bootstrap-vcpkg.bat를 실행합니다.

## <a name="basic-tasks"></a>기본 작업
  
### <a name="search-the-list-of-available-libraries"></a>사용 가능한 라이브러리 목록 검색
사용 가능한 패키지를 보려면 명령 프롬프트에서 다음을 입력합니다. `vcpkg search`

이 명령은 vcpkg/ports 하위 폴더에 제어 파일을 열거합니다. 다음과 같은 목록이 표시됩니다.

```cmd
ace       6.4.3   The ADAPTIVE Communication Environment
anax      2.1.0-1 An open source C++ entity system. <https://github...
antlr4    4.6-1   ANother Tool for Language Recognition
apr       1.5.2   The Apache Portable Runtime (APR) is a C library ...
asio      1.10.8  Asio is a cross-platform C++ library for network ...
assimp    3.3.1   The Open Asset import library
atk       2.24.0  GNOME Accessibility Toolkit
...
```

  한 패턴으로 필터링 할 수 있습니다(예: `vcpkg search ta`).

```cmd
botan       2.0.1      A cryptography library written in C++11
portaudio   19.0.6.00  PortAudio Portable Cross-platform Audio I/O API P...
taglib      1.11.1-2   TagLib Audio Meta-Data Library

```

### <a name="install-a-library-on-your-local-machine"></a>로컬 컴퓨터에 라이브러리 설치
`vcpkg search`를 사용하여 라이브러리 이름을 찾은 다음 `vcpkg install`을 사용하여 라이브러리를 다운로드하고 컴파일합니다. vcpkg는 포트 디렉터리에 있는 라이브러리의 포트 파일을 사용합니다. 세 가지를 지정하지 않으면 Vcpkg는 x86 Windows에 대해 설치 및 컴파일합니다. 포트 파일이 종속성을 지정하는 경우 vcpkg도 이를 다운로드 및 설치합니다. 다운로드 후 vcpkg는 라이브러리가 사용하는 빌드 시스템이면 무엇이든 사용하여 라이브러리를 빌드합니다. CMake 및 MSBuild 프로젝트 파일이 선호되지만 MAKE도 다른 빌드 시스템과 함께 지원됩니다. Vcpkg가 로컬 컴퓨터에서 지정된 빌드 시스템을 찾을 수 없으면 다운로드하여 설치합니다.

```cmd
> vcpkg install boost:x86-windows

The following packages will be built and installed:
    boost:x86-windows
  * bzip2:x86-windows
  * zlib:x86-windows
Additional packages (*) will be installed to complete this operation.
```

### <a name="list-the-libraries-already-installed"></a>이미 설치된 라이브러리 나열
일부 라이브러리를 설치한 후 어떤 라이브러리를 갖고 있는지 `vcpkg list`를 사용하여 확인할 수 있습니다.

```cmd
> vcpkg list

boost:x86-windows       1.64-3   Peer-reviewed portable C++ source libraries
bzip2:x86-windows       1.0.6-1  High-quality data compressor.
cpprestsdk:x86-windows  2.9.0-2  C++11 JSON, REST, and OAuth library The C++ REST ...
openssl:x86-windows     1.0.2k-2 OpenSSL is an open source project that provides a...
websocketpp:x86-windows 0.7.0    Library that implements RFC6455 The WebSocket Pro...
zlib:x86-windows        1.2.11   A compression library
```

### <a name="integrate-with-visual-studio"></a>Visual Studio와 통합
#### <a name="per-user"></a>사용자 단위
`vcpkg integrate install`을 실행하여 VC++ 디렉터리 경로를 수동으로 편집할 필요 없이 사용자 단위로 모든 vcpkg 헤더 파일과 이진 파일을 찾도록 Visual Studio를 구성할 수 있습니다. 클론이 여러 개 있는 경우 이 명령을 실행하는 클론은 새 기본 위치가 됩니다.

그러면 폴더/헤더를 입력하는 것만으로 헤더를 포함할 수 있으며 자동 완성이 도움이 됩니다. 라이브러리에 연결하거나 프로젝트 참조를 추가하는 추가 단계는 필요 없습니다. 다음 그림에서는 Visual Studio가 azure-storage-cpp 헤더를 찾는 방법을 보여 줍니다. vcpkg는 대상 플랫폼으로 분할된 \installed 하위 폴더에 헤더를 배치합니다. 다음 다이어그램에서는 라이브러리의 `/was`에 있는 포함 파일의 목록을 보여 줍니다.

 ![vcpkg Intellisense 통합](media/vcpkg-intellisense.png "vcpkg 및 Intellisense")  

#### <a name="per-project"></a>프로젝트 단위
활성 vcpkg 인스턴스의 버전과 다른 라이브러리의 특정 버전을 사용해야 할 경우 새 vcpkg 클론을 만들고 필요한 버전을 가져오도록 라이브러리의 포트 파일을 수정한 다음 `vcpkg install <library>`를 실행할 수 있습니다. 그런 다음에는 `vcpkg integrate project`를 사용하여 프로젝트 단위로 해당 라이브러리를 참조하는 NuGet 패키지를 만들 수 있습니다.

### <a name="export-compiled-binaries-and-headers"></a>컴파일된 이진 파일 및 헤더 내보내기
모든 팀 구성원이 라이브러리를 다운로드 및 빌드해야 한다면 비효율적일 것입니다. 한 구성원만 해당 작업을 수행한 다음 `vcpkg export`를 사용하여 이진 파일 및 헤더의 Zip 파일을 만들어 다른 팀 구성원이 쉽게 공유하도록 만들 수 있습니다. 

### <a name="update-installed-libraries"></a>설치된 라이브러리 업데이트
공용 카탈로그는 라이브러리의 최신 버전으로 최신 상태로 유지됩니다. 로컬 라이브러리 중 어떤 것이 오래되었는지 확인하려면 `vcpkg update`를 사용합니다. 포트 컬렉션을 공용 카탈로그의 최신 버전으로 업데이트할 준비가 되면 github 리포지토리에 대해 git 풀 작업을 수행하거나 새 클론을 만들고 아직 필요한 이전 클론은 유지하면 됩니다.

### <a name="contribute-new-libraries"></a>새 라이브러리 제공
원하는 모든 라이브러리를 개인 포트 컬렉션에 포함할 수 있습니다. 공용 카탈로그에 대한 새 라이브러리를 제안하려면 


### <a name="remove-a-library"></a>라이브러리를 제거합니다.
`vcpkg remove`를 입력하여 설치된 라이브러리를 제거합니다. 종속된 라이브러리가 있는 경우 모든 다운스트림 라이브러리가 제거되는 `--recurse`를 사용하여 명령을 다시 실행하라는 메시지가 나타납니다.

### <a name="customize-vcpkg"></a>Vcpkg 사용자 지정
원하는 어떤 방식으로든 vcpkg의 클론을 수정할 수 있습니다. 여러 vcpkg 클론을 만들고 각 클론에서 포트 파일을 수정하여 특정 라이브러리 버전을 구하거나 명령줄 매개 변수를 지정할 수 있습니다. 예를 들어 기업에서 한 개발자 그룹은 한 가지 종속성 집합을 가진 소프트웨어로 작업하고 다른 그룹은 다른 집합으로 작업할 수 있습니다. Vcpkg의 두 클론을 설정하고 필요에 따라 라이브러리 및 컴파일 스위치 등의 버전을 다운로드하도록 각 클론을 수정할 수 있습니다. 

## <a name="the-vcpkg-folder-hierarchy"></a>Vcpkg 폴더 계층 구조
모든 vcpkg 기능 및 데이터는 단일 디렉터리 계층 구조에서 완전히 독립적입니다. 이를 "인스턴스"라고 합니다. 레지스트리 설정 또는 환경 변수는 없습니다. 한 컴퓨터에 Vcpkg의 인스턴스가 얼마든지 있을 수 있으며 서로를 방해하지 않습니다. 

Vcpkg 인스턴스의 내용: 
- buildtrees -- 빌드된 각 라이브러리의 소스의 하위 폴더를 포함합니다.
- docs -- 문서 및 예제
- downloads -- 다운로드된 도구 또는 소스의 캐시 복사본. 설치 명령을 실행하면 vcpkg는 여기를 먼저 검색합니다.
- installed -- 설치된 각 라이브러리의 헤더 및 이진 파일을 포함합니다. VIsual Studio와 통합하는 것은 본질적으로 이 폴더를 검색 경로에 추가하는 것입니다.
- packages -- 단계적 설치를 위한 내부 폴더.
- ports -- 카탈로그의 각 라이브러리, 버전 및 다운로드 위치를 설명하는 파일. 필요한 경우 고유한 포트를 추가할 수 있습니다.
- scripts -- vcpkg가 사용하는 스크립트(cmake, powershell).
- toolsrc -- vcpkg 및 관련 구성 요소에 대한 C++ 소스 코드
- triplets -- 지원되는 각 대상 플랫폼(예: x86-windows 또는 x64-uwp)에 대한 설정을 포함합니다.

## <a name="command-line-reference"></a>명령줄 참조
- vcpkg search [pat]        빌드 가능한 패키지 검색
- vcpkg install <pkg>...    패키지 설치
- vcpkg remove <pkg>...  패키지 제거
- vcpkg remove -- 오래 된  오래 된 패키지를 모두 제거
- vcpkg list            설치된 패키지 나열
- vcpkg update          업데이트할 패키지 목록 표시
- vcpkg hash <file> [alg]    특정 알고리즘에 따라 파일 해시, 기본 SHA512
- vcpkg integrate install       설치된 패키지를 누구나 사용할 수 있도록 만듭니다. 처음 사용할 때 관리자 권한 필요
- vcpkg integrate remove        사용자 수준의 통합 제거
- vcpkg integrate project        개별 VS 프로젝트 사용을 위한 참조 nuget 패키지 생성
- vcpkg export <pkg>... [opt]...    패키지 내보내기
- vcpkg edit <pkg>      편집을 위해 포트 열기(%EDITOR% 사용, 기본 ‘코드’)
- vcpkg import <pkg>        미리 빌드된 라이브러리 가져오기
- vcpkg create <pkg> <url>   [archivename]        새 패키지 만들기
- vcpkg owns <pat>      설치된 패키지에서 파일 검색
- vcpkg cache           컴파일된 캐시 패키지 나열
- vcpkg version         버전 정보 표시
- vcpkg contact         피드백을 보낼 연락처 정보 표시

### <a name="options"></a>옵션:
  **`--triplet <t>`** 대상 아키텍처 세 개를 지정합니다. (기본값: `%VCPKG_DEFAULT_TRIPLET%`, `vcpkg help triplet` 참조)

  **`--vcpkg-root <path>`**Vcpkg 루트 디렉터리 지정(기본값: `%VCPKG_ROOT%`)
