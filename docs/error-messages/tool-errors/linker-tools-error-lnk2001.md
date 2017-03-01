---
title: "링커 도구 오류 LNK2001 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2001
dev_langs:
- C++
helpviewer_keywords:
- LNK2001
ms.assetid: dc1cf267-c984-486c-abd2-fd07c799f7ef
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 9dee257bec0f09bd729bf10c4a1468ecb20dfa61
ms.openlocfilehash: 3629075e5659cb89ab751b011f3ce2cbf89397cc
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk2001"></a>링커 도구 오류 LNK2001
확인 되지 않은 외부 기호 "기호"  
  
 코드는 참조 항목 (예: 함수, 변수 또는 레이블)을 링커에 개체 파일 및 라이브러리에서 찾을 수 없습니다.  
  
 이 오류 메시지 오류가 이어서 [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md)합니다.  
  
 **가능한 원인**  
  
-   관리 되는 라이브러리 또는 웹 서비스 프로젝트를 Visual c + + 2003에서에서 업그레이드 하는 경우는 **/Zl** 컴파일러 옵션에 추가 되는 **명령줄** 속성 페이지. 그러면 LNK2001 있습니다.  
  
     이 오류를 해결 하려면을 추가 하거나 msvcrt.lib 및 msvcmrt.lib 링커의 추가 종속성 속성입니다. 또는 제거 **/Zl** 에서 **명령줄** 속성 페이지. 자세한 내용은 참조 [/Zl (기본 라이브러리 이름 생략)](../../build/reference/zl-omit-default-library-name.md) 및 [프로젝트 속성](../../ide/working-with-project-properties.md)합니다.  
  
-   존재 하지 않는 대 한 코드 요청 (기호는 철자가 잘못 또는 예를 들어 잘못 된 대/소문자를 사용 하 여).  
  
-   코드에서 잘못 된 항목 (사용 하는 다른 버전에서 다른 제품의 한 버전에서 일부 라이브러리의 혼합 된 버전)을 요청 합니다.  
  
 **특정 원인**  
  
 **코딩 문제**  
  
-   LNK2001 진단 텍스트를 보고 하는 경우 `__check_commonlanguageruntime_version` 는 확인 되지 않은 외부 기호 참조 [l n k&2019;](../../error-messages/tool-errors/linker-tools-error-lnk2019.md) 해결 하는 방법에 대 한 내용은 합니다.  
  
-   멤버 템플릿 정의 클래스를 벗어납니다. Visual c + +에는&1; 멤버 템플릿은 바깥쪽 클래스 내에서 완벽 하 게 정의 합니다. LNK2001 및 멤버 템플릿에 대 한 자세한 내용은 기술 자료 문서를 q&23943;6를 참조 하십시오.  
  
-   대/소문자를 일치 하지 않는 코드 또는 모듈 정의 (.def) 파일에는 LNK2001 발생할 수 있습니다. 예를 들어 변수를 명명 된 `var1` 한 c + + 소스 파일 및으로 액세스 하려고 했습니다. `VAR1` 다른 합니다.  
  
-   사용 하는 프로젝트 [함수 인라이닝](../../error-messages/tool-errors/function-inlining-problems.md) 헤더에서 파일 LNK2001 하면 보다는.cpp 파일에서 함수를 정의 합니다.  
  
-   C + + 프로그램에서 C 함수를 사용 하지 않고 호출 `extern` (컴파일러가 C 명명 규칙을 사용 하 여)는 "C" LNK2001 발생할 수 있습니다. 컴파일러 옵션 [/Tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) 및 [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) 사용 하면 컴파일러가 파일 이름 확장명에 관계 없이 파일을 c + + 또는 C로 컴파일합니다. 이러한 옵션에는 원하는 것과 다른 함수 이름을 발생할 수 있습니다.  
  
-   외부 링크를 사용 하지 않는 데이터 또는 함수를 참조 하려고 하면 LNK2001 발생할 수 있습니다. C + +에서 인라인 함수 및 `const` 으로 명시적으로 지정 되지 않은 데이터는 내부 링크 `extern`합니다.  
  
-   A [함수 본문 또는 변수 누락](../../error-messages/tool-errors/missing-function-body-or-variable.md) LNK2001 발생할 수 있습니다. 함수 프로토타입을 사용 또는 `extern` 선언 컴파일러는 오류 없이 계속할 수 있지만 함수 코드 또는 예약 된 변수 공간이 없을 때문에 링커 주소에 대 한 호출 또는 변수에 대 한 참조를 확인할 수 없습니다.  
  
-   함수 선언에 있는 일치 하지 않는 매개 변수 형식으로 함수를 호출 하면 lnk2001이 발생할 수 있습니다. [이름 데코레이션](../../error-messages/tool-errors/name-decoration.md) 데코 레이트 된 최종 함수 이름에는 함수의 매개 변수를 포함 시킵니다.  
  
-   잘못 포함 된 프로토타입으로 하면 컴파일러는 제공 되지 않는 함수 본문의 결과 LNK2001 발생할 수 있습니다. 함수는 클래스와 비 클래스 구현이 있는 경우 `F`, c + + 범위 결정 규칙에 주의 하세요.  
  
-   C + +를 사용 하면 함수 프로토타입을 클래스 정의에 포함 하 고 실패 [구현을 포함](../../error-messages/tool-errors/missing-function-body-or-variable.md) 해당 클래스에 대 한 함수의 LNK2001 발생할 수 있습니다.  
  
-   생성자 나 소멸자는 추상 기본 클래스의 순수 가상 함수를 호출 하려고 하면 LNK2001 발생할 수 있습니다. 순수 가상 함수에는 기본 클래스 구현이 없습니다.  
  
-   함수 내에 선언 된 변수를 사용 하려고 ([지역 변수](../../error-messages/tool-errors/automatic-function-scope-variables.md)) 해당 함수의 범위 밖에 LNK2001 발생할 수 있습니다.  
  
-   ATL 프로젝트의 릴리스 버전을 빌드하는 경우 CRT 시작 코드가 필요 함을 나타냅니다. 다음 중 하나를 수행를 해결 하려면  
  
    -   제거 `_ATL_MIN_CRT` 전처리기의 목록에서 CRT 시작 코드가 포함 될 수 있도록 정의 합니다. 참조 [일반 구성 설정의 속성 페이지](../../ide/general-property-page-project.md) 에 대 한 자세한 내용은 합니다.  
  
    -   가능 하면 CRT 시작 코드를 필요로 하는 CRT 함수에 대 한 호출을 제거 합니다. 대신 Win32이에 해당 합니다. 예를 들어 사용 `lstrcmp` 대신 `strcmp`합니다. CRT 시작 코드가 필요한 알려진된 함수에 문자열 및 부동 소수점 함수가 중 일부입니다.  
  
 **컴파일 및 링크 문제**  
  
-   프로젝트에 라이브러리에 대 한 참조를 없습니다 (합니다. LIB) 또는 개체 (합니다. OBJ) 파일입니다. 참조 [링커 입력 파일로 사용 하는.lib 파일](../../build/reference/dot-lib-files-as-linker-input.md) 에 대 한 자세한 내용은 합니다.  
  
-   사용 하는 경우 [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) 또는 [/Zl](../../build/reference/zl-omit-default-library-name.md), 명시적으로 포함 하지 않으면 필요한 코드가 포함 된 라이브러리를 프로젝트에 연결 되지 것입니다. (로 컴파일할 때 **/clr** 또는 **/clr: pure**,.cctor에 대 한 참조가 표시 됩니다; 참조 [혼합 어셈블리 초기화](../../dotnet/initialization-of-mixed-assemblies.md) 에 대 한 자세한 내용은.)  
  
-   유니코드 및 MFC를 사용 하는 경우에서 확인할 수 없는 외부를 얻을 수 있습니다 `_WinMain@16` 한 entrypoint를 만들지 않으면 `wWinMainCRTStartup`; 사용는 [/ENTRY](../../build/reference/entry-entry-point-symbol.md)합니다. 참조 [유니코드 프로그래밍 요약](../../text/unicode-programming-summary.md)합니다.  
  
     자세한 내용은 MSDN Library에 있는 다음 기술 자료 문서를 참조 하십시오. MSDN Library에서 클릭 된 **검색** 탭, 문서 번호 또는 문서 제목 텍스트 상자에 붙여 클릭 한 후 **항목 목록**합니다. 문서 번호를 검색 하는 경우는 **제목 에서만 검색** 옵션의 선택을 취소 합니다.  
  
    -   Q125750 "PRB: 오류 LNK2001: '_WinMain@16': 외부 기호를 확인할 수 없는"  
  
    -   Q131204 "PRB: 잘못 된 프로젝트 선택 하면 LNK2001에 _WinMain@16"  
  
    -   Q100639 "유니코드 지원 Microsoft Foundation 클래스 라이브러리"  
  
    -   Q291952 "PRB: 연결 오류 LNK2001: 확인 되지 않은 외부 기호 _main"  
  
-   라이브러리 LIBC.lib /MT으로 컴파일된 코드를 연결로 인해 LNK2001 `_beginthread`, `_beginthreadex`, `_endthread`, 및 `_endthreadex`합니다.  
  
-   다중 스레드 라이브러리를 필요로 하는 코드를 연결할 (MFC 코드나 사용 하 여 컴파일된 코드 [/MT](../../build/reference/md-mt-ld-use-run-time-library.md))로 인해 LNK2001 [_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md), `_beginthreadex`, [_endthread](../../c-runtime-library/reference/endthread-endthreadex.md), 및 `_endthreadex`합니다. 자세한 내용은 다음 기술 자료 문서를 참조 하십시오.  
  
    -   Q126646 "PRB: 오류 메시지: __beginthreadex에 LNK2001 및 \__endthreadex"  
  
    -   Q128641 "INFO: /Mx 컴파일러 옵션 및 LIBC, LIBCMT, MSVCRT Libs"  
  
    -   Q166504 "PRB: MFC, CRT 디버그/릴리스 및 정적 및 동적 일치 해야 합니다"  
  
-   로 컴파일할 때 **/MD**, 원본의 "func"에 대 한 참조에서 참조 하 게 "`__imp__func`" DLL 내에서 모든 실행 시간은 이제 보유 하므로 개체에 있습니다. LNK2001 LIBC.lib 또는 LIBCMT.lib 정적 라이브러리와 링크 하려는 경우 얻을 수 있습니다 `__imp__func`합니다. /MD 없이 컴파일할 때 msvcxx.lib 연결 하려고 하는 경우 항상 LNK2001을 가져오지 않습니다 하지만 다른 문제를 사용할 수 있습니다.  
  
-   응용 프로그램의 디버그 버전을 빌드할 때 릴리스 모드 라이브러리에 링크 LNK2001 발생할 수 있습니다. 마찬가지로,를 사용 하는 **/Mxd** 옵션 (**/MTd**, 또는 **/MDd**) 정의 및/또는 `_DEBUG` 다음 릴리스 라이브러리에 링크 제공 됩니다 (다른 문제가) 간에 잠재적인 해결 되지 않은 외부 참조입니다. 디버그 라이브러리와 릴리스 모드 빌드를 연결 하는 경우에 비슷한 문제가 발생도 합니다.  
  
-   혼합 버전의 Microsoft 라이브러리 및 컴파일러 제품 문제가 될 수 있습니다. 새 컴파일러 버전의 라이브러리는 이전 버전에 포함 된 라이브러리에서 찾을 수 없는 새 기호를 포함할 수 있습니다. 현재 버전을 가리키도록 변경 또는 검색 경로에 있는 디렉터리의 순서를 변경 해야 할 수 있습니다.  
  
     도구 | 옵션 | 프로젝트 | 라이브러리 파일 선택 영역에서 VC + + 디렉터리 대화 상자를 사용 하면 검색 순서를 변경할 수 있습니다. 링커 폴더는 프로젝트의 속성 페이지 대화 상자에 만료 될 수 있는 경로 포함할 수도 있습니다.  
  
     이 문제는 (아마도 다른 위치로), 새 SDK 설치 될 때 검색 순서가 새 위치를 가리키도록 업데이트 되지 않습니다 나타날 수 있습니다. 일반적으로 새 Sdk로의 경로 입력 해야 포함 및 라이브러리의 기본 Visual c + + 위치 앞에 디렉터리입니다. 또한 포함 된 경로 포함 하는 프로젝트 경로 이전 경로 유효 하지만 다른 위치에 설치 되어 있는 새 버전에 의해 추가 된 새로운 기능에 대 한 오래 된를 가리키기도 합니다.  
  
-   현재 표준이 없습니다 [c + + 명명](../../error-messages/tool-errors/name-decoration.md) 컴파일러 공급 업체 간에 또는 서로 다른 버전의 컴파일러 간 합니다. 따라서 다른 컴파일러로 컴파일한 개체 파일에 연결 될 수 있습니다 하지 같은 명명 체계가 생성 하 고 오류 LNK2001.  
  
-   [혼합 인라인이 아닌 컴파일 옵션](../../error-messages/tool-errors/function-inlining-problems.md) 서로 다른 모듈에서 LNK2001 발생할 수 있습니다. C + + 라이브러리 함수 인라이닝 설정 만들어집니다 (**/Ob1** 또는 **/Ob2**)는 해당 하는 함수를 설명 하는 헤더 파일 해제 인라인 처리 하지만 (없습니다 `inline` 키워드),이 오류가 표시 됩니다. 이 문제를 방지 하 여 인라인 함수 정의 되어 있는 `inline` 다른 파일에 포함 하는 것은 헤더 파일에 있습니다.  
  
-   사용 하는 경우는 `#pragma inline_depth` 있는지 컴파일러 지시문을 확인 한 [2 이상 집합의 값에](../../error-messages/tool-errors/function-inlining-problems.md), 사용 하 고 있는지 확인 하 고는 [/Ob1](../../build/reference/ob-inline-function-expansion.md) 또는 [/Ob2](../../build/reference/ob-inline-function-expansion.md) 컴파일러 옵션입니다.  
  
-   연결 옵션을 생략 하 여 리소스 전용 DLL을 만들 때 /NOENTRY LNK2001 발생 합니다.  
  
-   잘못 된 /SUBSYSTEM 또는 /ENTRY 설정을 사용 하 여 LNK2001 발생할 수 있습니다. 예를 들어 문자 기반 응용 프로그램 (콘솔 응용 프로그램)을 작성 하 고 /subsystem 받습니다에 대 한 확인 되지 않은 외부 `WinMain`합니다. 이러한 옵션 및 진입점에 대 한 자세한 내용은 참조는 [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) 및 [/ENTRY](../../build/reference/entry-entry-point-symbol.md) 링커 옵션입니다.  
  
 **내보내기 문제**  
  
-   32 또는 64 비트 16에서 응용 프로그램을 이식 하는 LNK2001 발생할 수 있습니다. 현재 모듈 정의 (.def) 파일 구문에서는 `__cdecl`, `__stdcall`, 및 `__fastcall` 함수 없이 데코레이팅되지 밑줄 없이 EXPORTS 섹션에 나열 되어야 합니다. 이 밑줄 (데코레이팅된)로 표시 되어야 합니다 여기서는 16 비트 구문에서와 다릅니다. 자세한 내용은 참조에 대 한 설명을 [내보내기](../../build/reference/exports.md) 모듈 정의 파일의 섹션입니다.  
  
-   .Def 파일에 나열 된 내보내기를 찾지 LNK2001 발생 합니다. 존재 하지 않는 것은 철자가 잘못 또는 c + + 데코레이팅된 이름 (.def 파일 데코레이팅된 이름을 사용 하지 않음)를 사용 하 여 때문일 수 있습니다.  
  
 **결과 해석**  
  
 기호 확인 없는 경우 다음 지침에 따라 함수에 대 한 정보를 얻을 수 있습니다.  
  
 X86 플랫폼에서 이름에 대 한 호출 규칙 장식 c에서 컴파일된 또는 extern "C" 이름을 c + +에서는:  
  
 `__cdecl`  
 함수에는 밑줄 (_)이 접두사로 있습니다.  
  
 `__stdcall`  
 함수에는 밑줄 (_) 접두사와 접미사 뒤에 있는 dword @ 맞춤 크기가 스택에 매개 변수입니다.  
  
 `__fastcall`  
 함수에는 @ 접두사와 접미사 뒤에 있는 dword @ 맞춤 크기가 스택에 매개 변수입니다.  
  
 Undname.exe를 사용 하 여 데코레이팅되지 않은 형태의 데코레이팅된 이름 가져옵니다.  
  
 위에 나열 된 원인 중 일부에 대 한 자세한 내용은 참조 하십시오. [이름 데코레이션](../../error-messages/tool-errors/name-decoration.md)합니다.
