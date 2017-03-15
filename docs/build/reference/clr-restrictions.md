---
title: "/clr 제한 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr 컴파일러 옵션[C++], 제한 사항"
ms.assetid: 385f6462-2c68-46d6-810e-469553ead447
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# /clr 제한
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/clr** 옵션을 사용할 경우 다음과 같은 제한 사항이 있습니다.  
  
-   **\/clr**를 사용하여 컴파일할 때는 구조적 예외 처리기에서 `_alloca`를 사용하는 데 제한이 있습니다.  자세한 내용은 [\_alloca](../../c-runtime-library/reference/alloca.md)를 참조하십시오.  
  
-   **\/clr**를 사용하는 경우에는 런타임 오류 검사를 사용할 수 없습니다.  자세한 내용은 [런타임 오류 검사](../Topic/How%20to:%20Use%20Native%20Run-Time%20Checks.md)를 참조하십시오.  
  
-   표준 C\+\+ 구문만 사용하는 프로그램을 **\/clr**로 컴파일하는 경우 인라인 어셈블리를 사용할 때 다음과 같은 지침이 적용됩니다.  
  
    -   네이티브 스택 레이아웃 정보를 가정하는 인라인 어셈블리 코드가 현재 함수 외부의 규칙이나 컴퓨터에 관한 다른 하위 수준 정보를 호출할 경우, 관리되는 함수용 스택 프레임에 이 네이티브 스택 레이아웃 정보가 적용되면 오류가 발생합니다.  인라인 어셈블리 코드를 포함하는 함수는 **\/clr**를 사용하지 않고 컴파일된 별도의 모듈에 배치되는 것으로 처리하여 관리되지 않는 함수로 생성됩니다.  
  
    -   복사 생성된 함수 매개 변수를 전달하는 인라인 어셈블리 코드는 지원되지 않습니다.  
  
-   **\/clr**로 컴파일한 프로그램에서는 [vprintf Functions](../../c-runtime-library/vprintf-functions.md)를 호출할 수 없습니다.  
  
-   [naked](../../cpp/naked-cpp.md) [\_\_declspec](../../cpp/declspec.md) 수정자는 \/clr 옵션을 사용하면 무시됩니다.  
  
-   [\_set\_se\_translator](../../c-runtime-library/reference/set-se-translator.md)에 의해 설정된 변환기 함수는 비관리 코드의 catch에만 영향을 줍니다.  자세한 내용은 [Exception Handling](../../windows/exception-handling-cpp-component-extensions.md)를 참조하십시오.  
  
-   **\/clr** 옵션을 사용하면 함수 포인터 비교를 사용할 수 없습니다.  
  
-   **\/clr** 옵션을 사용하면 완전히 프로토타입된 함수만 사용할 수 있습니다.  
  
-   **\/clr**를 사용할 때는 다음과 같은 컴파일러 옵션이 지원되지 않습니다.  
  
    -   **\/EHsc** 및 **\/EHs**\(**\/clr**는 **\/EHa**를 내포합니다. [\/EH\(예외 처리 모델\)](../../build/reference/eh-exception-handling-model.md)를 참조하십시오.\)  
  
    -   **\/fp:strict** 및 **\/fp:except**\([\/fp\(부동 소수점 동작 지정\)](../../build/reference/fp-specify-floating-point-behavior.md)를 참조하십시오.\)  
  
    -   [\/Zd](../../build/reference/z7-zi-zi-debug-information-format.md)  
  
    -   [\/Gm](../../build/reference/gm-enable-minimal-rebuild.md)  
  
    -   [\/MT](../../build/reference/md-mt-ld-use-run-time-library.md)  
  
    -   [\/RTC](../../build/reference/rtc-run-time-error-checks.md)  
  
    -   **\/ZI**  
  
-   `_STATIC_CPPLIB` 전처리기 정의\(`/D_STATIC_CPPLIB`\)와 **\/clr**의 조합 또는 **\/clr:pure** 컴파일러 옵션은 지원되지 않습니다.  그 이유는 해당 정의에 의해 지원되지 않는 정적 다중 스레드 표준 C\+\+ 라이브러리에 응용 프로그램이 연결될 수 있기 때문입니다.  자세한 내용은 [\/MD, \/MT, \/LD\(런타임 라이브러리 사용\)](../../build/reference/md-mt-ld-use-run-time-library.md) 항목을 참조하십시오.  
  
-   [\/J](../../build/reference/j-default-char-type-is-unsigned.md)는 **\/clr:safe** 또는 **\/clr:pure**와 함께 사용할 수 없습니다.  
  
-   순수 모드 컴파일\(**\/clr:pure**\)에서는 ATL 및 MFC 라이브러리를 지원하지 않습니다.  또한 **\/MD** 또는 **\/MDd**를 사용하여 컴파일하는 경우 표준 C\+\+ 라이브러리 및 CRT와 함께 **\/clr:pure**를 사용할 수 있습니다.  
  
-   **\/Zi**를 **\/clr**와 함께 사용하는 경우 성능에 영향을 줄 수 있습니다.  자세한 내용은 [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)를 참조하십시오.  
  
-   [\/Zc:wchar\_t](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md)를 지정하지 않거나 문자를 `__wchar_t`로 캐스팅하지 않고 .NET Framework 출력 루틴에 와이드 문자를 전달하면 출력이 `unsigned short int`로 표시됩니다.  예를 들면 다음과 같습니다.  
  
    ```  
    Console::WriteLine(L' ')              // Will output 32.  
    Console::WriteLine((__wchar_t)L' ')   // Will output a space.  
    ```  
  
-   **\/clr** 옵션을 사용하여 컴파일하면 [\/GS](../../build/reference/gs-buffer-security-check.md) 옵션이 무시됩니다. 함수가 `#pragma` [unmanaged](../../preprocessor/managed-unmanaged.md)에 포함되거나 네이티브 코드로 컴파일되는 경우에는 예외이며, 이 경우 컴파일러는 기본적으로 해제되어 있는 C4793 경고를 생성합니다.  
  
-   관리되는 응용 프로그램의 함수 시그니처 요구 사항은 [\/ENTRY](../../build/reference/entry-entry-point-symbol.md)를 참조하십시오.  
  
-   **\/openmp** 및 **\/clr**를 사용하여 컴파일한 응용 프로그램은 단일 응용 프로그램 도메인 프로세스에서만 실행할 수 있습니다.  자세한 내용은 [\/openmp\(OpenMP 2.0 지원 활성화\)](../../build/reference/openmp-enable-openmp-2-0-support.md)를 참조하십시오.  
  
-   인수의 변수 번호를 취하는 함수\(varargs\)는 네이티브 함수로 생성됩니다.  가변 인수 위치에 있는 모든 관리되는 데이터 형식은 네이티브 형식으로 마샬링됩니다.  <xref:System.String?displayProperty=fullName> 형식은 실제로는 와이드 문자열이지만 싱글 바이트 문자열로 마샬링됩니다.  따라서 printf 지정자가 %S\(wchar\_t\*\)일 경우에는 대신 %s 문자열로 마샬링됩니다.  
  
-   va\_arg 매크로를 사용하는 경우 **\/clr:pure**를 사용하여 컴파일할 때 예기치 않은 결과가 발생할 수도 있습니다.  자세한 내용은 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)을 참조하십시오.  
  
-   응용 프로그램에서 [va\_list](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) 형식의 인수를 [여러 가지 인수](../../misc/variable-argument-lists.md)를 사용하도록 선언된 기능에 전달하고 사용자 응용 프로그램이 **\/clr:pure**로 컴파일되면 CLR에서 <xref:System.NotSupportedException>을 throw합니다.  **\/clr** 를 대신 사용하는 경우 영향을 받는 함수는 네이티브 코드로 컴파일되고 적절히 실행됩니다.  **\/clr:safe**가 사용되는 경우 오류 진단이 내보내집니다.  
  
-   매개 변수 정보\(함수 인수\)를 얻기 위해 스택을 조사하는 어떠한 함수도 관리 코드에서 호출하지 말아야 합니다. P\/Invoke 계층에서는 이 정보가 스택의 더 아래쪽에 배치됩니다.  예를 들어 **\/clr**을 사용하여 프록시\/스텁을 컴파일하지 말아야 합니다.  
  
-   함수는 가능한 경우 항상 관리 코드로 컴파일되지만 모든 C\+\+ 구문을 관리 코드로 변환할 수 있는 것은 아닙니다.  이 변환 여부는 함수별로 각기 다르게 결정됩니다.  함수의 일부분이라도 관리 코드로 변환할 수 없으면 전체 함수가 네이티브 코드로 대신 변환됩니다.  컴파일러에서 관리 코드를 생성하지 않는 경우는 다음과 같습니다.  
  
    -   컴파일러에서 생성한 썽크 또는 도우미 함수.  가상 함수 호출을 비롯하여 함수 포인터를 통한 모든 함수 호출에 대해 네이티브 썽크가 생성됩니다.  
  
    -   `setjmp` 또는 `longjmp`를 호출하는 함수  
  
    -   컴퓨터 리소스를 직접 조작하기 위해 특정한 내장 루틴을 사용하는 함수.  예를 들어, `__enable`과 `__disable`, `_ReturnAddress`와 `_AddressOfReturnAddress` 또는 멀티미디어 내장 형식을 사용하면 네이티브 코드가 생성됩니다.  
  
    -   `#pragma unmanaged` 지시문을 따르는 함수. 반대로 `#pragma managed` 지시문도 지원됩니다.  
  
    -   정렬된 형식\(`__declspec(align(...))`을 사용하여 선언된 형식\)에 대한 참조가 들어 있는 함수  
  
-   **\/clr:pure**나 **\/clr:safe**에서는 [컴파일러 COM 지원](../../cpp/compiler-com-support.md) 클래스를 사용할 수 없습니다.  
  
## 참고 항목  
 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)