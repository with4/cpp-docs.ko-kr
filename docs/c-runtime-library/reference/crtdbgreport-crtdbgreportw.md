---
title: "_CrtDbgReport, _CrtDbgReportW | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtDbgReport
- _CrtDbgReportW
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
- CrtDbgReport
- CrtDbgReportW
- _CrtDbgReportW
- _CrtDbgReport
dev_langs:
- C++
helpviewer_keywords:
- debug reporting
- _CrtDbgReport function
- CrtDbgReport function
- CrtDbgReportW function
- _CrtDbgReportW function
ms.assetid: 6e581fb6-f7fb-4716-9432-f0145d639ecc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4720053f96972c6ff0d846b9641d9ddc2d256f20
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2018
---
# <a name="crtdbgreport-crtdbgreportw"></a>_CrtDbgReport, _CrtDbgReportW
디버깅 메시지가 포함된 보고서를 생성하고 이 보고서를 가능한 대상 3개로 보냅니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
int _CrtDbgReport(   
   int reportType,  
   const char *filename,  
   int linenumber,  
   const char *moduleName,  
   const char *format [,  
   argument] ...   
);  
int _CrtDbgReportW(   
   int reportType,  
   const wchar_t *filename,  
   int linenumber,  
   const wchar_t *moduleName,  
   const wchar_t *format [,  
   argument] ...   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `reportType`  
 보고서 형식: `_CRT_WARN`, `_CRT_ERROR` 및 `_CRT_ASSERT`  
  
 `filename`  
 어설션/보고서 또는 `NULL`이 발생한 소스 파일의 이름에 대한 포인터입니다.  
  
 `linenumber`  
 assert/report 또는 `NULL`이 발생한 소스 파일의 줄 번호입니다.  
  
 `moduleName`  
 어설션 또는 보고서가 발생한 모듈(.exe 또는 .dll)의 이름에 대한 포인터입니다.  
  
 `format`  
 사용자 메시지를 만드는 데 사용되는 형식 컨트롤 문자열에 대한 포인터입니다.  
  
 `argument`  
 `format`에서 사용하는 선택적 대체 인수입니다.  
  
## <a name="return-value"></a>반환 값  
 모든 보고서 대상에 대 한 `_CrtDbgReport` 및 `_CrtDbgReportW` 없는 오류가 발생 한 경우 오류가 발생 한 경우-1과 0을 반환 합니다. 그러나 보고서 대상이 디버그 메시지 창이고 사용자가 **다시 시도** 단추를 클릭하면 이러한 함수는 1을 반환합니다. 사용자가 디버그 메시지 창에서 **중단** 단추를 클릭하면 이러한 함수가 즉시 중단되고 값을 반환하지 않습니다.  
  
 [_RPT, _RPTF](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) 디버그 매크로는 `_CrtDbgReport`를 호출하여 디버그 보고서를 생성합니다. [_ASSERT[E]](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), `_RPTW n` 및 `_RPTFW n`뿐만 아니라 이러한 매크로의 와이드 문자 버전은 `_CrtDbgReportW`를 사용하여 디버그 보고서를 생성합니다. JIT(Just-In-Time) 디버깅을 사용하도록 설정한 경우 `_CrtDbgReport` 또는 `_CrtDbgReportW`가 1을 반환하면 이러한 매크로는 디버거를 시작합니다.  
  
## <a name="remarks"></a>설명  
 `_CrtDbgReport` 및 `_CrtDbgReportW`는 3가지 다른 대상, 즉 디버그 보고서 파일, 디버그 모니터([!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] 디버그) 또는 디버그 메시지 창으로 디버거 보고서를 보낼 수 있습니다. 두 구성 함수인 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)와 [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md)은 각 보고서 형식의 대상을 지정하는 데 사용됩니다. 이러한 함수를 사용하면 각 보고서 형식의 보고 대상을 개별적으로 제어할 수 있습니다. 예를 들어 `reportType`의 `_CRT_WARN`은 디버그 모니터로만 보내도록 하고 `reportType`의 `_CRT_ASSERT`은 디버그 메시지 창과 사용자 정의 보고서 파일로 보내도록 지정할 수 있습니다.  
  
 `_CrtDbgReportW`는 `_CrtDbgReport`의 와이드 문자 버전입니다. 이 함수의 모든 출력 및 문자열 매개 변수는 와이드 문자열에 있습니다. 이 점을 제외하면 이 함수는 싱글바이트 문자 버전과 동일합니다.  
  
 `_CrtDbgReport` 및 `_CrtDbgReportW`는 `argument` 또는 `n` 함수에서 정의한 동일한 규칙을 통해 `format`[`printf`] 인수를 `wprintf` 문자열로 대체하여 디버그 보고서에 대한 사용자 메시지를 만듭니다. 그런 다음 이러한 함수는 디버그 보고서를 생성하고 현재 보고서 모드와 `reportType`에 대해 정의된 파일을 기반으로 대상을 결정합니다. 보고서를 디버그 메시지 창으로 보내면 `filename`, `lineNumber` 및 `moduleName`이 창에 표시되는 정보에 포함됩니다.  
  
 다음 테이블은 사용 가능한 보고서 모드 및 파일 선택 항목과 `_CrtDbgReport` 및 `_CrtDbgReportW`의 결과 동작을 보여줍니다. 이러한 옵션은 \<crtdbg.h>에서 비트 플래그로 정의되어 있습니다.  
  
|보고서 모드|보고서 파일|`_CrtDbgReport`, `_CrtDbgReportW` 동작|  
|-----------------|-----------------|------------------------------------------------|  
|`_CRTDBG_MODE_DEBUG`|적용할 수 없음|Windows [OutputDebugString](http://msdn.microsoft.com/library/windows/desktop/aa363362.aspx) API를 사용하여 메시지를 작성합니다.|  
|`_CRTDBG_MODE_WNDW`|적용할 수 없음|Windows [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) API를 호출하여 **중단**, **다시 시도** 및 **무시** 단추와 함께 메시지를 표시하는 메시지 상자를 만듭니다. 사용자가 **중단**을 클릭하면 `_CrtDbgReport` 또는 `_CrtDbgReport`가 즉시 중단됩니다. 사용자가 **다시 시도**를 클릭하면 1이 반환됩니다. 사용자가 **무시**를 클릭하면 실행이 계속되고 `_CrtDbgReport` 및 `_CrtDbgReportW`가 0을 반환합니다. 오류 조건이 있을 때 **무시**를 클릭하면 종종 "정의되지 않은 동작"이 발생할 수 있습니다.|  
|`_CRTDBG_MODE_FILE`|`__HFILE`|Windows [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747.aspx) API를 사용하여 사용자가 제공한 `HANDLE`에 메시지를 작성하지만 파일 핸들의 유효성을 검사하지는 않습니다. 보고서 파일 열기 및 유효한 파일 핸들 전달은 응용 프로그램에서 담당합니다.|  
|`_CRTDBG_MODE_FILE`|`_CRTDBG_FILE_STDERR`|`stderr`에 메시지를 씁니다.|  
|`_CRTDBG_MODE_FILE`|`_CRTDBG_FILE_STDOUT`|`stdout`에 메시지를 씁니다.|  
  
 보고서는 1개, 2개 또는 3개 대상으로 보내거나 아무 대상으로도 보내지 않을 수 있습니다. 보고서 모드 및 보고서 파일을 지정하는 방법에 대한 자세한 내용은 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) 및 [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) 함수를 참조하세요. 디버그 매크로 및 보고 함수 사용에 대한 자세한 내용은 [보고서 매크로](/visualstudio/debugger/macros-for-reporting)를 참조하세요.  
  
 응용 프로그램에 `_CrtDbgReport` 및 `_CrtDbgReportW`에서 제공하는 것보다 더 뛰어난 유연성이 필요한 경우 고유한 보고 함수를 작성한 후 [_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md) 함수를 사용하여 C 런타임 라이브러리 보고 메커니즘에 이 보고 함수를 연결할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_CrtDbgReport`|\<crtdbg.h>|  
|`_CrtDbgReportW`|\<crtdbg.h>|  
  
 `_CrtDbgReport` 및 `_CrtDbgReportW`는 Microsoft 확장입니다. 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.  
  
## <a name="example"></a>예  
  
```  
// crt_crtdbgreport.c  
#include <crtdbg.h>  
  
int main(int argc, char *argv[]) {  
#ifdef _DEBUG  
   _CrtDbgReport(_CRT_ASSERT, __FILE__, __LINE__, argv[0], NULL);  
#endif  
}  
```  
  
 보고 함수 변경 방법의 예는 [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)   
 [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [_DEBUG](../../c-runtime-library/debug.md)