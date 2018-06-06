---
title: 심각한 오류 C1083 | Microsoft Docs
ms.custom: ''
ms.date: 09/01/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1083
dev_langs:
- C++
helpviewer_keywords:
- C1083
ms.assetid: 97e52df3-e79c-4f85-8f1e-bbd1057d55e7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b014ccc46434fd0c3f13689e579ed4798ebcdb2
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34569812"
---
# <a name="fatal-error-c1083"></a>심각한 오류 C1083

> 열 수 없습니다 *filetype* 파일: '*파일*': *메시지*

컴파일러는 필요한 파일을 찾을 수 없는 경우 C1083 오류가 발생을 생성 합니다. 이 오류에 대 한 다양 한 원인 있습니다. 잘못 된 포함 검색 경로 또는 없거나 이름이 잘못 지정 된 헤더 파일은 가장 일반적인 원인은 이지만 다른 파일 형식 및 문제 C1083 발생할 수 있습니다. 다음은 몇 가지 일반적인 이유 컴파일러가이 오류를 생성 하는 이유입니다.

## <a name="the-specified-file-name-is-wrong"></a>지정한 파일 이름이 잘못됨

파일 이름이 잘못 입력될 수 있습니다. 예를 들어 개체에 적용된

`#include <algorithm.h>`

원하는 파일을 찾을 수 없습니다. 대부분의 c + + 표준 라이브러리 헤더 파일에.h 파일 확장명이 없는 합니다. \<알고리즘 >이 헤더를 찾을 수는 `#include` 지시문입니다. 이 문제를 해결 하려면 다음이 예제와 같이 올바른 파일 이름을 입력을 확인 합니다.

`#include <algorithm>`

특정 C 런타임 라이브러리 헤더는 표준 포함 디렉터리의 하위 디렉터리에 있습니다. 예를 들어 sys/types.h를 포함 하려면 포함 해야 sys 하위 디렉터리 이름에는 `#include` 지시문:

`#include <sys/types.h>`

## <a name="the-file-is-not-included-in-the-include-search-path"></a>파일 포함 검색 경로에 포함 되지 않습니다.

컴파일러가 `#include` 또는 `#import` 지시문으로 표시되는 검색 규칙을 사용하여 파일을 찾을 수 없습니다. 예를 들어 경우 헤더 파일 이름은 괄호로 묶여 인용 부호

`#include "myincludefile.h"`

그러면 컴파일러가를 먼저 소스 파일을 포함 하는 동일한 디렉터리에 파일을 찾아 빌드 환경에 의해 지정 된 다른 위치를 확인 합니다. 따옴표에 절대 경로가 포함되어 있는 경우 컴파일러는 해당 위치에서만 파일을 찾습니다. 따옴표에 상대 경로가 포함되어 있는 경우 컴파일러는 소스 디렉터리에 관련된 디렉터리에서 파일을 찾습니다.

꺾쇠 괄호에서 이름이 포함 되어 있으면

`#include <stdio.h>`

컴파일러가 빌드 환경에 의해 정의 된 검색 경로 따릅니다는 **/I** 컴파일러 옵션의 **/X** 컴파일러 옵션 및 **INCLUDE** 환경 변수입니다. 파일을 찾는 데 검색 순서에 대 한 특정 세부 정보를 포함 한 자세한 내용은 참조 하십시오. [#include 지시문 (C/c + +)](../../preprocessor/hash-include-directive-c-cpp.md) 및 [#import 지시문](../../preprocessor/hash-import-directive-cpp.md)합니다.

포함 파일 소스 디렉터리에 상대적인 다른 디렉터리에 있으며에 상대 경로 사용 하는 경우 프로그램 지시문이 포함 꺾쇠 괄호 대신 큰따옴표를 사용 해야 합니다. 예를 들어 헤더 파일 myheader.h 헤더 라는 프로젝트 소스 프로그램의 하위 디렉터리에 있으면 다음이 예에서는 파일을 찾지 못하면 않았으며 C1083:

`#include <headers\myheader.h>`

그러나이 예제에서는 동작:

`#include "headers\myheader.h"`

포함 검색 경로에 대 한 디렉터리와 상대 경로 사용할 수도 있습니다. 디렉터리를 추가 하는 경우는 **INCLUDE** 환경 변수 또는 프로그램 **포함 디렉터리** Visual Studio에서 경로 경로 부분에 include 지시문도 추가 하지 마십시오. 예를 들어, 헤더가 \path\example\headers\myheader.h에 \path\example\headers\를를 추가 하 여 **포함 디렉터리** Visual Studio에서 경로 하지만 `#include` 지시문으로 파일을 참조

`#include <headers\myheader.h>`

다음 파일을 찾을 수 없습니다. 올바른 경로 포함 검색 경로에 지정 된 디렉터리에 상대적를 사용 합니다. 이 예제에서는 \path\example로 포함 검색 경로 변경할 수 있습니다\, 에서 headers\ 경로 세그먼트를 제거 하거나는 `#include` 지시문입니다.

## <a name="third-party-library-issues-and-vcpkg"></a>타사 라이브러리 문제 및 Vcpkg

빌드의 일부로 타사 라이브러리를 구성 하려고 시도할 때이 오류를 표시 하는 경우를 사용해 [Vcpkg](../../vcpkg.md), Visual c + + 패키지 관리자를 설치 하 여 라이브러리를 빌드합니다. 크기가 크고 점점 Vcpkg에서는 [타사 라이브러리 목록이](https://github.com/Microsoft/vcpkg/tree/master/ports), 구성 속성 및 프로젝트의 일부분으로 빌드가 성공한 경우에 필요한 종속성을 가져오거나 설정 합니다. 자세한 내용은 참조는 관련 [Visual c + + 블로그](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) 게시 합니다.

## <a name="the-file-is-in-your-project-but-not-the-include-search-path"></a>파일이 프로젝트에 있지만 포함 검색 경로에

헤더 파일에 표시 되는 경우에 **솔루션 탐색기** 프로젝트의 일부로 파일을 찾을 수 컴파일러에 의해으로 참조 되는 `#include` 또는 `#import` 지시문에 원본 파일, 및에 검색 경로 포함 합니다. 빌드 종류에 따라 다른 검색 경로가 사용될 수도 있습니다. **/X** 포함 검색 경로에서 디렉터리를 제외 하려면 컴파일러 옵션을 사용할 수 있습니다. 이렇게 하면 각 빌드에서 이름은 같지만 다른 디렉터리에 보관되는 다른 포함 파일을 사용할 수 있습니다. 이는 전처리기 명령을 통한 조건부 컴파일의 대체 방법입니다. 에 대 한 자세한 내용은 **/X** 컴파일러 옵션을 참조 [/X (표준 포함 경로 무시)](../../build/reference/x-ignore-standard-include-paths.md)합니다.

이 문제를 해결하려면 컴파일러가 포함되거나 가져온 파일을 찾는 데 사용하는 경로를 수정합니다. 새 프로젝트 사용 하 여 기본 검색 경로 포함 합니다. 프로젝트에 대 한 디렉터리를 추가할 포함 검색 경로 수정 해야 합니다. 명령줄에서 컴파일하 하는 경우 추가에 대 한 경로 **INCLUDE** 환경 변수 또는 **/I** 컴파일러 옵션을 파일에 경로 지정 합니다.

Visual Studio에서 include 디렉터리 경로 설정 하려면 프로젝트의 열고 **속성 페이지** 대화 상자. 선택 **VC + + 디렉터리** 아래 **구성 속성** 다음 편집 고 왼쪽된 창에는 **포함 디렉터리** 속성입니다. Visual Studio에서 컴파일러에 의해 검색 된 사용자 및-프로젝트 디렉터리에 대 한 자세한 내용은 참조 [VC + + 디렉터리 속성 페이지](../../ide/vcpp-directories-property-page.md)합니다. 에 대 한 자세한 내용은 **/I** 컴파일러 옵션을 참조 [/I (추가 포함 디렉터리)](../../build/reference/i-additional-include-directories.md)합니다.

## <a name="the-command-line-include-or-lib-environment-is-not-set"></a>명령줄 포함 또는 LIB 환경 설정 되지 않았습니다.

명령줄에서 컴파일러를 호출하는 경우 대체로 환경 변수를 사용하여 검색 경로를 지정합니다. 설명 하는 검색 경로 **INCLUDE** 또는 **LIB** 환경 변수가 올바르게 설정 되지 않았습니다., C1083 오류가 생성 될 수 있습니다. 빌드 명령줄에 대 한 기본 환경 설정 하려면 개발자 명령 프롬프트 바로 가기를 사용 하는 것이 좋습니다. 자세한 내용은 참조 하십시오. 참조 [빌드 C/c + + 명령줄에서](../../build/building-on-the-command-line.md)합니다. 환경 변수를 사용 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: 빌드에서 환경 변수를 사용 하 여](/visualstudio/msbuild/how-to-use-environment-variables-in-a-build)합니다.

## <a name="the-file-may-be-locked-or-in-use"></a>파일이 잠겨 있거나 사용 중

다른 프로그램을 편집 하거나 해당 파일에 액세스를 사용 하는 경우 파일이 잠겨 있을 수 있습니다. 다른 프로그램에서 파일을 닫으십시오. 때로는 다른 프로그램 병렬 컴파일 옵션을 사용 하는 경우 Visual Studio 자체에 수 있습니다. 병렬 빌드 옵션을 해제 하는 경우이 문제는 다음 있어서 오류를 하면 됩니다. 다른 병렬 빌드 시스템에서이 문제를 가질 수도 있습니다. 이 빌드 순서가 올바른 파일 및 프로젝트 종속성을 설정 해야 합니다. 경우에 따라 중간 프로젝트를 여러 프로젝트에서 작성 될 수 있습니다는 공통 파일에 대 한 빌드 종속성 순서를 강제로 만들어 하는 것이 좋습니다. 경우에 따라 바이러스 백신 프로그램은 일시적으로 검색을 위해 최근에 변경 된 파일을 잠급니다. 가능 하면 바이러스 백신 검사 프로그램에서 프로젝트 빌드 디렉터리를 제외 하는 것이 좋습니다.

## <a name="the-wrong-version-of-a-file-name-is-included"></a>잘못된 버전의 파일 이름이 포함됨

C1083 오류가 잘못된 버전의 파일이 포함되었음을 나타낼 수도 있습니다. 예를 들어 빌드에서 사용되지 않는 헤더 파일에 대한 `#include` 지시문이 있는 잘못된 버전의 파일이 빌드에 포함되어 있을 수 있습니다. 예를 들어 특정 파일 적용할 수 있습니다만 x86 빌드 또는 디버그 빌드에 있습니다. 헤더 파일을 찾을 수 없는 경우 컴파일러에서 C1083 오류가 발생합니다. 이 문제를 해결하려면 올바른 파일을 사용하고 헤더 파일 또는 디렉터리를 빌드에 추가하지 마십시오.

## <a name="the-precompiled-headers-are-not-yet-precompiled"></a>미리 컴파일된 헤더가 미리 컴파일되지 않았음

프로젝트가 미리 컴파일된 헤더를 사용하도록 구성되어 있는 경우 헤더 콘텐츠를 사용하는 파일이 컴파일될 수 있도록 관련 .PCH 파일을 만들어야 합니다. 예를 들어 stdafx.cpp 파일이 자동으로 새 프로젝트를 프로젝트 디렉터리에 만들어집니다. 먼저 해당 파일을 컴파일하여 미리 컴파일된 헤더 파일을 만듭니다. 일반적인 빌드 프로세스 디자인에서이 자동으로 수행 됩니다. 자세한 내용은 참조 [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)합니다.

## <a name="additional-causes"></a>추가 원인

- SDK 또는 타사 라이브러리를 설치 하지만 SDK 후 새 개발자 명령 프롬프트 창을 열지 않은 또는 라이브러리가 설치 되어 있습니다. SDK 또는 라이브러리 파일을 추가 하는 경우는 **INCLUDE** 경로, 환경 변수 변경 내용이 이러한 새 개발자 명령 프롬프트 창을 열고 해야 할 수 있습니다.

- 하지만 컴파일러 옵션의 관리 되는 코드를 사용 하는 파일 **/clr** 지정 되지 않았습니다. 자세한 내용은 [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하세요.

- 다른을 사용 하 여 파일을 컴파일하 **/analyze** 헤더를 미리 컴파일하는 데 사용 된 컴파일러 옵션 설정입니다. 프로젝트에 대 한 헤더는 미리 컴파일된 경우 모든 사용 해야 동일한 **/analyze** 설정 합니다. 자세한 내용은 [/analyze(코드 분석)](../../build/reference/analyze-code-analysis.md)를 참조하세요.

- 파일 또는 디렉터리 Windows 하위 시스템에서 Linux 용, 디렉터리별 대/소문자 구분을 사용 하도록 설정 만들어졌으며 경로 또는 파일의 지정 된 경우 경로 또는 디스크에 파일의 경우 일치 하지 않습니다.

- 파일, 디렉터리 또는 디스크가 읽기 전용입니다.

- Visual Studio 또는 명령줄 도구 없는 파일 또는 디렉터리를 읽을 수 있는 권한이 충분 합니다. 예를 들어 프로젝트 파일이 Visual Studio 또는 명령줄 도구를 실행 하는 프로세스 보다 서로 다른 소유권이 갖고 있으면이 오류가 발생할 수 있습니다. 경우에 따라 관리자 권한으로 Visual Studio 또는 개발자 명령 프롬프트를 실행 하 여이 문제를 해결할 수 있습니다.

- 파일 핸들이 충분하지 않습니다. 일부 응용 프로그램을 닫은 후 다시 컴파일하십시오. 이러한 경우는 일반적인 상황에서 거의 발생하지 않습니다. 하지만 실제 메모리가 제한된 컴퓨터에서 큰 프로젝트를 빌드하는 경우 발생할 수 있습니다.

## <a name="example"></a>예

다음 예제에서는 C1083 오류가 발생 하는 경우 헤더 파일 `"test.h"` 포함 검색 경로에 또는 소스 디렉터리에 존재 하지 않습니다.

```cpp
// C1083.cpp
// compile with: /c
#include "test.h"   // C1083 test.h does not exist
#include "stdio.h"  // OK
```

IDE 또는 명령줄에서 C/c + + 프로젝트를 빌드하는 방법에 대 한 정보 및 환경 변수를 설정 하는 방법에 대 한 정보에 대 한 참조 [C/c + + 프로그램 빌드](../../build/building-c-cpp-programs.md)합니다.

## <a name="see-also"></a>참고자료

- [MSBuild 속성](/visualstudio/msbuild/msbuild-properties)
