---
title: "미리 컴파일된 헤더 파일 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: pch
dev_langs: C++
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- cl.exe compiler, precompiling code
- .pch files, creating
ms.assetid: e2cdb404-a517-4189-9771-c869c660cb1b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 09c436d55ad7087d407ba580be0b63286b056898
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-precompiled-header-files"></a>미리 컴파일된 헤더 파일 만들기
  
Microsoft C 및 C++ 컴파일러는 인라인 코드를 포함하여 모든 C 또는 C++ 코드를 미리 컴파일하는 옵션을 제공합니다. 이 성능 기능을 사용하여 안정적인 코드 본문을 컴파일하고, 코드의 컴파일된 상태를 파일에 저장하고, 후속 컴파일 중 미리 컴파일된 코드와 아직 개발 중인 코드를 결합할 수 있습니다. 안정적인 코드는 다시 컴파일할 필요가 없기 때문에 각 후속 컴파일 속도가 향상됩니다.  
  
이 항목에서는 다음 미리 컴파일된 헤더 주제를 다룹니다.  
  
-   [소스 코드를 미리 컴파일하는 시기](#when-to-precompile-source-code)  
  
-   [코드를 미리 컴파일하기 위한 두 가지 선택 사항](#two-choices-for-precompiling-code)  
  
-   [미리 컴파일된 헤더의 일관성 규칙](#precompiled-header-consistency-rules)  
  
-   [미리 컴파일된 헤더의 파일별 사용에 대한 일관성 규칙](#consistency-rules-for-per-file-use-of-precompiled-headers)  
  
-   [/Yc 및 /Yu에 대 한 일관성 규칙](#consistency-rules-for-yc-and-yu)  
  
-   [프로젝트에 미리 컴파일된 헤더 사용](#using-precompiled-headers-in-a-project)  
  
-   [빌드 프로세스의 PCH 파일](#pch-files-in-the-build-process)  
  
-   [PCH용 샘플 메이크파일](#sample-makefile-for-pch)  
  
-   [PCH에 대한 예제 코드](#example-code-for-pch)  
  
미리 컴파일된 헤더와 관련 된 컴파일러 옵션에 대 한 참조 정보를 참조 하십시오. [/Y (미리 컴파일된 헤더)](../../build/reference/y-precompiled-headers.md)합니다.  
  
<a name="when-to-precompile-source-code"></a>  
  
## <a name="when-to-precompile-source-code"></a>소스 코드를 미리 컴파일하는 시기  
  
미리 컴파일된 코드는 특히 경우 컴파일 시간을 줄이기 위해 개발 주기 동안 유용 합니다.  
  
-   항상 자주 변경 되지 않는 코드의 큰 본문이 사용 합니다.  
  
-   프로그램은 포함 파일 및 동일한 컴파일 옵션의 표준 집합을 사용 하는 여러 모듈을 구성 합니다. 이 경우 모든 포함 파일 하나의 미리 컴파일된 헤더로 미리 컴파일할 수 있습니다.  
  
첫 번째 컴파일-을 미리 컴파일된 헤더 (PCH) 파일을 만드는-후속 컴파일 보다 약간 더 많은 시간이 걸립니다. 미리 컴파일된 코드를 포함 하 여 후속 컴파일 보다 신속 하 게 진행할 수 있습니다.  
  
C 및 c + + 프로그램을 미리 컴파일할 수 있습니다. C + + 프로그래밍에 것이 일반적 헤더 파일로 클래스 인터페이스 정보를 구분 합니다. 나중에 클래스를 사용 하는 프로그램에 이들 헤더 파일을 포함할 수 있습니다. 이러한 헤더를 컴파일하여 프로그램 컴파일하는 데 걸리는 시간을 줄일 수 있습니다.  
  
> [!NOTE]
>  소스 파일 당 하나만 미리 컴파일된 헤더 (.pch) 파일을 사용할 수 있지만 프로젝트에 여러 개의.pch 파일을 사용할 수 있습니다.  
  
<a name="two-choices-for-precompiling-code"></a>  
  
# <a name="two-choices-for-precompiling-code"></a>코드를 미리 컴파일하기 위한 두 가지 선택 사항  
  
Visual c + +, C 또는 c + + 코드; 미리 컴파일할 수 있습니다. 헤더 파일에만 미리 컴파일하도록 제한 되지 않습니다.  
  
계획이 필요 하지만 훨씬 더 빨라집니다 컴파일 더 간단한 헤더 파일이 아닌 소스 코드를 미리 컴파일하는 경우.  
  
코드를 미리 컴파일하 미리 컴파일하는 작업의 소스 코드를 포함 하려는 경우 또는 원본 파일에 헤더 파일의 공통 집합을 사용 하지만 동일한 순서에이 포함 하지 않습니다.  
  
미리 컴파일된 헤더 옵션은 [/Yc (미리 컴파일된 헤더 파일 만들기)](../../build/reference/yc-create-precompiled-header-file.md) 및 [/Yu (미리 컴파일된 헤더 파일 사용)](../../build/reference/yu-use-precompiled-header-file.md)합니다. 사용 하 여 **/Yc** 미리 컴파일된 헤더 만들기. 선택적와 함께 사용할 경우 [hdrstop](../../preprocessor/hdrstop.md) pragma **/Yc** 및 소스 코드를 모두 헤더 파일을 미리 컴파일할 수 있습니다. 선택 **/Yu** 기존 컴파일에서 기존의 미리 컴파일된 헤더를 사용 하도록 합니다. 사용할 수도 있습니다 **/Fp** 와 **/Yc** 및 **/Yu** 미리 컴파일된 헤더에 대 한 대체 이름을 제공 하기 위한 옵션입니다.  
  
컴파일러 옵션 참조 항목에 대 한 **/Yu** 및 **/Yc** 개발 환경에서이 기능에 액세스 하는 방법을 설명 합니다.  
  
<a name="precompiled-header-consistency-rules"></a>  
  
## <a name="precompiled-header-consistency-rules"></a>미리 컴파일된 헤더의 일관성 규칙  
  
PCH 파일 시스템 환경에 대 한 정보와 프로그램에 대 한 메모리 주소 정보를 포함 하므로 만들어진 컴퓨터에서 PCH에 대 한 파일에만 사용 해야 합니다.  
  
<a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>  
  
## <a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>미리 컴파일된 헤더의 파일별 사용에 대한 일관성 규칙

[/Yu](../../build/reference/yu-use-precompiled-header-file.md) 컴파일러 옵션 PCH 파일을 사용 하 여 지정할 수 있습니다.  
  
PCH 파일을 사용 하는 경우 컴파일러 가정 동일한 컴파일 환경-일치 하는 컴파일러 옵션, pragma, 및 등을 사용 하 여 하나-가 별도로 지정 하지 않으면 PCH 파일을 만들 때 적용 된 것입니다. 컴파일러에서 불일치를 감지 하면 경고를 표시 하 고 가능한 경우 일관성 오류를 식별 합니다. 이러한 경고 PCH 파일; 문제가 반드시 단순히 경고할 충돌 합니다. PCH 파일에 대 한 일관성 요구 사항은 다음 섹션에서 설명 합니다.  
  
### <a name="compiler-option-consistency"></a>컴파일러 옵션 일관성  
  
PCH 파일을 사용할 때 다음과 같은 컴파일러 옵션 불일치 경고를 트리거할 수 있습니다.  
  
-   매크로 전처리기를 사용 하 여 만든 (/ D) 옵션 PCH 파일을 만든 컴파일 및 현재 컴파일 간에 동일 해야 합니다. 정의 된 상수 중 상태는 확인 되지 않지만 이러한 변경 하는 경우 예상치 못한 결과가 발생할 수 있습니다.  
  
-   PCH 파일 /E 및 /EP 옵션과 함께 작동 하지 않습니다.  
  
-   PCH 파일 중 하나에서 찾아보기 정보 생성을 사용 하 여 만들어야 (/ FR) 옵션 또는 지역 변수 제외 (/ Fr) 만들어야만 PCH 파일을 사용 하는 후속 컴파일 이러한 옵션을 사용할 수 있습니다.  
  
### <a name="c-70-compatible-z7"></a>C 7.0 호환 (/ Z7)  
  
이 옵션은 적용 PCH 파일을 만들 때, PCH 파일을 사용 하는 후속 컴파일 디버깅 정보를 사용할 수 있습니다.  
  
하는 경우 C 7.0 호환 (/ Z7) 옵션이 적용 되지 않습니다 PCH 파일을 만들 때, 후속 컴파일 PCH 파일 및/z 7을 사용 하는 경고가 발생 합니다. 현재.obj 파일에 디버깅 정보 포함 되며 PCH 파일에 정의 된 로컬 기호는 디버거에서 사용할 수 없습니다.  
  
### <a name="include-path-consistency"></a>포함 경로 일관성  
  
PCH 파일을 만들 때 유효 했던 포함 경로 대 한 내용은 없습니다. PCH 파일을 사용 하면 컴파일러는 항상 현재 컴파일에서 지정 된 포함 경로 사용 합니다.  
  
### <a name="source-file-consistency"></a>소스 파일 일관성  
  
미리 컴파일된 헤더 파일 사용 (/Yu) 옵션을 지정 하면 컴파일러 미리 컴파일될 소스 코드에 나타나는 모든 전처리기 지시문 (pragma 포함)를 무시 합니다. 이러한 전처리기 지시문에 의해 지정 된 컴파일이 미리 컴파일된 헤더 파일 만들기 (/Yc) 옵션에 사용 되는 컴파일과 같아야 합니다.  
  
### <a name="pragma-consistency"></a>Pragma 일관성    
  
일반적으로 파일은 해당 파일을 만드는 동안 처리 된 Pragma 이후에 PCH 파일이 사용 하는 파일을 영향을 줍니다. `comment` 및 `message` pragma는 컴파일의 나머지 부분에서는 영향을 주지 않습니다.  
  
이러한 pragma에서 PCH 파일 내에서 코드를만 영향을 줍니다. 이후에 PCH 파일을 사용 하는 코드에는 영향을 주지 않습니다.  
  
||||  
|-|-|-|  
|`comment`|`page`|`subtitle`|  
|`linesize`|`pagesize`|`title`|  
|`message`|`skip`||  
  
이러한 pragma 미리 컴파일된 헤더의 일부로 유지 되 고 미리 컴파일된 헤더를 사용 하는 컴파일의 나머지 부분에 영향을 줍니다.  
  
||||  
|-|-|-|  
|`alloc_text`|`include_alias`|`pack`|  
|`auto_inline`|`init_seg`|`pointers_to_members`|  
|`check_stack`|`inline_depth`|`setlocale`|  
|`code_seg`|`inline_recursion`|`vtordisp`|  
|`data_seg`|`intrinsic`|`warning`|  
|`function`|`optimize`||  
  
<a name="consistency-rules-for-yc-and-yu"></a>  
  
## <a name="consistency-rules-for-yc-and-yu"></a>/Yc 및 /Yu에 대한 일관성 규칙  
  
/Yc 또는 /Yu를 사용 하 여 만든 미리 컴파일된 헤더를 사용 하면 컴파일러 현재 컴파일 환경 PCH 파일을 만들 때 존재 하는 것을 비교 합니다. 현재 컴파일에 대 한 이전 쿼리와 (일치 하는 컴파일러 옵션, pragma, 및 등을 사용 하 여)와 일치 하는 환경을 지정 해야 합니다. 컴파일러에서 불일치를 감지 하면 경고를 표시 하 고 가능한 경우 일관성 오류를 식별 합니다. 이러한 경고 하지 않는 반드시에 문제가 있는 PCH 파일 단순히 경고할 충돌 합니다. 다음 섹션에는 미리 컴파일된 헤더의 일관성 요구 사항을 설명 합니다.  
  
### <a name="compiler-option-consistency"></a>컴파일러 옵션 일관성  
  
이 표에서 미리 컴파일된 헤더를 사용 하는 경우 불일치 경고를 발생 시킬 수 있는 컴파일러 옵션을 보여 줍니다.  
  
|옵션|name|규칙|  
|------------|----------|----------|  
|/D|상수 및 매크로 정의|미리 컴파일된 헤더를 생성 하는 컴파일 및 현재 컴파일의 사이의 동일 해야 합니다. 정의 된 상수 중 상태는 확인 하지 않지만 파일 변경 된 상수 값에 종속 된 경우 예기치 않은 결과가 발생할 수 있습니다.|  
|/E 또는 /EP|전처리기 출력을 표준 출력에 복사|미리 컴파일된 헤더 /E 또는 /EP 옵션과 함께 작동 하지 않습니다.|  
|/Fr 또는 /FR|Microsoft 소스 브라우저 정보를 생성 합니다.|/Yu 옵션으로 유효 하려면 /Fr 및 /FR 옵션에 대 한 해야 또한 있다가 적용 미리 컴파일된 헤더를 만들 때. 또한 미리 컴파일된 헤더를 사용 하는 후속 컴파일 소스 브라우저 정보를 생성 합니다. 브라우저 정보 단일.sbr 파일에 배치 되 고 동일한 방식으로 CodeView 정보에서 다른 파일에서 참조 됩니다. 소스 브라우저 정보의 배치를 재정의할 수 없습니다.|  
|/ GA, /GD, /GE, /Gw, 또는 /GW|Windows 프로토콜 옵션|미리 컴파일된 헤더를 생성 하는 컴파일 및 현재 컴파일의 사이의 동일 해야 합니다. 이러한 옵션이 서로 다른 경우에 경고 메시지가 발생 합니다.|  
|/ZI|완전 한 디버깅 정보 생성|이 옵션이 미리 컴파일된 헤더를 만들 때 적용 인 경우 사용 하는 후속 컴파일 해당 디버깅 정보를 사용할 수 있습니다. /Zi 적용 되지 않습니다는 미리 컴파일된 헤더를 만들 때, 하는 경우와 /Zi 옵션을 사용 하는 후속 컴파일 경고를 발생 합니다. 현재 개체 파일에 디버깅 정보 포함 되며 미리 컴파일된 헤더에 정의 된 로컬 기호는 디버거에서 사용할 수 없습니다.|  
  
> [!NOTE]
>  미리 컴파일된 헤더 기능은 C 및 c + + 소스 파일에만 사용이 됩니다.  
  
<a name="using-precompiled-headers-in-a-project"></a>  
  
## <a name="using-precompiled-headers-in-a-project"></a>프로젝트에 미리 컴파일된 헤더 사용  
  
미리 컴파일된 헤더의 프로그램 개요를 제공 하는 이전 섹션: /Yc 및 /Yu, /Fp 옵션 및 [hdrstop](../../preprocessor/hdrstop.md) pragma입니다. 이 섹션에서는 프로젝트;에서 수동 미리 컴파일된 헤더 옵션을 사용 하는 방법을 설명합니다 예제 메이크파일 하 고 관리 하는 코드 끝납니다.  
  
프로젝트에 수동 미리 컴파일된 헤더 옵션을 사용 하는 또 다른 방법을 Visual c + +의 기본 설치 중에 만들어진 MFC\SRC 디렉터리에 있는 메이크파일 중 하나를 조사 합니다. 이러한 메이크파일 비슷한 방법으로이 섹션에 제공 된 책갈피로 접근 하지만 Microsoft 프로그램 유지 관리 유틸리티 (NMAKE) 매크로의 사용 및 빌드 프로세스의 큰 제어를 제공 합니다.  
  
<a name="pch-files-in-the-build-process"></a>  
  
## <a name="pch-files-in-the-build-process"></a>빌드 프로세스의 PCH 파일  
  
소프트웨어 프로젝트의 코드 베이스는 일반적으로 여러 C 또는 c + + 소스 파일, 개체 파일, 라이브러리 및 헤더 파일에 포함 됩니다. 일반적으로 메이크파일 실행 파일에 이러한 요소 들의 조합을 조정합니다. 다음 그림은 미리 컴파일된 헤더 파일을 사용 하는 메이크파일의 구조를 보여줍니다. NMAKE 매크로 이름 및이 다이어그램의 파일 이름에 예제 코드에서와 일치는 [PCH 용 샘플 메이크파일](#sample-makefile-for-pch) 및 [PCH에 대 한 예제 코드](#example-code-for-pch)합니다.  
  
그림 3 개의 다이어그램 장치를 사용 하 여 빌드 프로세스의 흐름을 보여 줍니다. 사각형을 나타내는 명명 된 각 파일 또는 매크로입니다. 세 가지 매크로 하나 이상의 파일을 나타냅니다. 음영 처리 된 영역은 각 컴파일 또는 링크 동작을 나타냅니다. 화살표 표시는 파일 및 매크로 컴파일 또는 연결 프로세스 중에 결합 합니다.  
  
![미리 컴파일된 헤더 파일을 사용 하는 메이크파일](../../build/reference/media/vc30ow1.gif "미리 컴파일된 헤더 파일을 사용 하는 메이크파일의 구조")  
##### <a name="structure-of-a-makefile-that-uses-a-precompiled-header-file"></a>미리 컴파일된 헤더 파일을 사용하는 메이크파일의 구조  
  
다이어그램의 위쪽부터, STABLEHDRS와 경계는 모두 NMAKE 매크로 파일 가능성이 적은 컴파일해야를 나열할 수 있습니다. 이러한 파일은 명령 문자열에 의해 컴파일됩니다.  
  
`CL /c /W3 /Yc$(BOUNDRY) applib.cpp myapp.cpp`  
  
미리 컴파일된 헤더 파일 (STABLE.pch) 존재 하지 않는 경우에 또는 두 매크로에 나열 된 파일에 변경 하는 경우. 두 경우 모두 미리 컴파일된 헤더 파일에는 STABLEHDRS 매크로에 나와 있는 파일 에서만에서 코드가 포함 됩니다. 원하는 미리 컴파일된 경계 매크로에 마지막 파일을 나열 합니다.  
  
이 매크로에 나열 하는 파일에는 헤더 파일 또는 C 또는 c + + 소스 파일 일 수 있습니다. (C 및 c + + 모듈로 단일 PCH 파일을 사용할 수 없습니다.) 사용할 수 있는 참고는 **hdrstop** 미리 컴파일 경계 파일 내에서 특정 시점을 중지 하는 매크로입니다. 참조 [hdrstop](../../preprocessor/hdrstop.md) 자세한 정보에 대 한 합니다.  
  
다이어그램, 계속 APPLIB.obj 최종 응용 프로그램에 사용 되는 지원 코드를 나타냅니다. APPLIB.cpp에서 만든, UNSTABLEHDRS 매크로에 나열 된 파일과 미리 컴파일된 코드는 미리 컴파일된 헤더를 합니다.  
  
MYAPP.obj 최종 응용을 프로그램을 나타냅니다. MYAPP.cpp에서 만든, UNSTABLEHDRS 매크로에 나열 된 파일과 미리 컴파일된 코드는 미리 컴파일된 헤더를 합니다.  
  
마지막으로, 실행 파일 (MYAPP 합니다. EXE) OBJS 매크로 (APPLIB.obj 및 MYAPP.obj)에 나열 된 파일에 연결 하 여 만들어집니다.  
  
<a name="sample-makefile-for-pch"></a>  
  
## <a name="sample-makefile-for-pch"></a>PCH용 샘플 메이크파일  
  
다음 메이크파일 매크로 사용 하 고! IF! ELSE! 흐름 제어 명령 구조를 프로젝트에 ENDIF입니다.  
  
```NMAKE  
# Makefile : Illustrates the effective use of precompiled  
#            headers in a project  
# Usage:     NMAKE option  
# option:    DEBUG=[0|1]  
#            (DEBUG not defined is equivalent to DEBUG=0)  
#  
OBJS = myapp.obj applib.obj  
# List all stable header files in the STABLEHDRS macro.  
STABLEHDRS = stable.h another.h  
# List the final header file to be precompiled here:  
BOUNDRY = stable.h  
# List header files under development here:  
UNSTABLEHDRS = unstable.h  
# List all compiler options common to both debug and final  
# versions of your code here:  
CLFLAGS = /c /W3  
# List all linker options common to both debug and final  
# versions of your code here:  
LINKFLAGS = /NOD /ONERROR:NOEXE  
!IF "$(DEBUG)" == "1"  
CLFLAGS   = /D_DEBUG $(CLFLAGS) /Od /Zi /f  
LINKFLAGS = $(LINKFLAGS) /COD  
LIBS      = slibce  
!ELSE  
CLFLAGS   = $(CLFLAGS) /Oselg /Gs  
LINKFLAGS = $(LINKFLAGS)  
LIBS      = slibce  
!ENDIF  
myapp.exe: $(OBJS)  
    link $(LINKFLAGS) @<<  
$(OBJS), myapp, NUL, $(LIBS), NUL;  
<<  
# Compile myapp  
myapp.obj  : myapp.cpp $(UNSTABLEHDRS)  stable.pch  
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    myapp.cpp  
# Compile applib  
applib.obj : applib.cpp $(UNSTABLEHDRS) stable.pch  
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    applib.cpp  
# Compile headers  
stable.pch : $(STABLEHDRS)  
    $(CPP) $(CLFLAGS) /Yc$(BOUNDRY)    applib.cpp myapp.cpp  
```  
  
"구조의 정도 메이크파일을 사용 하는 미리 컴파일된 헤더 파일" 그림에 표시 된 STABLEHDRS, 경계, 및 UNSTABLEHDRS 매크로 외 [빌드 프로세스의 PCH 파일](#pch-files-in-the-build-process),이 메이크파일 CLFLAGS 매크로 및는 LINKFLAGS를 제공 합니다. 매크로입니다. 이러한 매크로 사용 하 여 컴파일러 및 디버그 또는 응용 프로그램의 실행 파일의 최종 버전을 작성 하는지 여부를 적용 하는 링커 옵션을 나열 해야 합니다. 이기도 LIBS 매크로 라이브러리를 나열 하는 위치 프로젝트가 필요 합니다.  
  
메이크파일을 사용 하 여! IF! ELSE! NMAKE 명령줄에서 디버그 기호를 정의 하는지 여부를 검색 하는 ENDIF:  
  
```NMAKE  
NMAKE DEBUG=[1|0]  
```  
  
이 기능을 사용 하면 개발 하는 동안 동일한 메이크파일을 사용 하 고 프로그램의 최종 버전에 대 한-디버그를 사용 하 여 최종 버전에는 0입니다. 다음 명령줄은 동일 합니다.  
  
```NMAKE  
NMAKE   
NMAKE DEBUG=0  
```  
  
메이크파일에 대 한 자세한 내용은 참조 하십시오. [NMAKE 참조](../../build/nmake-reference.md)합니다. 또한 참조 [컴파일러 옵션](../../build/reference/compiler-options.md) 및 [링커 옵션](../../build/reference/linker-options.md)합니다.  
  
<a name="example-code-for-pch"></a>  
  
## <a name="example-code-for-pch"></a>PCH에 대한 예제 코드  
  
다음과 같은 소스 파일에 설명 된 메이크파일에 사용 되 [빌드 프로세스의 PCH 파일](#pch-files-in-the-build-process) 및 [PCH 용 샘플 메이크파일](#sample-makefile-for-pch)합니다. 참고 주석을 중요 한 정보를 포함 합니다.  
  
```cpp  
// ANOTHER.H : Contains the interface to code that is not  
//             likely to change.  
//  
#ifndef __ANOTHER_H  
#define __ANOTHER_H  
#include<iostream>  
void savemoretime( void );  
#endif // __ANOTHER_H  
```  
  
```cpp  
// STABLE.H : Contains the interface to code that is not likely  
//            to change. List code that is likely to change   
//            in the makefile's STABLEHDRS macro.  
//  
#ifndef __STABLE_H  
#define __STABLE_H  
#include<iostream>  
void savetime( void );  
#endif // __STABLE_H  
```  
  
```cpp  
// UNSTABLE.H : Contains the interface to code that is  
//              likely to change. As the code in a header  
//              file becomes stable, remove the header file  
//              from the makefile's UNSTABLEHDR macro and list  
//              it in the STABLEHDRS macro.  
//  
#ifndef __UNSTABLE_H  
#define __UNSTABLE_H  
#include<iostream.h>  
void notstable( void );  
#endif // __UNSTABLE_H  
```  
  
```cpp
// APPLIB.CPP : This file contains the code that implements  
//              the interface code declared in the header  
//              files STABLE.H, ANOTHER.H, and UNSTABLE.H.  
//  
#include"another.h"  
#include"stable.h"  
#include"unstable.h"  
// The following code represents code that is deemed stable and  
// not likely to change. The associated interface code is  
// precompiled. In this example, the header files STABLE.H and  
// ANOTHER.H are precompiled.  
void savetime( void )  
    { cout << "Why recompile stable code?\n"; }  
void savemoretime( void )  
    { cout << "Why, indeed?\n\n"; }  
// The following code represents code that is still under  
// development. The associated header file is not precompiled.  
void notstable( void )  
    { cout << "Unstable code requires"  
            << " frequent recompilation.\n"; 
    }  
```  
  
```cpp
// MYAPP.CPP : Sample application  
//             All precompiled code other than the file listed  
//             in the makefile's BOUNDRY macro (stable.h in  
//             this example) must be included before the file  
//             listed in the BOUNDRY macro. Unstable code must  
//             be included after the precompiled code.  
//  
#include"another.h"  
#include"stable.h"  
#include"unstable.h"  
int main( void )  
{  
    savetime();  
    savemoretime();  
    notstable();  
}  
```  
    
## <a name="see-also"></a>참고 항목  
[C/C++ 빌드 참조](../../build/reference/c-cpp-building-reference.md)   
[컴파일러 옵션](../../build/reference/compiler-options.md)