---
title: "_ASSERT, _ASSERTE, _ASSERT_EXPR 매크로 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _ASSERTE
- ASSERTE
- _ASSERT
- _ASSERT_EXPR
dev_langs: C++
helpviewer_keywords:
- debugging [CRT], using macros
- _ASSERTE macro
- macros, debugging with
- debug reporting macros
- _ASSERT macro
- _ASSERT_EXPR macro
ms.assetid: e98fd2a6-7f5e-4aa8-8fe8-e93490deba36
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 07be60643ad77e1138c3c23a1dd358a1d4177f25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="assert-asserte-assertexpr-macros"></a>_ASSERT, _ASSERTE, _ASSERT_EXPR 매크로
식을 계산하고 결과가 `False` 인 경우 디버그 보고서를 생성합니다(디버그 버전만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
_ASSERT_EXPR(  
   booleanExpression,  
   message  
);  
_ASSERT(   
   booleanExpression   
);  
_ASSERTE(   
   booleanExpression   
);  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `booleanExpression`  
 0이 아닌 값(true) 또는 0(false)으로 계산되는 스칼라 식(포인터 식 포함)입니다.  
  
 `message`  
 보고서 일부로 표시할 전각 문자열입니다.  
  
## <a name="remarks"></a>설명  
 `_ASSERT_EXPR`, `_ASSERT` 및 `_ASSERTE` 매크로는 디버깅 프로세스 중에 가정을 확인하기 위한 간단 명료한 메커니즘을 응용 프로그램에 제공합니다. 이들 매크로는 응용 프로그램의 정품 빌드 시 호출되지 않도록 `#ifdef` 문에 포함할 필요가 없으므로 매우 유연합니다. 이 유연성을 얻으려면 [_DEBUG](../../c-runtime-library/debug.md) 매크로를 사용합니다. `_ASSERT_EXPR`, `_ASSERT` 및 `_ASSERTE` 는 `_DEBUG` 가 컴파일 시간에 정의될 때만 사용할 수 있습니다. `_DEBUG` 가 정의되지 않으면 이러한 매크로 호출이 전처리 중에 제거됩니다.  
  
 `_ASSERT_EXPR`, `_ASSERT` 및 `_ASSERTE` 는 `booleanExpression` 인수를 계산하고 결과가 `false` (0)이면 진단 메시지를 출력하고 [_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) 를 호출하여 디버그 보고서를 생성합니다. `_ASSERT` 매크로는 간단한 진단 메시지를 출력하고,  `_ASSERTE` 는 실패한 식의 문자열 표시를 메시지에 포함하고, `_ASSERT_EXPR` 은 `message` 문자열을 진단 메시지에 포함합니다. `booleanExpression` 이 0이 아닌 값으로 계산되면 이들 매크로는 아무것도 하지 않습니다.  
  
 `_ASSERT_EXPR`, `_ASSERT` 및 `_ASSERTE` 는 모든 출력을 전각 문자로 제공하는 `_CrtDbgReportW`를 호출합니다. `_ASSERTE` 는 `booleanExpression` 에서 유니코드 문자를 제대로 출력하고 `_ASSERT_EXPR` 은 `message`에서 유니코드 문자를 출력합니다.  
  
 `_ASSERTE` 매크로는 실패한 식을 지정하고 생성된 보고서에서 `_ASSERT_EXPR` 을 통해 메시지를 지정할 수 있으므로 이들 매크로를 사용하면 사용자가 응용 프로그램 소스 코드를 참조하지 않아도 문제를 식별할 수 있습니다. 그러나 `message` 을 통해 출력된 모든 `_ASSERT_EXPR` 와 `_ASSERTE` 를 통해 계산된 모든 식이 응용 프로그램 출력(디버그 버전) 파일에 문자열 상수로 포함된다는 단점이 있습니다. 따라서 `_ASSERT_EXPR` 또는 `_ASSERTE`가 너무 많이 호출되면 이러한 식 때문에 출력 파일 크기가 매우 증가할 수 있습니다.  
  
 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) 및 [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) 함수를 사용해서 지정하지 않으면 메시지가 설정에 해당하는 팝업 대화 상자에 표시됩니다.  
  
`_CrtSetReportMode(CRT_ASSERT, _CRTDBG_MODE_WNDW);`  
  
 `_CrtDbgReportW` 는 디버그 보고서를 생성하고 현재 보고서 모드나 `_CRT_ASSERT` 보고서 종류에 대해 정의된 모드 및 파일을 기반으로 대상을 결정합니다. 기본적으로 어설션 실패 및 오류는 디버그 메시지 창에 전달됩니다. [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) 및 [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) 함수는 각 보고서 종류의 대상을 정의하는 데 사용됩니다.  
  
 대상이 디버그 메시지 창이고 사용자가 **다시 시도** 단추를 클릭하면 `_CrtDbgReportW` 가 1을 반환하고, 이에 따라 JIT(Just-In-Time) 디버깅이 사용하도록 설정된 경우 `_ASSERT_EXPR`, `_ASSERT` 및 `_ASSERTE` 매크로가 디버거를 시작합니다.  
  
 보고 프로세스에 대한 자세한 내용은 [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) 함수를 참조하세요. 어설션 실패를 해결하고 이들 매크로를 디버깅 오류 처리 메커니즘으로 사용하는 방법에 대한 자세한 내용은 [확인 및 보고에 매크로 사용](/visualstudio/debugger/macros-for-reporting)을 참조하세요.  
  
 `_ASSERT` 매크로 이외에 [assert](../../c-runtime-library/reference/assert-macro-assert-wassert.md) 매크로를 사용하여 프로그램 논리를 확인할 수 있습니다. 이 매크로는 라이브러리의 디버그 및 릴리스 버전에서 둘 다 사용할 수 있습니다. [_RPT, _RPTF](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) 디버그 매크로는 디버그 보고서 생성에도 사용할 수 있지만 식을 계산하지 않습니다. `_RPT` 매크로는 간단한 보고서를 생성합니다. `_RPTF` 매크로는 보고서 매크로가 호출된 소스 파일과 줄 번호를 생성된 보고서에 포함합니다. 이들 매크로의 와이드 문자 버전을 사용할 수 있습니다(`_RPTWn`, `_RPTFWn`). 와이드 문자 문자열이 모든 문자열 매개 변수 및 출력에 사용된다는 점을 제외하고 와이드 문자 버전은 반각 문자 버전과 똑같습니다.  
  
 `_ASSERT_EXPR`, `_ASSERT` 및 `_ASSERTE`는 매크로이고 \<crtdbg.h>를 포함하여 사용할 수 있지만, 이들 매크로는 다른 런타임 함수를 호출하므로 `_DEBUG`가 정의된 경우 응용 프로그램은 C 런타임 라이브러리의 디버그 버전과 연결되어야 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|매크로|필수 헤더|  
|-----------|---------------------|  
|`_ASSERT_EXPR`,                  `_ASSERT`, `_ASSERTE`|\<crtdbg.h>|  
  
## <a name="example"></a>예  
 이 프로그램에서 `_ASSERT` 및 `_ASSERTE` 매크로를 호출하여 `string1 == string2`조건을 테스트합니다. 조건이 실패하면 이들 매크로가 진단 메시지를 출력합니다. 매크로의 `_RPTn` 및 `_RPTFn` 그룹도 이 프로그램에서 `printf` 함수 대신 실행됩니다.  
  
```C  
// crt_ASSERT_macro.c  
// compile with: /D_DEBUG /MTd /Od /Zi /link /verbose:lib /debug  
//  
// This program uses the _ASSERT and _ASSERTE debugging macros.  
//  
  
#include <stdio.h>  
#include <string.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main()  
{  
   char *p1, *p2;  
  
   // The Reporting Mode and File must be specified  
   // before generating a debug report via an assert  
   // or report macro.  
   // This program sends all report types to STDOUT.  
   _CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);  
   _CrtSetReportFile(_CRT_WARN, _CRTDBG_FILE_STDOUT);  
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);  
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDOUT);  
   _CrtSetReportMode(_CRT_ASSERT, _CRTDBG_MODE_FILE);  
   _CrtSetReportFile(_CRT_ASSERT, _CRTDBG_FILE_STDOUT);  
  
   // Allocate and assign the pointer variables.  
   p1 = (char *)malloc(10);  
   strcpy_s(p1, 10, "I am p1");  
   p2 = (char *)malloc(10);  
   strcpy_s(p2, 10, "I am p2");  
  
   // Use the report macros as a debugging  
   // warning mechanism, similar to printf.  
   // Use the assert macros to check if the   
   // p1 and p2 variables are equivalent.  
   // If the expression fails, _ASSERTE will  
   // include a string representation of the  
   // failed expression in the report.  
   // _ASSERT does not include the  
   // expression in the generated report.  
   _RPT0(_CRT_WARN,  
       "Use the assert macros to evaluate the expression p1 == p2.\n");  
   _RPTF2(_CRT_WARN, "\n Will _ASSERT find '%s' == '%s' ?\n", p1, p2);  
   _ASSERT(p1 == p2);  
  
   _RPTF2(_CRT_WARN, "\n\n Will _ASSERTE find '%s' == '%s' ?\n",  
          p1, p2);  
   _ASSERTE(p1 == p2);  
  
   _RPT2(_CRT_ERROR, "'%s' != '%s'\n", p1, p2);  
  
   free(p2);  
   free(p1);  
  
   return 0;  
}  
```  
  
```Output  
Use the assert macros to evaluate the expression p1 == p2.  
crt_ASSERT_macro.c(54) :   
 Will _ASSERT find 'I am p1' == 'I am p2' ?  
crt_ASSERT_macro.c(55) : Assertion failed!  
crt_ASSERT_macro.c(58) :   
  
 Will _ASSERTE find 'I am p1' == 'I am p2' ?  
crt_ASSERT_macro.c(59) : Assertion failed: p1 == p2  
'I am p1' != 'I am p2'  
```  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [assert Macro, _assert, _wassert](../../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [_RPT, _RPTF, _RPTW, _RPTFW 매크로](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)