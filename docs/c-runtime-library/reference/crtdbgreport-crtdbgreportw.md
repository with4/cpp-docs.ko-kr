---
title: "_CrtDbgReport, _CrtDbgReportW | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtDbgReport"
  - "_CrtDbgReportW"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "CrtDbgReport"
  - "CrtDbgReportW"
  - "_CrtDbgReportW"
  - "_CrtDbgReport"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "디버그 보고"
  - "_CrtDbgReport 함수"
  - "CrtDbgReport 함수"
  - "CrtDbgReportW 함수"
  - "_CrtDbgReportW 함수"
ms.assetid: 6e581fb6-f7fb-4716-9432-f0145d639ecc
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtDbgReport, _CrtDbgReportW
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

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
 모든 보고서 대상에 대해 `_CrtDbgReport` 및 `_CrtDbgReportW`는 오류가 발생하면 –1을 반환하고 오류가 발생하지 않으면 0을 반환합니다. 그러나 때 보고서 대상이 디버그 메시지 창이 고 사용자가는 **다시 시도** 단추, 이러한 함수는 1을 반환 합니다. 사용자가 클릭 하는 경우는 **중단** 단추 디버그 메시지 창에서 이러한 함수가 즉시 중단 하 고 값을 반환 하지 않습니다.  
  
  [_RPT, _RPTF](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) 매크로 호출을 디버그 `_CrtDbgReport` 보고서를 디버그를 생성 하려면. 이러한 매크로의 와이드 문자 버전으로 [_ASSERT & # 91이 고, &#93;](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), `_RPTW``n` 및 `_RPTFW``n`, 를 사용 하 여 `_CrtDbgReportW` 보고서를 디버그를 생성 하려면. JIT(Just-In-Time) 디버깅을 사용하도록 설정한 경우 `_CrtDbgReport` 또는 `_CrtDbgReportW`가 1을 반환하면 이러한 매크로는 디버거를 시작합니다.  
  
## <a name="remarks"></a>설명  
 `_CrtDbgReport` 및 `_CrtDbgReportW`는 3가지 다른 대상, 즉 디버그 보고서 파일, 디버그 모니터([!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] 디버그) 또는 디버그 메시지 창으로 디버거 보고서를 보낼 수 있습니다. 2 가지 구성 함수인 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) 및 [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md), 각 보고서 형식의 대상을 지정 하는 데 사용 됩니다. 이러한 함수를 사용하면 각 보고서 형식의 보고 대상을 개별적으로 제어할 수 있습니다. 예를 들어 `reportType`의 `_CRT_WARN`은 디버그 모니터로만 보내도록 하고 `reportType`의 `_CRT_ASSERT`은 디버그 메시지 창과 사용자 정의 보고서 파일로 보내도록 지정할 수 있습니다.  
  
 `_CrtDbgReportW`는 `_CrtDbgReport`의 와이드 문자 버전입니다. 이 함수의 모든 출력 및 문자열 매개 변수는 와이드 문자열에 있습니다. 이 점을 제외하면 이 함수는 싱글바이트 문자 버전과 동일합니다.  
  
 `_CrtDbgReport` 및 `_CrtDbgReportW`는 `argument` 또는 `n` 함수에서 정의한 동일한 규칙을 통해 `format`[`printf`] 인수를 `wprintf` 문자열로 대체하여 디버그 보고서에 대한 사용자 메시지를 만듭니다. 그런 다음 이러한 함수는 디버그 보고서를 생성하고 현재 보고서 모드와 `reportType`에 대해 정의된 파일을 기반으로 대상을 결정합니다. 보고서를 디버그 메시지 창으로 보내면 `filename`, `lineNumber` 및 `moduleName`이 창에 표시되는 정보에 포함됩니다.  
  
 다음 테이블은 사용 가능한 보고서 모드 및 파일 선택 항목과 `_CrtDbgReport` 및 `_CrtDbgReportW`의 결과 동작을 보여줍니다. 이러한 옵션은 \<crtdbg.h>에 비트 플래그에 정의되어 있습니다.  
  
|보고서 모드|보고서 파일|`_CrtDbgReport`, `_CrtDbgReportW` 동작|  
|-----------------|-----------------|------------------------------------------------|  
|`_CRTDBG_MODE_DEBUG`|해당 없음|Windows를 사용 하 여 메시지를 씁니다 [OutputDebugString](http://msdn.microsoft.com/library/windows/desktop/aa363362.aspx) API입니다.|  
|`_CRTDBG_MODE_WNDW`|해당 없음|Windows 호출 [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) API와 함께 메시지를 표시 하려면 메시지 상자를 만들려면 **중단**, **다시 시도**, 및 **무시** 단추입니다. 사용자가 클릭 **중단**, `_CrtDbgReport` 또는 `_CrtDbgReport` 즉시 중단 됩니다. 사용자가 클릭 **다시 시도**, 1을 반환 합니다. 사용자가 클릭 **무시**, 실행이 계속 되 고 `_CrtDbgReport` 및 `_CrtDbgReportW` 0을 반환 합니다. 클릭 하면 **무시** 때 오류 조건이 있는데 종종 "정의 되지 않은 동작 발생 합니다."|  
|`_CRTDBG_MODE_FILE`|`__HFILE`|메시지를 사용자가 제공한 씁니다 `HANDLE`, Windows를 사용 하 여 [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747.aspx) API 및 파일 핸들의 유효성을 확인 하지 않습니다; 보고서 파일 열기 및 유효한 파일 핸들 전달은 응용 프로그램이 있습니다.|  
|`_CRTDBG_MODE_FILE`|`_CRTDBG_FILE_STDERR`|`stderr`에 메시지를 씁니다.|  
|`_CRTDBG_MODE_FILE`|`_CRTDBG_FILE_STDOUT`|
          `stdout`에 메시지를 씁니다.|  
  
 보고서는 1개, 2개 또는 3개 대상으로 보내거나 아무 대상으로도 보내지 않을 수 있습니다. 보고서 모드 및 보고서 파일을 지정 하는 방법에 대 한 자세한 내용은 참조는 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) 및 [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) 함수입니다. 디버그 매크로 사용 하 여 및 보고 기능에 대 한 자세한 내용은 참조 [보고에 대 한 매크로](../Topic/Macros%20for%20Reporting.md)합니다.  
  
 응용 프로그램에서 제공 된 것 보다 더 뛰어난 유연성이 필요한 경우 `_CrtDbgReport` 및 `_CrtDbgReportW`, 자체 보고 함수를 작성 하 고 보고 메커니즘을 사용 하 여 C 런타임 라이브러리에 연결할 수는 [_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md) 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_CrtDbgReport`|\<crtdbg.h>|  
|`_CrtDbgReportW`|\<crtdbg.h>|  
  
 `_CrtDbgReport` 및 `_CrtDbgReportW`는 Microsoft 확장입니다. 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 디버그 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 만 합니다.  
  
## <a name="example"></a>예제  
  
```  
// crt_crtdbgreport.c  
#include <crtdbg.h>  
  
int main(int argc, char *argv[]) {  
#ifdef _DEBUG  
   _CrtDbgReport(_CRT_ASSERT, __FILE__, __LINE__, argv[0], NULL);  
#endif  
}  
```  
  
 참조 [crt_dbg2](http://msdn.microsoft.com/ko-kr/21e1346a-6a17-4f57-b275-c76813089167) 보고 함수를 변경 하는 방법의 예입니다.  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
  
-   [System::Diagnostics::Debug::Write](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.write.aspx)  
  
-   [System::Diagnostics::Debug::Writeline](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writeline.aspx)  
  
-   [System::Diagnostics::Debug::WriteIf](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writeif.aspx)  
  
-   [System::Diagnostics::Debug::WriteLineIf](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writelineif.aspx)  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)   
 [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [_DEBUG](../../c-runtime-library/debug.md)