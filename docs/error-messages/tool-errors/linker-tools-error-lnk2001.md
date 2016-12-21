---
title: "링커 도구 오류 LNK2001 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2001"
ms.assetid: dc1cf267-c984-486c-abd2-fd07c799f7ef
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK2001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"symbol" 외부 기호를 확인할 수 없습니다.  
  
 링커가 라이브러리 및 개체 파일에서 찾을 수 없는 함수, 변수 또는 레이블을 코드가 참조합니다.  
  
 이 오류 메시지 다음에 심각한 오류인 [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md)이 옵니다.  
  
 **가능한 원인**  
  
-   관리되는 라이브러리 또는 웹 서비스 프로젝트를 Visual C\+\+ 2003에서 업그레이드하면 **명령줄** 속성 페이지에 **\/Zl** 컴파일러 옵션이 추가됩니다.  이로 인해 LNK2001이 발생합니다.  
  
     이 오류를 해결하려면 msvcrt.lib 및 msvcmrt.lib를 링커의 추가 종속성 속성에 추가하거나  **명령줄** 속성 페이지에서 **\/Zl**을 제거합니다.  자세한 내용은 [\/Zl\(기본 라이브러리 이름 생략\)](../../build/reference/zl-omit-default-library-name.md) 및 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
-   코드가 요청하는 항목이 없습니다. 예를 들어, 기호의 철자가 잘못되었거나 기호에 잘못된 대\/소문자가 사용된 경우입니다.  
  
-   코드가 잘못된 항목을 요청했습니다. 예를 들어, 서로 다른 버전의 제품에서 라이브러리를 조금씩 가져와 혼합된 버전의 라이브러리를 사용하고 있습니다.  
  
 **특정 원인**  
  
 **코딩 문제**  
  
-   LNK2001 진단 텍스트에서 `__check_commonlanguageruntime_version`이 확인되지 않은 외부 기호라고 보고할 경우 이를 해결하는 방법에 대한 자세한 내용은 [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)를 참조하십시오.  
  
-   멤버 템플릿 정의가 클래스 외부에 있습니다.  Visual C\+\+에서는 멤버 템플릿을 포함 클래스 내부에 완전히 정의해야 합니다.  LNK2001 및 멤버 템플릿에 대한 자세한 내용은 기술 자료 문서 Q239436을 참조하십시오.  
  
-   코드 또는 모듈 정의\(.def\) 파일에서 대\/소문자가 일치하지 않으면 LNK2001이 발생할 수 있습니다.  예를 들어, 한 C\+\+ 소스 파일에 `var1` 변수를 명명한 다음 다른 파일에서 이 변수를 `VAR1`으로 액세스하려는 경우입니다.  
  
-   [함수 인라이닝](../../error-messages/tool-errors/function-inlining-problems.md)을 사용하는 프로젝트가 헤더 파일 대신에 .cpp 파일에 함수를 정의하면 LNK2001이 발생할 수 있습니다.  
  
-   `extern` "C"를 사용하지 않고 C\+\+ 프로그램에서 C 함수를 호출하면 컴파일러가 C 명명 규칙을 사용하게 되므로 LNK2001이 발생할 수 있습니다.  컴파일러 옵션 [\/Tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) 및 [\/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)를 사용하면 컴파일러가 파일 확장명에 관계없이 파일을 C\+\+ 또는 C로 컴파일합니다.  이러한 옵션으로 인해 함수 이름이 예상했던 이름과 달라질 수 있습니다.  
  
-   외부 링크를 사용하지 않는 데이터 또는 함수를 참조하려고 하면 LNK2001이 발생할 수 있습니다.  C\+\+에서 `extern`으로 명시적으로 지정되지 않은 인라인 함수 및 `const` 데이터는 내부 링크를 사용합니다.  
  
-   [함수 본문 또는 변수 누락](../../error-messages/tool-errors/missing-function-body-or-variable.md)으로 인해 LNK2001이 발생할 수 있습니다.  함수 프로토타입이나 `extern` 선언을 사용하면 컴파일러가 오류 발생 없이 작업을 계속할 수 있지만, 예약된 변수 공간이나 함수 코드가 없으므로 링커가 변수의 참조나 주소에 대한 호출을 확인할 수 없습니다.  
  
-   함수 선언에 있는 매개 변수 형식과 일치하지 않는 매개 변수 형식을 사용하는 함수를 호출하면 LNK2001이 발생할 수 있습니다.  [이름 데코레이션](../../error-messages/tool-errors/name-decoration.md)은 함수의 매개 변수를 최종으로 데코레이팅된 함수 이름에 포함시킵니다.  
  
-   잘못 포함된 프로토타입으로 인해, 컴파일러가 제공되지 않는 함수 본문을 기대하는 경우에는 LNK2001이 발생할 수 있습니다.  `F` 함수에 대한 클래스 구현과 비클래스 구현을 모두 사용하는 경우에는 C\+\+ 범위 결정 규칙에 유의하십시오.  
  
-   C\+\+를 사용할 때 클래스 정의에 함수 프로토타입을 포함시키고 해당 클래스에 대한 함수의 [구현을 포함](../../error-messages/tool-errors/missing-function-body-or-variable.md)시키지 못하면 LNK2001이 발생할 수 있습니다.  
  
-   추상 기본 클래스의 생성자나 소멸자에서 순수 가상 함수를 호출하려고 하면 LNK2001이 발생할 수 있습니다.  순수 가상 함수에서는 기본 클래스가 구현되지 않습니다.  
  
-   함수 범위에 속하지 않는 함수\([지역 변수](../../error-messages/tool-errors/automatic-function-scope-variables.md)\) 내에 선언된 변수를 사용하려고 하면 LNK2001이 발생할 수 있습니다.  
  
-   ATL 프로젝트의 릴리스 버전을 빌드할 경우에는 CRT 시작 코드가 필요한지 여부를 표시해야 합니다.  이를 해결하려면 다음 중 하나를 수행하십시오.  
  
    -   전처리기 목록에서 `_ATL_MIN_CRT`를 제거하면 CRT 시작 코드를 포함할 수 있도록 정의됩니다.  자세한 내용은 [일반 구성 설정 속성 페이지](../../ide/general-property-page-project.md)를 참조하십시오.  
  
    -   가능하다면 CRT 시작 코드를 필요로 하는 CRT 함수에 대한 호출을 제거하고  대신에 Win32 동등 항목을 사용하십시오.  예를 들어, `strcmp` 대신 `lstrcmp`를 사용합니다.  CRT 시작 코드를 필요로 한다고 알려진 함수에는 몇몇 문자열 함수와 부동 소수점 함수가 있습니다.  
  
 **컴파일 및 링크 문제**  
  
-   프로젝트에 라이브러리 파일\(.LIB\) 또는 개체 파일\(.OBJ\)에 대한 참조가 없습니다.  자세한 내용은 [링커 입력 파일로 사용하는 .lib 파일](../../build/reference/dot-lib-files-as-linker-input.md)을 참조하십시오.  
  
-   [\/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) 또는 [\/Zl](../../build/reference/zl-omit-default-library-name.md)을 사용하는 경우 필요한 코드가 들어 있는 라이브러리를 명시적으로 포함하지 않으면 해당 라이브러리가 프로젝트에 링크되지 않습니다. **\/clr** 또는 **\/clr:pure**를 사용하여 컴파일하는 경우 .cctor에 대한 참조가 표시됩니다. 자세한 내용은 [혼합형 어셈블리 초기화](../../dotnet/initialization-of-mixed-assemblies.md)를 참조하십시오.  
  
-   유니코드 및 MFC를 사용하는 경우 `wWinMainCRTStartup`에 대한 진입점을 만들지 않으면 `_WinMain@16`에 대해 확인할 수 없는 외부 참조가 생성됩니다. [\/ENTRY](../../build/reference/entry-entry-point-symbol.md)를 사용하십시오.  [유니코드 프로그래밍 요약](../../text/unicode-programming-summary.md)을 참조하십시오.  
  
     자세한 내용은 MSDN Library에서 다음 기술 자료 문서를 참조하십시오.  MSDN Library에서 **검색** 탭을 클릭하고 입력란에 문서 번호나 문서 제목을 붙여넣은 다음 **항목 나열**을 클릭합니다.  문서 번호를 검색하는 경우에는 **제목만 검색** 옵션의 선택을 취소해야 합니다.  
  
    -   Q125750   "PRB: Error LNK2001: '\_WinMain@16': Unresolved External Symbol"  
  
    -   Q131204   "PRB: Wrong Project Selection Causes LNK2001 on \_WinMain@16"  
  
    -   Q100639   "Unicode Support in the Microsoft Foundation Class Library"  
  
    -   Q291952   "PRB: Link Error LNK2001: Unresolved External Symbol \_main"  
  
-   \/MT로 컴파일한 코드를 LIBC.lib 라이브러리와 링크시키면 `_beginthread`, `_beginthreadex`, `_endthread` 및 `_endthreadex`에 대해 LNK2001이 발생합니다.  
  
-   다중 스레드 라이브러리를 필요로 하는 코드\(MFC 코드 또는 [\/MT](../../build/reference/md-mt-ld-use-run-time-library.md)로 컴파일한 코드\)를 링크시키면 [\_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md), `_beginthreadex`, [\_endthread](../../c-runtime-library/reference/endthread-endthreadex.md) 및 `_endthreadex`에 대해 LNK2001이 발생합니다.  자세한 내용은 다음 기술 자료 문서를 참조하십시오.  
  
    -   Q126646 "PRB: Error Msg: LNK2001 on \_\_beginthreadex and \_\_endthreadex"  
  
    -   Q128641 "INFO: \/Mx Compiler Options and the LIBC, LIBCMT, MSVCRT Libs"  
  
    -   Q166504 "PRB: MFC and CRT Must Match in debug\/release and static\/dynamic"  
  
-   **\/MD**로 컴파일하는 경우 모든 런타임이 DLL 내에 있으므로 소스의 "func"에 대한 참조가 개체의 "`__imp__func`" 참조로 됩니다.  정적 라이브러리 LIBC.lib 또는 LIBCMT.lib에 링크하려고 하면 `__imp__func`에 대해 LNK2001이 발생합니다.  \/MD 없이 컴파일하는 경우에 MSVCxx.lib에 링크하려고 하면, 항상 LNK2001이 발생하지는 않지만 다른 문제가 발생할 수 있습니다.  
  
-   응용 프로그램의 디버그 버전을 빌드할 때 릴리스 모드 라이브러리에 링크하면 LNK2001이 발생할 수 있습니다.  마찬가지로, **\/Mxd** 옵션\(**\/MTd** 또는 **\/MDd**\)을 사용하거나 `_DEBUG`를 정의한 다음 릴리스 라이브러리에 링크하면 특히 확인할 수 없는 외부 참조 문제가 발생할 수 있습니다.  릴리스 모드 빌드를 디버그 라이브러리와 링크시키는 경우에도 유사한 문제가 발생합니다.  
  
-   혼합 버전의 Microsoft 라이브러리 및 컴파일러 제품에는 문제가 있을 수 있습니다.  새로운 컴파일러 버전의 라이브러리에는 이전 버전에 포함된 라이브러리에는 없었던 새 기호가 포함될 수 있습니다.  검색 경로에서 디렉터리의 순서를 변경할 수 있으며 또한 디렉터리를 변경하여 현재 버전을 가리키도록 할 수도 있습니다.  
  
     도구 &#124; 옵션 &#124; 프로젝트 &#124; VC\+\+ 디렉터리 대화 상자의 라이브러리 파일 선택 영역에서 검색 순서를 변경할 수 있습니다.  프로젝트의 속성 페이지 대화 상자에 있는 링커 폴더에 만료된 경로를 포함할 수도 있습니다.  
  
     이 문제는 새로운 SDK가 다른 위치에 설치되는 경우에 발생할 수 있으며 검색 순서가 새 위치를 가리키도록 업데이트되지 않습니다.  일반적으로 새로운 SDK의 포함 및 라이브러리 디렉터리에 대한 경로는 기본 Visual C\+\+ 위치 앞쪽에 둡니다.  또한 포함된 경로를 포함하는 프로젝트는 유효한 경로이긴 하지만 다른 위치에 설치된 새 버전에 의해 추가된 새로운 기능에 대해 만료된 이전 경로를 가리키기도 합니다.  
  
-   현재, 컴파일러 공급업체 간에 또는 다른 버전의 컴파일러 간에 [C\+\+ 이름 지정](../../error-messages/tool-errors/name-decoration.md)에 대한 표준이 없습니다.  따라서 다른 컴파일러로 컴파일한 개체 파일을 링크하면 동일한 명명 스키마를 생성할 수 없으므로 오류 LNK2001이 발생합니다.  
  
-   서로 다른 모듈에서 [인라인과 비인라인 컴파일 옵션을 혼합](../../error-messages/tool-errors/function-inlining-problems.md)하면 LNK2001이 발생할 수 있습니다.  함수 인라이닝은 설정\(**\/Ob1** 또는 **\/Ob2**\)했지만 함수를 설명하는 해당 헤더 파일이 인라이닝을 해제한 상태\(`inline` 키워드 없음\)에서 C\+\+ 라이브러리를 만들면 이 오류가 발생합니다.  이 문제를 방지하려면 다른 파일에 포함시킬 헤더 파일에서 `inline`을 사용하여 인라인 함수를 정의하십시오.  
  
-   `#pragma inline_depth` 컴파일러 지시문을 사용하는 경우에는 [2 이상의 값을 설정](../../error-messages/tool-errors/function-inlining-problems.md)해야 하며 [\/Ob1](../../build/reference/ob-inline-function-expansion.md) 또는 [\/Ob2](../../build/reference/ob-inline-function-expansion.md) 컴파일러 옵션을 사용해야 합니다.  
  
-   리소스 전용 DLL을 만들 때 LINK 옵션 \/NOENTRY를 생략하면 LNK2001이 발생합니다.  
  
-   잘못된 \/SUBSYSTEM 또는 \/ENTRY 설정을 사용하면 LNK2001이 발생할 수 있습니다.  예를 들어, 문자 기반의 응용 프로그램\(콘솔 응용 프로그램\)을 작성하고 \/SUBSYSTEM:WINDOWS를 지정한 경우에는 `WinMain`에 대해 확인할 수 없는 외부 참조가 생성됩니다.  이러한 옵션 및 진입점에 대한 자세한 내용은 [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) 및 [\/ENTRY](../../build/reference/entry-entry-point-symbol.md) 링커 옵션을 참조하십시오.  
  
 **내보내기 문제**  
  
-   16비트 응용 프로그램을 32비트 또는 64비트 응용 프로그램으로 이식하면 LNK2001이 발생할 수 있습니다.  현재 모듈 정의\(.def\) 파일 구문에서는 `__cdecl`, `__stdcall` 및 `__fastcall` 함수가 EXPORTS 섹션에 밑줄 없이 데코레이팅되지 않고 표시되어야 합니다.  이 구문은 16비트 구문과 다릅니다. 16비트 구문에서는 함수에 밑줄이 표시되어야 합니다\(데코레이팅됨\).  자세한 내용은 모듈 정의 파일의 [EXPORTS](../../build/reference/exports.md) 섹션에 대한 설명을 참조하십시오.  
  
-   .def 파일에 표시된 내보내기를 찾지 못하면 LNK2001이 발생합니다.  이 오류는 내보내기가 없거나 내보내기의 철자가 잘못되었거나 내보내기가 C\+\+ 데코레이팅된 이름을 사용\(.def 파일은 데코레이팅된 이름을 사용하지 않음\)하기 때문에 발생할 수 있습니다.  
  
 **결과 해석**  
  
 기호를 확인할 수 없는 경우에는 다음 지침에 따라 함수에 대한 정보를 가져올 수 있습니다.  
  
 x86 플랫폼의 경우, C에서 컴파일된 이름에 대한 호출 규칙 데코레이션 또는 C\+\+에서의 extern "C" 이름에 대한 호출 규칙 데코레이션은 다음과 같습니다.  
  
 `__cdecl`  
 함수에 밑줄\(\_\) 접두사가 옵니다.  
  
 `__stdcall`  
 함수에 밑줄\(\_\) 접두사 및 @ 접미사가 오며 뒤이어 스택에서의 매개 변수에 대한 dword 맞춤 크기가 옵니다.  
  
 `__fastcall`  
 함수에 @ 접두사 및 @ 접미사가 오며 뒤이어 스택에서의 매개 변수에 대한 dword 맞춤 크기가 옵니다.  
  
 undname.exe를 사용하여 데코레이팅된 이름의 데코레이팅되지 않은 형식을 가져오십시오.  
  
 위에서 설명한 몇 가지 원인에 대한 자세한 내용은 [이름 데코레이션](../../error-messages/tool-errors/name-decoration.md)을 참조하십시오.