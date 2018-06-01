---
title: /clr 제한 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- /clr compiler option [C++], restrictions
ms.assetid: 385f6462-2c68-46d6-810e-469553ead447
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 34d21939f51fc3d4800d5cdd887b283b7e690db6
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704271"
---
# <a name="clr-restrictions"></a>/clr 제한

사용에 대 한 다음과 같은 제한 사항이 **/clr**:

- 구조적된 예외 처리기에 대 한 제한은 사용 하 여 `_alloca` 로 컴파일할 때 **/clr**합니다. 자세한 내용은 참조 [_alloca](../../c-runtime-library/reference/alloca.md)합니다.

- 런타임 오류 검사 사용으로 올바르지 않습니다. **/clr**합니다. 자세한 내용은 [방법: 네이티브 런타임 검사 기능 사용](/visualstudio/debugger/how-to-use-native-run-time-checks)을 참조하세요.

- 때 **/clr** 은 인라인 어셈블리의 사용에 적용 한 다음 지침만 표준 c + + 구문을 사용 하는 프로그램을 컴파일하는 데 사용 합니다.

  - 네이티브 스택 레이아웃 정보를 가정 하는 인라인 어셈블리 코드, 호출 규칙 현재 함수 또는 다른 하위 수준 정보는 컴퓨터에 대 한 외부 실패할 수 있습니다 기술 자료 관리 되는 함수에 대 한 스택 프레임에 적용 되는. 인라인 어셈블리 코드를 포함 하는 함수는 관리 되지 않는 함수로 처럼 생성 하지 않고 컴파일된 별도 모듈에 배치 된 **/clr**합니다.

  - 인라인 어셈블리 코드를 복사 하 여 생성 함수 매개 변수를 전달 하는 지원 되지 않습니다.

- [vprintf 함수](../../c-runtime-library/vprintf-functions.md) 로 컴파일된 프로그램에서 호출할 수 없습니다 **/clr**합니다.

- [naked](../../cpp/naked-cpp.md) [__declspec](../../cpp/declspec.md) /clr에서 한정자가 무시 됩니다.

- 변환기 함수를 설정한 [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md) 비관리 코드에서 catches만에 영향을 줍니다. 참조 [예외 처리](../../windows/exception-handling-cpp-component-extensions.md) 자세한 정보에 대 한 합니다.

- 함수 포인터 비교를 사용할 수 없습니다 **/clr**합니다.

- 완전히 프로토타입화 되지 않은 함수 사용을 사용할 수 없습니다 **/clr**합니다.

- 다음과 같은 컴파일러 옵션으로 지원 되지 않습니다 **/clr**:

  - **/ EHsc** 및 **/EHs** (**/clr** 의미 **/EHa** (참조 [/EH (예외 처리 모델)](../../build/reference/eh-exception-handling-model.md))

  - **/fp: strict** 및 **/fp: 제외한** (참조 [/fp (부동 소수점 동작 지정)](../../build/reference/fp-specify-floating-point-behavior.md))

  - [/Zd](../../build/reference/z7-zi-zi-debug-information-format.md)

  - [/Gm](../../build/reference/gm-enable-minimal-rebuild.md)

  - [/MT](../../build/reference/md-mt-ld-use-run-time-library.md)

  - [/RTC](../../build/reference/rtc-run-time-error-checks.md)

  - [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)

- 조합 된 `_STATIC_CPPLIB` 전처리기 정의 (`/D_STATIC_CPPLIB`) 및 **/clr** 컴파일러 옵션이 지원 되지 않습니다. 이 정의 인해 응용 프로그램의 정적 다중 스레드 c + + 표준 라이브러리, 지원 되지 않는와 연결 하기 때문에 그렇게 합니다. 자세한 내용은 참조는 [/MD, /MT, /LD (런타임 라이브러리 사용)](../../build/reference/md-mt-ld-use-run-time-library.md) 항목입니다.

- 사용 하는 경우 **/Zi** 와 **/clr**에 성능 문제. 자세한 내용은 참조 [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)합니다.

- 도 지정 하지 않고 루틴을 출력 하는.NET Framework에 대 한 와이드 문자를 전달 [/zc: wchar_t](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 또는 문자를 캐스팅 하지 않고도 `__wchar_t` 로 표시 되도록 출력 하면는 `unsigned short int`합니다. 예를 들어:

    ```cpp
    Console::WriteLine(L' ')              // Will output 32.
    Console::WriteLine((__wchar_t)L' ')   // Will output a space.
    ```

- [/GS](../../build/reference/gs-buffer-security-check.md) 로 컴파일할 때 무시 됩니다 **/clr**함수에서 있지 않으면 `#pragma` [관리 되지 않는](../../preprocessor/managed-unmanaged.md) 함수가 네이티브로 컴파일해야 합니다.이 경우에 컴파일러에서 생성 또는 기본적으로 꺼져 있는 C4793 경고입니다.

- 참조 [/ENTRY](../../build/reference/entry-entry-point-symbol.md) 관리 되는 응용 프로그램의 함수 서명 요구 사항에 대 한 합니다.

- 로 컴파일된 응용 프로그램 **/openmp** 및 **/clr** 단일 appdomain 프로세스에서 실행할 수 있습니다.  참조 [/openmp (OpenMP 2.0 지원 활성화)](../../build/reference/openmp-enable-openmp-2-0-support.md) 자세한 정보에 대 한 합니다.

- 네이티브 함수로 가변 개수의 인수 (varargs)를 사용 하는 함수 생성 됩니다. 가변 인수 위치에 있는 관리 되는 데이터 형식은 네이티브 형식으로 마샬링할 수 됩니다. <xref:System.String?displayProperty=fullName> 형식은 실제로 와이드 문자열 하지만 마샬링되 단일 바이트 문자 문자열입니다. 따라서 printf 지정자는 %%S (wchar_t *),입니다 경우 마샬링합니다 %s 문자열을 대신 합니다.

- Va_arg 매크로 사용 하는 경우로 컴파일할 때 예기치 않은 결과가 발생할 수 있습니다 **/clr: pure**합니다. 자세한 내용은 참조 [va_arg, va_copy, va_end, va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)합니다. **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다. C# "순수" 또는 "안전한" 이어야 하는 코드를 이식 해야 합니다.

- 관리 코드 (함수 인수); 매개 변수 정보를 얻으려면 스택을 탐색 하는 함수 내에서 호출 하지 않아야 P/Invoke 계층에서는 정보가 더 스택에서 아래쪽입니다.  예를 들어 프록시/스텁이 있는 컴파일하지 않거나 **/clr**합니다.

- 함수, 가능 하면 관리 코드에 컴파일되지만 관리 코드에 일부 c + + 구문 번역할 수 있습니다.  함수에서 함수 별로이 결정이 이루어집니다. 함수의 일부 관리 코드로 변환할 수 없습니다, 전체 함수 변환 됩니다 네이티브 코드를 대신 합니다. 다음과 같은 경우 관리 되는 코드를 생성 컴파일러를 방지 합니다.

  - 컴파일러에서 생성 한 썽크 또는 도우미 함수입니다. 네이티브 썽크는 가상 함수 호출을 포함 하는 함수 포인터를 통해 모든 함수 호출에 대해 생성 됩니다.

  - 호출 하는 함수 `setjmp` 또는 `longjmp`합니다.

  - 특정 내장 루틴을 사용 하 여 컴퓨터 리소스를 직접 조작 하는 함수입니다. 사용 예를 들어 `__enable` 및 `__disable`, `_ReturnAddress` 및 `_AddressOfReturnAddress`, 멀티미디어 내장 함수는 네이티브 코드에서 모든 결과 또는 합니다.

  - 따르는 함수는 `#pragma unmanaged` 지시문입니다. (유의 역, `#pragma managed`도 지원 됩니다.)

  - 에 대 한 참조를 포함 하는 함수 정렬 된 형식, 즉 형식을 사용 하 여 선언 `__declspec(align(...))`합니다.

## <a name="see-also"></a>참고자료

- [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)
