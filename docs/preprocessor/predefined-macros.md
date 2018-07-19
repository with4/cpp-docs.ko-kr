---
title: 미리 정의 된 매크로 | Microsoft Docs
ms.custom: update_every_version
ms.date: 04/30/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _ATL_VER
- __ATOM__
- __AVX__
- __AVX2__
- _CHAR_UNSIGNED
- __CLR_VER
- _CONTROL_FLOW_GUARD
- __COUNTER__
- __cplusplus
- __cplusplus_cli
- __cplusplus_winrt
- _CPPRTTI
- _CPPUNWIND
- __DATE__
- _DEBUG
- _DLL
- __FILE__
- __FUNCDNAME__
- __FUNCSIG__
- __FUNCTION__
- _INTEGRAL_MAX_BITS
- _ISO_VOLATILE
- _KERNEL_MODE
- __LINE__
- _M_AMD64
- _M_ARM
- _M_ARM_ARMV7VE
- _M_ARM_FP
- _M_ARM64
- _M_CEE
- _M_CEE_PURE
- _M_CEE_SAFE
- _M_FP_EXCEPT
- _M_FP_FAST
- _M_FP_PRECISE
- _M_FP_STRICT
- _M_IX86
- _M_IX86_FP
- _M_X64
- _MANAGED
- _MFC_VER
- _MSC_BUILD
- _MSC_EXTENSIONS
- _MSC_FULL_VER
- _MSC_VER
- _MSVC_LANG
- __MSVC_RUNTIME_CHECKS
- _MT
- _NATIVE_WCHAR_T_DEFINED
- _NO_SIZED_DEALLOCATION
- _OPENMP
- _PREFAST_
- _RESUMABLE_FUNCTIONS_SUPPORTED
- _RTC_CONVERSION_CHECKS_ENABLED
- __STDC__
- __STDC_HOSTED__
- __STDCPP_THREADS__
- __TIME__
- __TIMESTAMP__
- __VA_ARGS__
- _VC_NODEFAULTLIB
- _WCHAR_T_DEFINED
- _WIN32
- _WIN64
- _WINRT_DLL
- __func__
dev_langs:
- C++
helpviewer_keywords:
- timestamps, preprocessor macro
- cl.exe compiler, version number
- version numbers, C/C++ compiler (cl.exe)
- macros, predefined C++
- preprocessor, macros
- predefined macros
- _ATL_VER macro
- __ATOM__ macro
- __AVX__ macro
- __AVX2__ macro
- _CHAR_UNSIGNED macro
- __CLR_VER macro
- _CONTROL_FLOW_GUARD macro
- __COUNTER__ macro
- __cplusplus macro
- __cplusplus_cli macro
- __cplusplus_winrt macro
- _CPPRTTI macro
- _CPPUNWIND macro
- __DATE__ macro
- _DEBUG macro
- _DLL macro
- __FILE__ macro
- __FUNCDNAME__ macro
- __FUNCSIG__ macro
- __FUNCTION__ macro
- _INTEGRAL_MAX_BITS macro
- _ISO_VOLATILE macro
- _KERNEL_MODE macro
- __LINE__ macro
- _M_AMD64 macro
- _M_ARM macro
- _M_ARM_ARMV7VE macro
- _M_ARM_FP macro
- _M_ARM64 macro
- _M_CEE macro
- _M_CEE_PURE macro
- _M_CEE_SAFE macro
- _M_FP_EXCEPT macro
- _M_FP_FAST macro
- _M_FP_PRECISE macro
- _M_FP_STRICT macro
- _M_IX86 macro
- _M_IX86_FP macro
- _M_X64 macro
- _MANAGED macro
- _MFC_VER macro
- _MSC_BUILD macro
- _MSC_EXTENSIONS macro
- _MSC_FULL_VER macro
- _MSC_VER macro
- _MSVC_LANG macro
- __MSVC_RUNTIME_CHECKS macro
- _MT macro
- _NATIVE_WCHAR_T_DEFINED macro
- _NO_SIZED_DEALLOCATION macro
- _OPENMP macro
- _PREFAST_ macro
- _RESUMABLE_FUNCTIONS_SUPPORTED macro
- _RTC_CONVERSION_CHECKS_ENABLED macro
- __STDC__ macro
- __STDC_HOSTED__ macro
- __STDCPP_THREADS__ macro
- __TIME__ macro
- __TIMESTAMP__ macro
- __VA_ARGS__ macro
- _VC_NODEFAULTLIB macro
- _WCHAR_T_DEFINED macro
- _WIN32 macro
- _WIN64 macro
- _WINRT_DLL macro
- __func__ identifier
ms.assetid: 1cc5f70a-a225-469c-aed0-fe766238e23f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 692279d8c19f2a03dcd9388eb47a640dcb00658a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32425246"
---
# <a name="predefined-macros"></a>미리 정의된 매크로

Visual c + + 컴파일러 (C 또는 c + +) 언어, 컴파일 대상 및 선택한 컴파일러 옵션에 따라 특정 전처리기 매크로 미리 정의 합니다.

Visual c + +는 ANSI/ISO C99 표준 및 ISO C + + 14 표준에 지정 된 미리 정의 된 필요한 전처리기 매크로 지원 합니다. 구현도 몇 가지 추가 Microsoft 전용 전처리기 매크로 지원합니다. 일부 매크로 특정 빌드 환경 또는 컴파일러 옵션에 대해서만 정의 됩니다. 설명이 없는 한, 매크로로 지정 된 경우에 따라 전체 변환 단위에서 정의 된 **/D** 컴파일러 옵션 인수입니다. 정의 된 매크로 컴파일 전에 전처리기에 의해 지정된 된 값으로 확장 됩니다. 미리 정의 된 매크로 인수를 사용 하지 않으며 재정의 될 수 없습니다.

## <a name="standard-predefined-identifier"></a>미리 정의 된 표준 식별자

컴파일러는 ISO C99 및 C + + 11 ISO에서 지정 된이 미리 정의 된 식별자를 지원 합니다.

- **&#95;&#95;func&#95; &#95;**  함수 로컬 바깥쪽 함수의 정규화 되지 않은 되지 않은 이름을 `static const` 배열을 `char`합니다.

    ```cpp
    void example(){
        printf("%s\n", __func__);
    } // prints "example"
    ```

## <a name="standard-predefined-macros"></a>표준 미리 정의 된 매크로

컴파일러는 ISO C99 및 ISO C + + 17 표준에 지정 된 이러한 미리 정의 된 매크로 지원 합니다.

- **&#95;&#95;cplusplus** c + +로 변환 단위를 컴파일할 때 정수 리터럴 값으로 정의 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;&#95;날짜&#95; &#95;**  현재 소스 파일의 컴파일 날짜입니다. 날짜가 상수 길이 문자열 형식의 리터럴 *Mmm dd yyyy*합니다. 월 이름 *Mmm* 같습니다에 약식된 월 이름으로 C 런타임 라이브러리에서 생성 된 날짜 [asctime](../c-runtime-library/reference/asctime-wasctime.md) 함수입니다. 날짜의 첫 번째 문자 *dd* 값이 10 보다 작은 경우에 공백입니다. 이 매크로 항상 정의 됩니다.

- **&#95;&#95;파일&#95; &#95;**  현재 소스 파일의 이름입니다. **&#95;&#95;파일&#95; &#95;**  문자 문자열 리터럴로 확장 됩니다. 전체 경로 파일에 표시 되도록 하려면 사용 하 여 [/FC (전체 소스 코드 파일의 경로 진단에서)](../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md)합니다. 이 매크로 항상 정의 됩니다.

- **&#95;&#95;줄&#95; &#95;**  현재 소스 파일에서 정수 줄 수로 정의 됩니다. 값은 **&#95; &#95;줄&#95; &#95;** 매크로 사용 하 여 변경할 수 있습니다는 `#line` 지시문입니다. 이 매크로 항상 정의 됩니다.

- **&#95;&#95;STDC&#95; &#95;**  C로 컴파일된 경우에 있고 1로 정의 된 [/Za](../build/reference/za-ze-disable-language-extensions.md) 컴파일러 옵션을 지정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;&#95;STDC&#95;HOSTED&#95; &#95;**  구현이 1로 정의 *구현 호스트*를 지 원하는 전체 필요한 표준 라이브러리입니다. 그렇지 않으면 0으로 정의 합니다.

- **&#95;&#95;STDCPP&#95;스레드&#95; &#95;**  프로그램 실행 둘 이상의 스레드를 가질 수 있습니다 하는 경우에 1로 정의 하 고 c + +로 컴파일된 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;&#95;시간&#95; &#95;**  번역 전처리 변환 단위의 시간입니다. 문자열에 리터럴 폼의 *hh: mm:*, C 런타임 라이브러리에서 반환 된 시간과 같은 [asctime](../c-runtime-library/reference/asctime-wasctime.md) 함수입니다. 이 매크로 항상 정의 됩니다.

## <a name="microsoft-specific-predefined-macros"></a>Microsoft 전용 미리 정의 된 매크로

Microsoft Visual c + + 추가 이러한 미리 정의 된 매크로 지원합니다.

- **&#95;&#95;ATOM&#95; &#95;**  하면 1로 정의 된 [/favor:ATOM](../build/reference/favor-optimize-for-architecture-specifics.md) 컴파일러 옵션을 설정 하 고 컴파일러 대상은 x86 또는 x64 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;&#95;AVX&#95; &#95;**  하면 1로 정의 된 [/arch: avx](../build/reference/arch-x86.md) 또는 [/arch: avx2](../build/reference/arch-x86.md) 컴파일러 옵션을 설정 하 고 컴파일러 대상은 x86 또는 x64 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;&#95;AVX2&#95; &#95;**  하면 1로 정의 된 [/arch: avx2](../build/reference/arch-x86.md) 컴파일러 옵션을 설정 하 고 컴파일러 대상은 x86 또는 x64 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;CHAR&#95;UNSIGNED** 기본 이면 1로 정의 `char` 부호 없는 형식입니다. 이 경우에 설정 됩니다는 [/J (부호 형식은 기본 문자)](../build/reference/j-default-char-type-is-unsigned.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;&#95;CLR&#95;VER** 응용 프로그램을 컴파일할 때 사용 되는 공용 언어 런타임의 버전을 나타내는 정수 리터럴로 정의 합니다. 인코딩 형식에서 `Mmmbbbbb`여기서 `M` 은 런타임의 주 버전 `mm` 은 런타임의 부 버전이 및 `bbbbb` 는 빌드 번호입니다. **&#95;&#95;CLR&#95;VER** 경우가 정의 된 [/clr](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

    ```cpp
    // clr_ver.cpp
    // compile with: /clr
    using namespace System;
    int main() {
       Console::WriteLine(__CLR_VER);
    }
    ```

- **&#95;컨트롤&#95;흐름&#95;가드** 하면 1로 정의 된 [/guard: cf (제어 흐름 보호 사용)](../build/reference/guard-enable-control-flow-guard.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;&#95;카운터&#95; &#95;**  0부터 시작 하 고 소스 파일에서 사용 될 때마다 1 씩 증가 또는 소스 파일의 헤더를 포함 하는 정수 리터럴로 확장 합니다. **&#95;&#95;카운터&#95; &#95;**  미리 컴파일된 헤더를 사용 하는 경우의 상태를 기억 합니다. 이 매크로 항상 정의 됩니다.

  이 예에서는 `__COUNTER__` 를 같은 유형의 세 가지 다른 개체에 고유 식별자를 할당 합니다. `exampleClass` 생성자 매개 변수로 정수를 사용 합니다. `main`, 형식의 세 개체를 선언 하는 응용 프로그램 `exampleClass`를 사용 하 여 `__COUNTER__` 고유 식별자 매개 변수로:

    ```cpp
    // macro__COUNTER__.cpp
    // Demonstration of __COUNTER__, assigns unique identifiers to
    // different objects of the same type.
    // Compile by using: cl /EHsc /W4 macro__COUNTER__.cpp
    #include <stdio.h>

    class exampleClass {
        int m_nID;
    public:
        // initialize object with a read-only unique ID
        exampleClass(int nID) : m_nID(nID) {}
        int GetID(void) { return m_nID; }
    };

    int main()
    {
        // __COUNTER__ is initially defined as 0
        exampleClass e1(__COUNTER__);

        // On the second reference, __COUNTER__ is now defined as 1
        exampleClass e2(__COUNTER__);

        // __COUNTER__ is now defined as 2
        exampleClass e3(__COUNTER__);

        printf("e1 ID: %i\n", e1.GetID());
        printf("e2 ID: %i\n", e2.GetID());
        printf("e3 ID: %i\n", e3.GetID());

        // Output
        // ------------------------------
        // e1 ID: 0
        // e2 ID: 1
        // e3 ID: 2

        return 0;
    }
    ```

- **&#95;&#95;cplusplus&#95;cli** 200406 c + +로 컴파일할 때 정수 리터럴 값으로 정의 및 [/clr](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다. 정의 된 경우  **&#95; &#95;cplusplus&#95;cli** 변환 단위 전체에 적용 됩니다.

    ```cpp
    // cplusplus_cli.cpp
    // compile by using /clr
    #include "stdio.h"
    int main() {
       #ifdef __cplusplus_cli
          printf("%d\n", __cplusplus_cli);
       #else
          printf("not defined\n");
       #endif
    }
    ```

- **&#95;&#95;cplusplus&#95;winrt** 201009 c + +로 컴파일할 때 정수 리터럴 값으로 정의 및 [/ZW (Windows 런타임 컴파일)](../build/reference/zw-windows-runtime-compilation.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;CPPRTTI** 경우 1로 정의 된 [/GR (런타임 형식 정보 사용)](../build/reference/gr-enable-run-time-type-information.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;CPPUNWIND** 하나 이상 있으면 1로 정의 된 [/GX (예외 처리 활성화)](../build/reference/gx-enable-exception-handling.md), [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md), 또는 [/EH (예외 처리 모델)](../build/reference/eh-exception-handling-model.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;디버그** 하면 1로 정의 된 [/LDd](../build/reference/md-mt-ld-use-run-time-library.md), [/MDd](../build/reference/md-mt-ld-use-run-time-library.md), 또는 [/MTd](../build/reference/md-mt-ld-use-run-time-library.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;DLL** 하면 1로 정의 된 [/MD](../build/reference/md-mt-ld-use-run-time-library.md) 또는 [/MDd](../build/reference/md-mt-ld-use-run-time-library.md) (다중 스레드 DLL) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;&#95;FUNCDNAME&#95; &#95;**  포함 된 문자열 리터럴로 정의 [데코 레이트 된 이름](../build/reference/decorated-names.md) 바깥쪽 함수의 합니다. 매크로 함수 내 에서만 정의 됩니다. **&#95; &#95;FUNCDNAME&#95; &#95;** 매크로 사용 하는 경우 확장 되지 않은 [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) 또는 [/P](../build/reference/p-preprocess-to-a-file.md) 컴파일러 옵션입니다.

   사용 하 여이 예제는 `__FUNCDNAME__`, `__FUNCSIG__`, 및 `__FUNCTION__` 매크로 함수 정보를 표시 합니다.

   [!code-cpp[NVC_Predefined_Macros_Examples#1](../preprocessor/codesnippet/CPP/predefined-macros_1.cpp)]

- **&#95;&#95;FUNCSIG&#95; &#95;**  바깥쪽 함수의 시그니처를 포함 하는 문자열 리터럴로 정의 합니다. 매크로 함수 내 에서만 정의 됩니다. **&#95; &#95;FUNCSIG&#95; &#95;** 매크로 사용 하는 경우 확장 되지 않은 [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) 또는 [/P](../build/reference/p-preprocess-to-a-file.md) 컴파일러 옵션입니다. 호출 규칙은 64 비트 대상에 대 한 컴파일하면 `__cdecl` 기본적으로 합니다. 사용 예제를 보려면는 `__FUNCDNAME__` 매크로입니다.

- **&#95;&#95;함수&#95; &#95;**  바깥쪽 함수의 데코레이팅되지 않은 이름을 포함 하는 문자열 리터럴로 정의 합니다. 매크로 함수 내 에서만 정의 됩니다. **&#95; &#95;함수&#95; &#95;** 매크로 사용 하는 경우 확장 되지 않은 [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) 또는 [/P](../build/reference/p-preprocess-to-a-file.md) 컴파일러 옵션입니다. 사용 예제를 보려면는 `__FUNCDNAME__` 매크로입니다.

- **&#95;정수 계열&#95;최대&#95;비트** 64 정수 리터럴 값으로 정의 됨, 최대 크기 (비트) 벡터가 아닌 정수 계열 형식에 대 한 합니다. 이 매크로 항상 정의 됩니다.

   ```cpp
   // integral_max_bits.cpp
   #include <stdio.h>
   int main() {
      printf("%d\n", _INTEGRAL_MAX_BITS);
   }
   ```

- **&#95;&#95;INTELLISENSE&#95; &#95;**  Visual Studio IDE에서 전달 하는 동안 IntelliSense 컴파일러는 1로 정의 합니다. 그렇지 않으면 정의 되지 않았습니다. IntelliSense 컴파일러를 이해 하지 않거나 빌드 및 IntelliSense 컴파일러 사이 전환 하는 데 사용할 코드를 보호 하기 위해이 매크로 사용할 수 있습니다. 자세한 내용은 참조 [IntelliSense 속도 저하가 대 한 문제 해결 팁](https://blogs.msdn.microsoft.com/vcblog/2011/03/29/troubleshooting-tips-for-intellisense-slowness/)합니다.

- **&#95;ISO&#95;휘발성** 경우 1로 정의 된 [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;커널&#95;모드** 경우 1로 정의 된 [/kernel (커널 모드 이진 만들기)](../build/reference/kernel-create-kernel-mode-binary.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;M&#95;AMD64** 정수 리터럴 값에 컴파일할 100 해당 x64 대상 프로세서로 정의 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;M&#95;ARM** ARM 프로세서를 대상으로 하는 컴파일에 대해 정수 리터럴 값 7로 정의 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;M&#95;ARM&#95;ARMV7VE** 하면 1로 정의 된 [: armv7ve](../build/reference/arch-arm.md) ARM 프로세서를 대상으로 하는 컴파일에 대해 컴파일러 옵션이 설정 되어 있습니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;M&#95;ARM&#95;FP** 를 나타내는 정수 리터럴 값으로 정의 된 [/arch](../build/reference/arch-arm.md) 컴파일 대상이 ARM 프로세서 인 경우 컴파일러 옵션이 설정 되었습니다. 그렇지 않으면 정의 되지 않았습니다.

  - 없는 경우 30-39 범위에서 **/arch** 설정한 ARM에 대 한 기본 아키텍처를 나타내는, ARM 옵션이 지정 되었습니다 (`VFPv3`).

  - 범위에 40-49 if **/arch: vfpv4** 설정 되었습니다.

  - 참조 [/arch (ARM)](../build/reference/arch-arm.md) 자세한 정보에 대 한 합니다.

- **&#95;M&#95;ARM64** 64 비트 ARM 프로세서를 대상으로 하는 컴파일에 대해는 1로 정의 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;M&#95;CEE** 001 경우로 정의 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;M&#95;CEE&#95;순수형** Visual Studio 2015에서 시작 하는 사용 되지 않습니다. 경우에 001로 정의 [/clr: pure](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;M&#95;CEE&#95;안전** Visual Studio 2015에서 시작 하는 사용 되지 않습니다. 경우에 001로 정의 된 [/clr: safe](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;M&#95;FP&#95;EXCEPT** 경우 1로 정의 [/fp: 제외한](../build/reference/fp-specify-floating-point-behavior.md) 또는 [/fp: strict](../build/reference/fp-specify-floating-point-behavior.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;M&#95;FP&#95;빠른** 경우 1로 정의 된 [/fp: fast](../build/reference/fp-specify-floating-point-behavior.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;M&#95;FP&#95;정확히** 경우 1로 정의 된 [/fp: 정확한](../build/reference/fp-specify-floating-point-behavior.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;M&#95;FP&#95;STRICT** 경우 1로 정의 [/fp: strict](../build/reference/fp-specify-floating-point-behavior.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;M&#95;IX86** 정수 리터럴 값 600에 컴파일할 해당 x86 대상 프로세서로 정의 합니다. 이 매크로 x64 또는 ARM 컴파일 대상에 대해 정의 되지 않았습니다.

- **&#95;M&#95;IX86&#95;FP** 나타내는 정수 리터럴 값으로 정의 [/arch](../build/reference/arch-arm.md) 컴파일러 옵션 집합이 나 기본값입니다. 이 매크로 항상 때 정의 됩니다. 컴파일 대상이 x86 프로세서. 그렇지 않으면 정의 되지 않았습니다. 정의 된 경우에 값이입니다.

  - 인 경우 0은 **/arch:IA32** 컴파일러 옵션을 설정 합니다.

  - 이면 1는 **/arch:SSE** 컴파일러 옵션을 설정 합니다.

  - 경우 2는 **/arch: sse2**, **/arch: avx** 또는 **/arch: avx2** 컴파일러 옵션을 설정 합니다. 이 값은 기본값은 **/arch** 컴파일러 옵션을 지정 하지 않았습니다. 때 **/arch: avx** 지정 된 매크로가 **&#95; &#95;AVX&#95; &#95;** 도 정의 됩니다. 때 **/arch: avx2** 지정는 둘 다 **&#95; &#95;AVX&#95; &#95;** 및 **&#95; &#95;AVX2&#95; &#95;** 도 정의 됩니다.

  - 참조 [(x86) /arch](../build/reference/arch-x86.md) 자세한 정보에 대 한 합니다.

- **&#95;M&#95;X64** 정수 리터럴 값에 컴파일할 100 해당 x64 대상 프로세서로 정의 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;관리 되는** 하면 1로 정의 된 [/clr](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;MSC&#95;빌드** 컴파일러의 버전 번호의 수정 버전 번호 요소를 포함 하는 정수 리터럴로 정의 합니다. 수정 번호는 마침표로 구분 된 버전 번호의 네 번째 요소입니다. 예를 들어, Visual c + + 컴파일러의 버전 번호가 15.00.20706.01 인 경우는  **&#95;MSC&#95;빌드** 1로 평가 되는 매크로입니다. 이 매크로 항상 정의 됩니다.

- **&#95;MSC&#95;확장** 경우 1로 정의 [/Ze (언어 확장명 사용)](../build/reference/za-ze-disable-language-extensions.md) 기본값 컴파일러 옵션이 설정 되어 있습니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;MSC&#95;전체&#95;VER** 컴파일러의 버전 번호의 요소 수를 빌드 및 사소한, 주 등을 인코딩하는 정수 리터럴로 정의 합니다. 주 번호는 마침표로 구분 된 버전 번호의 첫 번째 요소, 부 번호는 두 번째 요소 및 빌드 번호는 세 번째 요소입니다. 예를 들어, Visual c + + 컴파일러의 버전 번호가 15.00.20706.01 인 경우는  **&#95;MSC&#95;전체&#95;VER** 매크로 150020706으로 평가 합니다. 입력 **cl /?** 명령줄에서 컴파일러의 버전 번호를 표시 합니다. 이 매크로 항상 정의 됩니다.

- **&#95;MSC&#95;VER** 로 컴파일러의 버전 번호의 주 및 부 번호 요소를 인코딩하는 정수 리터럴로 정의 합니다. 주 번호는 마침표로 구분 된 버전 번호의 첫 번째 요소가 고 부 번호는 두 번째 요소입니다. 예를 들어, Visual c + + 컴파일러의 버전 번호가 17.00.51106.1 인 경우는  **&#95;MSC&#95;VER** 매크로 1700으로 평가 합니다. 입력 **cl /?** 명령줄에서 컴파일러의 버전 번호를 표시 합니다. 이 매크로 항상 정의 됩니다.

   |Visual Studio 버전|&AMP;#95;MSC&AMP;#95;VER|
   |-|-|
   |Visual Studio 6.0|1200|
   |Visual Studio.NET 2002 (7.0)|1300|
   |Visual Studio.NET 2003 (7.1)|1310|
   |Visual Studio 2005 (8.0)|1400|
   |Visual Studio 2008 (9.0)|1500|
   |Visual Studio 2010 (10.0)|1600|
   |Visual Studio 2012 (11.0)|1700|
   |Visual Studio 2013 (12.0)|1800|
   |Visual Studio 2015 (14.0)|1900|
   |Visual Studio 2017 RTW (15.0)|1910|
   |Visual Studio 2017 15.3 버전|1911|
   |Visual Studio 2017 15.5 버전|1912|
   |Visual Studio 2017 버전 15.6|1913|
   |Visual Studio 2017 15.7 버전|1914|

   컴파일러 또는 특정된 버전의 Visual Studio 또는 후에 업데이트, 사용 하 여 테스트 하는 **>=** (크거나 같음) 연산자를 비교 하  **&#95;MSC&#95;VER** 알려 지에 대해 버전. 여러 버전을 함께 사용할 수 없는 방식으로 비교를 사용 하도록 설정한 경우 버전 번호의 내림차순으로 정렬에서 비교를 요청 하는 것이 좋습니다. 예를 들어 또는 Visual Studio 2013, 이후에 출시 컴파일러는 다음 Visual Studio 2013 이전에 릴리스된 모든 컴파일러에 대 한 작업을 수행 하는 다음이 코드는 Visual Studio 2015 이상 버전을 출시 하는 컴파일러에 대 한 확인:

   ```cpp
   #if _MSC_VER >= 1900
   // . . .
   #elif _MSC_VER >= 1800
   // . . .
   #else
   // . . .
   #endif
   ```

   자세한 내용은 참조 [Visual c + + 컴파일러 버전](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/visual-c-compiler-version/) Visual c + + 팀 블로그에서.

- **&#95;MSVC&#95;LANG** c + + 언어 표준 컴파일러에 의해 대상으로 지정 하는 정수 리터럴로 정의 합니다. 경우 매크로 정수 리터럴 값 201402 L c + +를 컴파일할 때는 [/std:c + + 14](../build/reference/std-specify-language-standard-version.md) 컴파일러 옵션을 설정 하거나 기본적으로 설정은 201703 L 경우는 [/std:c + + 17](../build/reference/std-specify-language-standard-version.md) 컴파일러 옵션이 설정 되어; 있고로 설정 되는 이상에서 지정 되지 않은 경우이 값은 [/std:c + + 최신](../build/reference/std-specify-language-standard-version.md)합니다. 그렇지 않으면 매크로가 정의 되지 않습니다. **&#95;MSVC&#95;LANG** 매크로 및 [/std (지정 언어 표준 버전)](../build/reference/std-specify-language-standard-version.md) 컴파일러 옵션은 Visual Studio 2015 업데이트 3부터 사용할 수 있습니다.

- **&#95;&#95;MSVC&#95;런타임&#95;확인** 한 경우 1로 정의의 [/RTC](../build/reference/rtc-run-time-error-checks.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;MT** 하면 1로 정의 [/MD 또는 /MDd](../build/reference/md-mt-ld-use-run-time-library.md) (다중 스레드 DLL) 또는 [/MT 또는 /MTd](../build/reference/md-mt-ld-use-run-time-library.md) (다중 스레드)를 지정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;네이티브&#95;WCHAR&#95;T&#95;DEFINED** 하면 1로 정의 된 [/zc: wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;OPENMP** 경우 Visual c + +에서 구현 된 OpenMP 사양의 날짜를 나타내는 정수 리터럴 200203로 정의 된 [/openmp (OpenMP 2.0 지원 활성화)](../build/reference/openmp-enable-openmp-2-0-support.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

   ```cpp
   // _OPENMP_dir.cpp
   // compile with: /openmp
   #include <stdio.h>
   int main() {
      printf("%d\n", _OPENMP);
   }
   ```

- **&#95;PREFAST&#95;**  하면 1로 정의 된 [/analyze](../build/reference/analyze-code-analysis.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;&#95;타임 스탬프&#95; &#95;**  날짜 및 C 런타임 라이브러리에서 반환 된 약식, 상수 길이 폼에서 현재 소스 파일의 마지막 수정 시간을 포함 하는 문자열 리터럴로 정의 [asctime](../c-runtime-library/reference/asctime-wasctime.md) 함수 예를 들어 `Fri 19 Aug 13:32:58 2016`합니다. 이 매크로 항상 정의 됩니다.

- **&#95;VC&#95;NODEFAULTLIB** 하면 1로 정의 된 [/Zl (기본 라이브러리 이름 생략)](../build/reference/zl-omit-default-library-name.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;WCHAR&#95;T&#95;DEFINED** 하면 1로 정의 된 기본 [/zc: wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 컴파일러 옵션을 설정 합니다. **&#95;WCHAR&#95;T&#95;DEFINED** 매크로 정의 되어 있지만 값이 없는 경우는 **/Zc:wchar_t-** 컴파일러 옵션을 설정 하 고 `wchar_t` 에 포함 된 시스템 헤더 파일에 정의 된 프로젝트입니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;WIN32** 컴파일 대상이 이면 32 비트 ARM, 64 비트 ARM, x86, 1 또는 x 64를 정의 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;WIN64** 컴파일 대상이 64 비트 ARM 또는 x64 인 경우 1로 정의 합니다. 그렇지 않으면 정의 되지 않았습니다.

- **&#95;WINRT&#95;DLL** c + + 및 둘 다로 컴파일된 경우에 1로 정의 된 [/ZW (Windows 런타임 컴파일)](../build/reference/zw-windows-runtime-compilation.md) 및 [/LD 또는 /LDd](../build/reference/md-mt-ld-use-run-time-library.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.

 ATL 또는 MFC 라이브러리 버전을 확인 하는 데 사용 되는 전처리기 매크로 컴파일러에서 미리 정의 되지 않습니다. 이러한 매크로 라이브러리에 대 한 헤더에 정의 필수 헤더를 포함 하기 전에 전처리기 지시문에서 정의 됩니다.

- **&#95;ATL&#95;VER** 에 정의 된 \<atldef.h > ATL 버전 번호 등을 인코딩하는 정수 리터럴.

- **&#95;MFC&#95;VER** 에 정의 된 \<afxver_.h > MFC 버전 번호 등을 인코딩하는 정수 리터럴.

## <a name="see-also"></a>참고 항목

[매크로 (C/c + +)](../preprocessor/macros-c-cpp.md)   
[전처리기 연산자](../preprocessor/preprocessor-operators.md)   
[전처리기 지시문](../preprocessor/preprocessor-directives.md)
