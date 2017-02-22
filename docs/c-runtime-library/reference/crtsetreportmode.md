---
title: "_CrtSetReportMode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetReportMode"
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
  - "_CrtSetReportMode"
  - "CrtSetReportMode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtSetReportMode 함수"
  - "CrtSetReportMode 함수"
ms.assetid: 3ecc6a12-afdd-4242-b046-8187ff6d4b36
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _CrtSetReportMode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\_ASSERT, \_ASSERTE, \_ASSERT\_EXPR 매크로](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), [\_ASSERT, \_ASSERTE, \_ASSERT\_EXPR 매크로](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), [\_RPT, \_RPTF, \_RPTW, \_RPTFW 매크로](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md), 및 [\_RPT, \_RPTF, \_RPTW, \_RPTFW 매크로](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) \(디버그 버전에만 해당\)와 같은 [\_CrtDbgReport, \_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) 를 호출하는 매크로나  `_CrtDbgReport` 에 의해 생성되는 특정 보고서 형식에 대한 대상 또는 대상들을 지정합니다.  
  
## 구문  
  
```  
int _CrtSetReportMode(   
   int reportType,  
   int reportMode   
);  
```  
  
#### 매개 변수  
 `reportType`  
 보고서 형식: `_CRT_WARN`, `_CRT_ERROR`, 및 `_CRT_ASSERT`.  
  
 `reportMode`  
 새 보고서 모드 또는  `reportType`  모드들.  
  
## 반환 값  
 성공적으로 완료했을 때,  `_CrtSetReportMode` 은   `reportType` 에 지정된 보고서 형식에 대한 이전 보고서 모드 또는 모드를 반환합니다.   `reportType` 같은 곳으로 잘못 된 값이 전달 되거나  `reportMode` 에  잘못된 모드를 지정할 경우,  `_CrtSetReportMode` 은 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된대로 잘못된 매개 변수 처리기를 호출합니다.  실행이 계속적으로 이루어질 경우, 이 함수는  `errno`을 `EINVAL` 로 설정한 뒤 \-1을 반환합니다.  자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `_CrtSetReportMode`은  `_CrtDbgReport` 의 출력 위치를 지정합니다.   `_ASSERT` ,  `_ASSERTE` ,  `_RPT` , 및  `_RPTF`  매크로가   `_CrtDbgReport` 을 호출하기 때문에,  `_CrtSetReportMode`  매크로 사용하여 지정된 텍스트의 출력 대상을 지정합니다.  
  
 이 [\_DEBUG](../../c-runtime-library/debug.md) 가 정의되어 있지 않으면 프로세싱중에 `_CrtSetReportMode` 에 대한 호출을 제거 됩니다.  
  
 메시지의 출력 대상을 정의하기 위한  `_CrtSetReportMode` 가 호출되지 않으면, 다음과 같은 기본값이 적용됩니다.  
  
-   어설션 실패 및 오류는 디버그 메시지 창으로 이동합니다.  
  
-   Windows 응용 프로그램의 경고는 디버거의 출력 창으로 보내집니다.  
  
-   콘솔 응용 프로그램에서 발생한 경고는 표시되지 않습니다.  
  
 다음 표는 Crtdbg.h에 정의된 보고서 형식을 나열합니다.  
  
|보고 형식|설명|  
|-----------|--------|  
|`_CRT_WARN`|경고, 메시지 및 정보는 즉각적인 주의가 필요하지 않습니다.|  
|`_CRT_ERROR`|오류, 복구할 수 없는 문제 및 이슈는 즉시 처리해야 합니다.|  
|`_CRT_ASSERT`|어설션 오류 \( `FALSE` 로 계산한 어설션 식\).|  
  
 `_CrtSetReportMode`  함수는  `reportType` 의 보고서 형식을 지정하기 위해  `reportMode`  에 지정된 새 보고서 모드를 지정하고,    `reportType` 에 대해 이전에 정의된 보고서를 반환합니다.  다음 표에서 사용 가능한 선택 목록이 `reportMode` 의 동작 결과 `_CrtDbgReport`입니다.  이러한 옵션은 비트 플래그로 Crtdbg.h에 정의됩니다.  
  
|보고서 모드|\_CrtDbgReport 동작|  
|------------|-----------------------|  
|`_CRTDBG_MODE_DEBUG`|디버거의 출력 창에 메시지를 씁니다.|  
|`_CRTDBG_MODE_FILE`|사용자가 제공한 파일 핸들을 메시지에 기록합니다.  [\_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md)은 특정 파일 또는 대상으로 사용하는 스트림을 정의하기 위해 호출합니다.|  
|`_CRTDBG_MODE_WNDW`|`Abort` ,  `Retry` , 및  `Ignore`  단추를 메세지에 함께 표시하기 위해 메시지 상자를 만듭니다.|  
|`_CRTDBG_REPORT_MODE`|지정된 `reportType`에 대한 `reportMode`를 반환합니다.<br /><br /> 1   `_CRTDBG_MODE_FILE`<br /><br /> 2   `_CRTDBG_MODE_DEBUG`<br /><br /> 4   `_CRTDBG_MODE_WNDW`|  
  
 하나, 둘 또는 세 개의 모드 또는 모두 모드 없음을 사용하여 각 보고서 유형을 보고할 수 있습니다.  따라서, 이 단일 보고서 형식에 대해 정의된 하나 이상의 대상에 있을 수 있습니다.  예를 들어, 다음 코드는 창과  `stderr` 에 어설션 오류 디버그 메시지 모두를 보낼 수 있습니다.  
  
```  
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );  
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );  
```  
  
 또한, 보고 모드 또는 각 보고서 형식에 대한 모드는 별도로 제어할 수 있습니다.  예를 들어, 디버그 메시지 창을 사용하여  `_CRT_ASSERT` 가 표시되거나  `stderr`  전송 되었을 동안  `_CRT_WARN` 의  `reportType` 가 출력 디버그 문자열에 전송되는 것을 지정할 수 있습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_CrtSetReportMode`|\<crtdbg.h\>|\<\<errno.h\>\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
 **라이브러리:** [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md) 의 유일한 디버그 버전  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)