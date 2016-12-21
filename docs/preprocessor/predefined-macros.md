---
title: "미리 정의된 매크로 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ATL_VER"
  - "__ATOM__"
  - "__AVX__"
  - "__AVX2__"
  - "_CHAR_UNSIGNED"
  - "__CLR_VER"
  - "_CONTROL_FLOW_GUARD"
  - "__COUNTER__"
  - "__cplusplus"
  - "__cplusplus_cli"
  - "__cplusplus_winrt"
  - "_CPPRTTI"
  - "_CPPUNWIND"
  - "__DATE__"
  - "_DEBUG"
  - "_DLL"
  - "__FILE__"
  - "__FUNCDNAME__"
  - "__FUNCSIG__"
  - "__FUNCTION__"
  - "_INTEGRAL_MAX_BITS"
  - "_ISO_VOLATILE"
  - "_KERNEL_MODE"
  - "__LINE__"
  - "_M_AMD64"
  - "_M_ARM"
  - "_M_ARM_ARMV7VE"
  - "_M_ARM_FP"
  - "_M_ARM64"
  - "_M_CEE"
  - "_M_CEE_PURE"
  - "_M_CEE_SAFE"
  - "_M_FP_EXCEPT"
  - "_M_FP_FAST"
  - "_M_FP_PRECISE"
  - "_M_FP_STRICT"
  - "_M_IX86"
  - "_M_IX86_FP"
  - "_M_X64"
  - "_MANAGED"
  - "_MFC_VER"
  - "_MSC_BUILD"
  - "_MSC_EXTENSIONS"
  - "_MSC_FULL_VER"
  - "_MSC_VER"
  - "_MSVC_LANG"
  - "__MSVC_RUNTIME_CHECKS"
  - "_MT"
  - "_NATIVE_WCHAR_T_DEFINED"
  - "_NO_SIZED_DEALLOCATION"
  - "_OPENMP"
  - "_PREFAST_"
  - "_RESUMABLE_FUNCTIONS_SUPPORTED"
  - "_RTC_CONVERSION_CHECKS_ENABLED"
  - "__STDC__"
  - "__STDC_HOSTED__"
  - "__STDCPP_THREADS__"
  - "__TIME__"
  - "__TIMESTAMP__"
  - "__VA_ARGS__"
  - "_VC_NODEFAULTLIB"
  - "_WCHAR_T_DEFINED"
  - "_WIN32"
  - "_WIN64"
  - "_WINRT_DLL"
  - "__func__"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "타임 스탬프, 전처리기 매크로"
  - "cl.exe 컴파일러, 버전 번호"
  - "버전 번호, C/c + + 컴파일러 (cl.exe)"
  - "매크로, 미리 정의 된 c + +"
  - "전처리기 매크로"
  - "미리 정의된 매크로"
  - "_ATL_VER 매크로"
  - "__ATOM__ 매크로"
  - "__AVX__ 매크로"
  - "__AVX2__ 매크로"
  - "_CHAR_UNSIGNED 매크로"
  - "__CLR_VER 매크로"
  - "_CONTROL_FLOW_GUARD 매크로"
  - "__COUNTER__ 매크로"
  - "__cplusplus 매크로"
  - "__cplusplus_cli 매크로"
  - "__cplusplus_winrt 매크로"
  - "_CPPRTTI 매크로"
  - "_CPPUNWIND 매크로"
  - "__DATE__ 매크로"
  - "_DEBUG 매크로"
  - "_DLL 매크로"
  - "__FILE__ 매크로"
  - "__FUNCDNAME__ 매크로"
  - "__FUNCSIG__ 매크로"
  - "__FUNCTION__ 매크로"
  - "_INTEGRAL_MAX_BITS 매크로"
  - "_ISO_VOLATILE 매크로"
  - "_KERNEL_MODE 매크로"
  - "__LINE__ 매크로"
  - "_M_AMD64 매크로"
  - "_M_ARM 매크로"
  - "_M_ARM_ARMV7VE 매크로"
  - "_M_ARM_FP 매크로"
  - "_M_ARM64 매크로"
  - "_M_CEE 매크로"
  - "_M_CEE_PURE 매크로"
  - "_M_CEE_SAFE 매크로"
  - "_M_FP_EXCEPT 매크로"
  - "_M_FP_FAST 매크로"
  - "_M_FP_PRECISE 매크로"
  - "_M_FP_STRICT 매크로"
  - "_M_IX86 매크로"
  - "_M_IX86_FP 매크로"
  - "_M_X64 매크로"
  - "_MANAGED 매크로"
  - "_MFC_VER 매크로"
  - "_MSC_BUILD 매크로"
  - "_MSC_EXTENSIONS 매크로"
  - "_MSC_FULL_VER 매크로"
  - "_MSC_VER 매크로"
  - "_MSVC_LANG 매크로"
  - "__MSVC_RUNTIME_CHECKS 매크로"
  - "_MT 매크로"
  - "_NATIVE_WCHAR_T_DEFINED 매크로"
  - "_NO_SIZED_DEALLOCATION 매크로"
  - "_OPENMP 매크로"
  - "_PREFAST_ 매크로"
  - "_RESUMABLE_FUNCTIONS_SUPPORTED 매크로"
  - "_RTC_CONVERSION_CHECKS_ENABLED 매크로"
  - "__STDC__ 매크로"
  - "__STDC_HOSTED__ 매크로"
  - "__STDCPP_THREADS__ 매크로"
  - "__TIME__ 매크로"
  - "__TIMESTAMP__ 매크로"
  - "__VA_ARGS__ 매크로"
  - "_VC_NODEFAULTLIB 매크로"
  - "_WCHAR_T_DEFINED 매크로"
  - "_WIN32 매크로"
  - "_WIN64 매크로"
  - "_WINRT_DLL 매크로"
  - "__func__ 식별자"
ms.assetid: 1cc5f70a-a225-469c-aed0-fe766238e23f
caps.latest.revision: 75
caps.handback.revision: 75
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 미리 정의된 매크로
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual c + + 컴파일러는 언어 (C 또는 c + +), 컴파일 대상 및 선택한 컴파일러 옵션에 따라 특정 전처리기 매크로 미리 정의 합니다.  
  
 Visual c + +는 C + + 14 표준 ISO 및 ANSI/ISO C99 표준에 지정 된 미리 정의 된 필요한 전처리기 매크로 지원 합니다. 또한 구현에서는 몇 가지 더 많은 Microsoft 전처리기 매크로 지원합니다. 일부 매크로 특정 빌드 환경 또는 컴파일러 옵션에 대해서만 정의 됩니다. 설명이 없는 한, 매크로로 지정 된 경우에 따라 변환 단위 전체에 걸쳐 정의 된 **/D** 컴파일러 옵션 인수입니다. 정의 된 매크로 컴파일 전에 전처리기에 의해 지정된 된 값으로 확장 됩니다. 미리 정의 된 매크로 인수를 받지 않으며 재정의 될 수 없습니다.  
  
## <a name="standard-predefined-identifier"></a>미리 정의 된 표준 식별자  
 컴파일러는 ISO C99 및 ISO C + + 11로 지정 된이 미리 정의 된 식별자를 지원 합니다.  
  
-   **__func\_\_** 함수 로컬 바깥쪽 함수의 정규화 되지 않은 이름을 `static``const` 배열을 `char`합니다.  
  
    ```cpp  
    void example(){  
        printf("%s\n", __func__);  
    } // prints "example"  
    ```  
  
## <a name="standard-predefined-macros"></a>표준 미리 정의 된 매크로  
 컴파일러는 ISO C99 및 ISO C + + 14 표준에 지정 된 이러한 미리 정의 된 매크로 지원 합니다.  
  
-   **__cplusplus** 변환 단위가 c + + 파일로 컴파일된 경우 정수 리터럴 값으로 정의 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **__DATE\_\_** 현재 소스 파일의 컴파일 날짜입니다. 날짜는 상수 길이 문자열 형식의 리터럴 *Mmm dd yyyy*합니다. 해당 월 이름 *Mmm* 같습니다에서 약식된 월 이름을 C 런타임 라이브러리에 의해 생성 된 날짜 [asctime](../c-runtime-library/reference/asctime-wasctime.md) 함수입니다. 날짜의 첫 번째 문자 *dd* 값이 10 보다 작은 경우에 공백입니다. 이 매크로 항상 정의 됩니다.  
  
-   **__FILE\_\_** 현재 소스 파일의 이름입니다. **__FILE\_\_** 문자 문자열 리터럴로 확장 됩니다. 파일의 전체 경로 표시 되도록 하려면 사용 하 여 [/FC (파일의 전체 경로 소스 코드에서 진단)](../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md)합니다. 이 매크로 항상 정의 됩니다.  
  
-   **__LINE\_\_** 현재 소스 파일에는 정수 줄 수로 정의 합니다. 값은 **__LINE\_\_** 매크로 사용 하 여 변경할 수 있습니다는 `#line` 지시문입니다. 이 매크로 항상 정의 됩니다.  
  
-   **__STDC\_\_** C로 컴파일된 경우에 있고 1로 정의 된 [/Za](../build/reference/za-ze-disable-language-extensions.md) 컴파일러 옵션을 지정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **__STDC_HOSTED\_\_** 구현이 경우 1로 정의 되는 *구현을 호스트*, 지 원하는 전체 필요한 표준 라이브러리입니다. 그렇지 않으면 0으로 정의 합니다.  
  
-   **__STDCPP_THREADS\_\_** 프로그램 실행의 둘 이상의 스레드가 있을 수 하는 경우에 1로 정의 하 고 c + +로 컴파일됩니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **__TIME\_\_** 번역의 전처리 된 변환 단위 시간입니다. 시간은 문자열 형식의 리터럴 *hh: mm:*, C 런타임 라이브러리에 의해 반환 된 시간이 동일 [asctime](../c-runtime-library/reference/asctime-wasctime.md) 함수입니다. 이 매크로 항상 정의 됩니다.  
  
## <a name="microsoft-specific-predefined-macros"></a>Microsoft 전용 미리 정의 된 매크로  
 Microsoft Visual c + +는 이러한 추가 미리 정의 된 매크로 지원합니다.  
  
-   **__ATOM\_\_** 경우 1로 정의 된 [/favor:ATOM](../build/reference/favor-optimize-for-architecture-specifics.md) 컴파일러 옵션을 설정 하 고 컴파일러 대상은 x86 또는 x64 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **__AVX\_\_** 경우 1로 정의 된 [: avx](../build/reference/arch-x86.md) 또는 [/arch: avx2](../build/reference/arch-x86.md) 컴파일러 옵션을 설정 하 고 컴파일러 대상은 x86 또는 x64 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **__AVX2\_\_** 경우 1로 정의 된 [/arch: avx2](../build/reference/arch-x86.md) 컴파일러 옵션을 설정 하 고 컴파일러 대상은 x86 또는 x64 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_CHAR_UNSIGNED** 기본 이면 1로 정의 `char` 부호 없는 형식입니다. 이 경우에 설정 됩니다는 [/J (부호 형식은 기본 문자)](../build/reference/j-default-char-type-is-unsigned.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **__CLR_VER** 응용 프로그램을 컴파일할 때 사용 되는 공용 언어 런타임의 버전을 나타내는 정수 리터럴로 정의 합니다. 인코딩 형태로 `Mmmbbbbb`, 여기서 `M` 은 런타임의 주 버전 `mm` 은 런타임의 부 버전 및 `bbbbb` 는 빌드 번호입니다. **__CLR_VER** 경우가 정의 된 [/clr](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
    ```cpp  
    // clr_ver.cpp  
    // compile with: /clr  
    using namespace System;  
    int main() {  
       Console::WriteLine(__CLR_VER);  
    }  
    ```  
  
-   **_CONTROL_FLOW_GUARD** 경우 1로 정의 된 [/guard:cf (제어 흐름 보호)](../build/reference/guard-enable-control-flow-guard.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **__COUNTER\_\_** 0부터 시작 하 고 소스 파일에서 사용 될 때마다 1 씩 증가 또는 소스 파일의 헤더를 포함 하는 정수 리터럴로 Expands 합니다. **__COUNTER\_\_** 미리 컴파일된 헤더를 사용 하는 경우 해당 상태를 기억 합니다. 이 매크로 항상 정의 됩니다.  
  
     이 예에서는 `__COUNTER__` 동일한 형식의 세 가지 다른 개체에 고유 식별자를 할당할 수 있습니다.  `exampleClass` 생성자 매개 변수로 정수를 사용 합니다.  `main`, 형식의 세 개체를 선언 하는 응용 프로그램 `exampleClass`, 를 사용 하 여 `__COUNTER__` 고유 식별자 매개 변수로:  
  
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
  
-   **__cplusplus_cli** 200406 c + + 파일로 컴파일된 경우 정수 리터럴 값으로 정의 및 [/clr](../build/reference/clr-common-language-runtime-compilation.md), [/clr: 순수](../build/reference/clr-common-language-runtime-compilation.md), 또는 [/clr: safe](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다. 정의 되 면 **__cplusplus_cli** 변환 단위 전체에 적용 됩니다.  
  
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
  
-   **__cplusplus_winrt** 201009 c + + 파일로 컴파일된 경우 정수 리터럴 값으로 정의 및 [/ZW (Windows Runtime 컴파일)](../build/reference/zw-windows-runtime-compilation.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_CPPRTTI** 이면 1로 정의 된 [/GR (런타임 형식 정보 사용)](../build/reference/gr-enable-run-time-type-information.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_CPPUNWIND** 하나 이상 있으면 1로 정의 된 [/GX (예외 처리 활성화)](../build/reference/gx-enable-exception-handling.md), [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md), 또는 [/EH (예외 처리 모델)](../build/reference/eh-exception-handling-model.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_DEBUG** 경우 1로 정의 된 [/LDd](../build/reference/md-mt-ld-use-run-time-library.md), [/MDd](../build/reference/md-mt-ld-use-run-time-library.md), 또는 [/MTd](../build/reference/md-mt-ld-use-run-time-library.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_DLL** 경우 1로 정의 된 [/MD](../build/reference/md-mt-ld-use-run-time-library.md) 또는 [/MDd](../build/reference/md-mt-ld-use-run-time-library.md) (다중 스레드 DLL) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **__FUNCDNAME\_\_** 포함 된 문자열 리터럴로 정의 [데코레이팅된 이름](../build/reference/decorated-names.md) 바깥쪽 함수의 합니다. 매크로 함수 내 에서만 정의 됩니다.  **__FUNCDNAME\_\_** 매크로 확장 되지 않는 경우 사용 하는 경우는 [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) 또는 [/P](../build/reference/p-preprocess-to-a-file.md) 컴파일러 옵션입니다.  
  
     사용 하 여이 예제는 `__FUNCDNAME__`, `__FUNCSIG__`, 및 `__FUNCTION__` 함수 정보를 표시 하는 매크로입니다.  
  
     [!code-cpp[NVC_Predefined_Macros_Examples#1](../preprocessor/codesnippet/CPP/predefined-macros_1.cpp)]  
  
-   **__FUNCSIG\_\_** 바깥쪽 함수의 시그니처를 포함 하는 문자열 리터럴로 정의 합니다. 매크로 함수 내 에서만 정의 됩니다.  **__FUNCSIG\_\_** 매크로 확장 되지 않는 경우 사용 하는 경우는 [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) 또는 [/P](../build/reference/p-preprocess-to-a-file.md) 컴파일러 옵션입니다. 호출 규칙은 64 비트 대상에 대 한 컴파일하면 `__cdecl` 기본적으로 합니다. 사용의 예를 들어 참조는 `__FUNCDNAME__` 매크로입니다.  
  
-   **__FUNCTION\_\_** 바깥쪽 함수의 데코레이팅되지 않은 이름을 포함 하는 문자열 리터럴로 정의 합니다. 매크로 함수 내 에서만 정의 됩니다.  **__FUNCTION\_\_** 매크로 확장 되지 않는 경우 사용 하는 경우는 [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) 또는 [/P](../build/reference/p-preprocess-to-a-file.md) 컴파일러 옵션입니다. 사용의 예를 들어 참조는 `__FUNCDNAME__` 매크로입니다.  
  
-   **_INTEGRAL_MAX_BITS** 64 정수 리터럴 값으로 정의 된, 벡터가 아닌 정수 계열 형식에 대 한 최대 크기 (비트)에 있습니다. 이 매크로 항상 정의 됩니다.  
  
    ```cpp  
    // integral_max_bits.cpp  
    #include <stdio.h>  
    int main() {  
       printf("%d\n", _INTEGRAL_MAX_BITS);  
    }  
    ```  
  
-   **__INTELLISENSE\_\_** Visual Studio IDE에서 전달 하는 동안 IntelliSense 컴파일러는 1로 정의 합니다. 그렇지 않으면 정의 되지 않았습니다. IntelliSense 컴파일러를 이해 하지 않거나 사용 하 여 빌드 및 IntelliSense 컴파일러 사이 전환 하려면 코드를이 매크로 사용할 수 있습니다. 자세한 내용은 참조 [IntelliSense 만료 경고에 대 한 문제 해결 팁](https://blogs.msdn.microsoft.com/vcblog/2011/03/29/troubleshooting-tips-for-intellisense-slowness/)합니다.  
  
-   **_ISO_VOLATILE** 이면 1로 정의 된 [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_KERNEL_MODE** 이면 1로 정의 된 [/kernel (커널 모드 이진 만들기)](../build/reference/kernel-create-kernel-mode-binary.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_M_AMD64** 정수 리터럴 값 100 컴파일에 대해 해당 대상 x64 프로세서로 정의 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_M_ARM** 는 정수 리터럴 값으로 7 ARM 프로세서를 대상으로 하는 컴파일에 대해 정의 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_M_ARM_ARMV7VE** 경우 1로 정의 된 [: armv7ve](../build/reference/arch-arm.md) 컴파일러 옵션은 ARM 프로세서를 대상으로 하는 컴파일에 대해 설정 됩니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_M_ARM_FP** 를 나타내는 정수 리터럴 값으로 정의 된 [/arch](../build/reference/arch-arm.md) 대상이 있는 경우 컴파일 ARM 프로세서 컴파일러 옵션이 설정 되었습니다. 그렇지 않으면 정의 되지 않았습니다.  
  
    -   없으면 30-39 범위에서 **/arch** ARM 옵션이 지정 되었으므로, 설정 된 arm의 기본 아키텍처를 나타내는 (`VFPv3`).  
  
    -   범위에서 40-49 if **/arch: vfpv4** 설정 되었습니다.  
  
    -   참조 [/arch (ARM)](../build/reference/arch-arm.md) 에 대 한 자세한 내용은 합니다.  
  
-   **_M_ARM64** 64 비트 ARM 프로세서를 대상으로 하는 컴파일에 대해 1로 정의 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_M_CEE** 001 경우로 정의 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_M_CEE_PURE** 001 경우로 정의 [/clr: pure](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_M_CEE_SAFE** 001 경우로 정의 된 [/clr: safe](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_M_FP_EXCEPT** 이면 1로 정의 [/fp: 제외 하 고](../build/reference/fp-specify-floating-point-behavior.md) 또는 [/fp: strict](../build/reference/fp-specify-floating-point-behavior.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_M_FP_FAST** 이면 1로 정의 된 [/fp:fast](../build/reference/fp-specify-floating-point-behavior.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_M_FP_PRECISE** 이면 1로 정의 된 [/fp: 정확한](../build/reference/fp-specify-floating-point-behavior.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_M_FP_STRICT** 이면 1로 정의 [/fp: strict](../build/reference/fp-specify-floating-point-behavior.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_M_IX86** 정수 리터럴 값 600에 컴파일은 x86 대상 프로세서로 정의 합니다. 이 매크로 x64 또는 ARM 컴파일 대상에 대해 정의 되지 않았습니다.  
  
-   **_M_IX86_FP** 나타내는 정수 리터럴 값으로 정의 된 [/arch](../build/reference/arch-arm.md) 집합 또는 기본 컴파일러 옵션입니다. 컴파일 대상에는 x86 때이 매크로 항상 정의 프로세서. 그렇지 않으면 정의 되지 않았습니다. 정의 된 경우에 값이입니다.  
  
    -   인 경우 0은 **/arch:IA32** 컴파일러 옵션을 설정 합니다.  
  
    -   1이 **/arch:SSE** 컴파일러 옵션을 설정 합니다.  
  
    -   경우 2는 **/arch: sse2**, **: avx** 또는 **/arch: avx2** 컴파일러 옵션을 설정 합니다. 이 값은 기본값은 **/arch** 컴파일러 옵션을 지정 하지 않았습니다. 때 **: avx** 지정 매크로 **__AVX\_\_** 도 정의 됩니다. 때 **/arch: avx2** 지정은 모두 **__AVX\_\_** 및 **__AVX2\_\_** 정의 됩니다.  
  
    -   참조 [(x86) /arch](../build/reference/arch-x86.md) 에 대 한 자세한 내용은 합니다.  
  
-   **_M_X64** 정수 리터럴 값 100 컴파일에 대해 해당 대상 x64 프로세서로 정의 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_MANAGED** 경우 1로 정의 된 [/clr](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_MSC_BUILD** 컴파일러의 버전 번호의 수정 버전 번호 요소를 포함 하는 정수 리터럴로 정의 합니다. 수정 번호는 마침표로 구분 된 버전 번호의 네 번째 요소. 예를 들어, Visual c + + 컴파일러의 버전 번호가 15.00.20706.01 인 경우는 **_MSC_BUILD** 1로 평가 되는 매크로입니다. 이 매크로 항상 정의 됩니다.  
  
-   **_MSC_EXTENSIONS** 이면 1로 정의 [/Ze (언어 확장 사용)](../build/reference/za-ze-disable-language-extensions.md) 기본값 컴파일러 옵션이 설정 되어 있습니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_MSC_FULL_VER** 부, 및 컴파일러의 버전 번호의 요소 수를 빌드 주요 인코딩하는 정수 리터럴로 정의 합니다. 주 번호는 마침표로 구분 된 버전 번호의 첫 번째 요소, 부 번호는 두 번째 요소 및 빌드 번호는 세 번째 요소입니다. 예를 들어, Visual c + + 컴파일러의 버전 번호가 15.00.20706.01 인 경우는 **_MSC_FULL_VER** 매크로 150020706으로 평가 합니다. 입력 **cl /?** 컴파일러의 버전 번호를 보려면 명령줄에서 이 매크로 항상 정의 됩니다.  
  
-   **_MSC_VER** 컴파일러의 버전 번호의 주 및 부 번호 요소를 인코딩하는 정수 리터럴로 정의 합니다. 주 번호는 마침표로 구분 된 버전 번호의 첫 번째 요소 및 부 번호는 두 번째 요소입니다. 예를 들어, Visual c + + 컴파일러의 버전 번호가 17.00.51106.1 인 경우는 **_MSC_VER** 매크로 평가 1700이 나옵니다. 입력 **cl /?** 컴파일러의 버전 번호를 보려면 명령줄에서 이 매크로 항상 정의 됩니다.  
  
-   **_MSVC_LANG** 컴파일러에 의해 대상으로 하는 c + + 언어 표준에 지정 하는 정수 리터럴로 정의 합니다. 매크로 정수 리터럴 값 201402 c + + 파일로 컴파일된, 하는 경우는는 [/std:c + + 14](../Topic/-std%20\(Specify%20Language%20Standard%20Version\).md) 컴파일러 옵션을 설정 하거나 기본적으로 높은으로 설정 되며, 지정 하지 않으면 됩니다 값으로 [/std:c + + 최신](../Topic/-std%20\(Specify%20Language%20Standard%20Version\).md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 매크로 정의 되지 않습니다.  **_MSVC_LANG** 매크로 및 [/std (지정 언어 표준 버전)](../Topic/-std%20\(Specify%20Language%20Standard%20Version\).md) 컴파일러 옵션은 Visual Studio 2015 업데이트 3부터 사용할 수 있습니다.  
  
-   **__MSVC_RUNTIME_CHECKS** 한 경우 1로 정의의 [/RTC](../build/reference/rtc-run-time-error-checks.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_MT** 경우 1로 정의 [/MD 또는 /MDd](../build/reference/md-mt-ld-use-run-time-library.md) (다중 스레드 DLL) 또는 [/MT 또는 /MTd](../build/reference/md-mt-ld-use-run-time-library.md) (다중 스레드)를 지정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_NATIVE_WCHAR_T_DEFINED** 경우 1로 정의 된 [/zc: wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_OPENMP** 경우 Visual c + +에서 구현 된 OpenMP 사양의 날짜를 나타내는 정수 리터럴 200203로 정의 된 [/openmp (OpenMP 2.0 지원 활성화)](../build/reference/openmp-enable-openmp-2-0-support.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
    ```cpp  
    // _OPENMP_dir.cpp  
    // compile with: /openmp   
    #include <stdio.h>   
    int main() {  
       printf("%d\n", _OPENMP);  
    }  
    ```  
  
-   **_PREFAST\_** 경우 1로 정의 된 [/analyze](../build/reference/analyze-code-analysis.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **__TIMESTAMP\_\_** C 런타임 라이브러리에 의해 반환 된 약식, 상수 길이 폼에서 현재 소스 파일의 마지막 수정 시간과 날짜를 포함 하는 문자열 리터럴로 정의 [asctime](../c-runtime-library/reference/asctime-wasctime.md) 함수 예를 들어 `Fri 19 Aug 13:32:58 2016`합니다. 이 매크로 항상 정의 됩니다.  
  
-   **_VC_NODEFAULTLIB** 경우 1로 정의 된 [/Zl (기본 라이브러리 이름 생략)](../build/reference/zl-omit-default-library-name.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_WCHAR_T_DEFINED** 경우 1로 정의 된 기본 [/zc: wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 컴파일러 옵션을 설정 합니다.  **_WCHAR_T_DEFINED** 매크로 정의 되어 있지만 값이 없는 경우는 **/Zc:wchar_t-** 컴파일러 옵션을 설정 하 고 `wchar_t` 프로젝트에 포함 된 시스템 헤더 파일에 정의 되어 있습니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_WIN32** 1을 컴파일 대상 32 비트 ARM, 64 비트 ARM, x86 또는 x 64를 정의 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_WIN64** 컴파일 대상이 64 비트 ARM 또는 x64 경우 1로 정의 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
-   **_WINRT_DLL** c + + 및 둘 다로 컴파일된 경우 1로 정의 된 [/ZW (Windows Runtime 컴파일)](../build/reference/zw-windows-runtime-compilation.md) 및 [/LD 또는 /LDd](../build/reference/md-mt-ld-use-run-time-library.md) 컴파일러 옵션을 설정 합니다. 그렇지 않으면 정의 되지 않았습니다.  
  
 전처리기 매크로 ATL 또는 MFC 라이브러리 버전을 확인 하는 데는 컴파일러에 의해 미리 정의 되지 않습니다. 이러한 매크로 라이브러리에 대 한 헤더에 정의 필수 헤더는 포함 하기 전에 전처리기 지시문에서 정의 됩니다.  
  
-   **_ATL_VER** ATL 버전 번호를 인코딩하는 정수 리터럴로 \< atldef.h >에 정의 합니다.  
  
-   **_MFC_VER** MFC 버전 번호를 인코딩하는 정수 리터럴로 \< afxver_.h >에 정의 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [매크로 (C/c + +)](../preprocessor/macros-c-cpp.md)   
 [전처리기 연산자](../preprocessor/preprocessor-operators.md)   
 [전처리기 지시문](../preprocessor/preprocessor-directives.md)