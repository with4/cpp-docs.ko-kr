---
title: "_RPT, _RPTF, _RPTW, _RPTFW 매크로 | Microsoft Docs"
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
- RPT3
- RPTF4
- _RPT4
- RPT1
- _RPTF0
- RPTF3
- _RPTF4
- RPTF1
- RPT4
- _RPT1
- _RPT0
- RPT0
- _RPTF2
- RPTF0
- _RPT3
- _RPT2
- _RPTF3
- RPT2
- _RPTF1
dev_langs: C++
helpviewer_keywords:
- debugging [CRT], using macros
- _RPTW3 macro
- _RPT0 macro
- RPTW4 macro
- _RPTF3 macro
- _RPTW4 macro
- RPTF4 macro
- RPTFW2 macro
- RPTW macros
- RPT1 macro
- _RPTF macros
- RPTFW3 macro
- _RPTW0 macro
- _RPTF0 macro
- macros, debugging with
- _RPTW2 macro
- RPTF3 macro
- RPT3 macro
- RPT0 macro
- _RPT macros
- RPTW3 macro
- _RPTFW macros
- debug reporting macros
- RPTF macros
- RPT macros
- _RPTW macros
- RPTF2 macro
- _RPTF1 macro
- _RPT1 macro
- _RPT4 macro
- _RPTFW2 macro
- _RPTFW1 macro
- RPTF0 macro
- _RPT2 macro
- RPTFW macros
- _RPTW1 macro
- _RPTFW0 macro
- RPT4 macro
- _RPT3 macro
- _RPTFW3 macro
- _RPTF4 macro
- _RPTFW4 macro
- _RPTF2 macro
- RPTW0 macro
- RPTFW4 macro
- RPTFW0 macro
- RPTW2 macro
- RPTF1 macro
- RPT2 macro
- RPTFW1 macro
- RPTW1 macro
ms.assetid: a5bf8b30-57f7-4971-8030-e773b7a1ae13
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 453b04174325a7c112105bdef1147e1b7909ccdb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="rpt-rptf-rptw-rptfw-macros"></a>_RPT, _RPTF, _RPTW, _RPTFW 매크로
디버그 보고서를 생성하여 응용 프로그램의 진행률을 추적합니다(디버그 버전에만 해당함).  *n*  의 인수 개수를 지정 `args` 이며 0, 1, 2, 3, 4 또는 5 일 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      _RPT  
      n  
      (  
   reportType,  
   format,  
...[args]  
);  
_RPTFn(  
   reportType,  
   format,  
   [args]  
);  
_RPTWn(  
   reportType,  
   format   
   [args]  
);  
_RPTFWn(  
   reportType,  
   format   
   [args]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `reportType`  
 보고서 형식(`_CRT_WARN`, `_CRT_ERROR` 또는 `_CRT_ASSERT`)입니다.  
  
 `format`  
 사용자 메시지를 만드는 데 사용되는 형식 제어 문자열입니다.  
  
 `args`  
 `format`에서 사용하는 대체 인수입니다.  
  
## <a name="remarks"></a>설명  
 이러한 모든 매크로는 `reportType` 및 `format` 매개 변수입니다. 또한 매크로 이름에 추가된 번호로 표시되는 추가 인수도 4개까지 사용할 수 있습니다. 예를 들어 `_RPT0` 및 `_RPTF0`은 추가 인수를 사용하지 않고, `_RPT1` 및 `_RPTF1`은 `arg1`, `_RPT2`를 사용하며, `_RPTF2`는 `arg1` 및 `arg2`를 사용하는 식입니다.  
  
 `_RPT` 및 `_RPTF` 매크로는 디버깅 프로세스 중에 응용 프로그램의 진행률을 추적하는 데 사용할 수 있으므로 [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 함수와 비슷합니다. 그러나 이들 매크로는 응용 프로그램의 정품 빌드 시 호출되지 않도록 `#ifdef` 문에 포함할 필요가 없으므로 `printf`에 비해 매우 유연합니다. 이처럼 매크로가 유연한 것은 [_DEBUG](../../c-runtime-library/debug.md) 매크로를 사용하기 때문입니다. `_RPT` 및 `_RPTF` 매크로는 `_DEBUG` 플래그를 정의할 때만 사용할 수 있습니다. `_DEBUG` 가 정의되지 않으면 이러한 매크로 호출이 전처리 중에 제거됩니다.  
  
 `_RPTW` 및 `_RPTFW` 매크로는 이러한 매크로의 와이드 문자 버전입니다. 이러한 매크로는 `wprintf`처럼 와이드 문자열을 인수로 사용합니다.  
  
 `_RPT` 매크로는 [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) 함수를 호출하여 사용자 메시지가 포함된 디버그 보고서를 생성합니다. `_RPTW` 매크로는 `_CrtDbgReportW` 함수를 호출하여 와이드 문자가 포함된 동일 보고서를 생성합니다. `_RPTF` 및 `_RPTFW` 매크로는 보고서 매크로가 호출된 소스 파일과 줄 번호 및 사용자 메시지를 사용하여 디버그 보고서를 만듭니다. 사용자 메시지를 대체 하 여 작성는 `arg`[*n*] 인수는 `format` 문자열에 의해 정의 된 동일한 규칙을 사용 하는 [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 함수입니다.  
  
 `_CrtDbgReport` 또는 `_CrtDbgReportW`는 디버그 보고서를 생성하고 `reportType`에 대해 정의된 파일 및 현재 보고서 모드에 따라 해당 대상을 결정합니다. [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) 및 [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) 함수는 각 보고서 종류의 대상을 정의하는 데 사용됩니다.  
  
 `_RPT` 매크로가 호출되었는데 `_CrtSetReportMode`와 `_CrtSetReportFile`은 둘 다 호출되지 않은 경우에는 메시지가 다음과 같이 표시됩니다.  
  
|보고서 종류|출력 대상|  
|-----------------|------------------------|  
|`_CRT_WARN`|경고 텍스트가 표시되지 않습니다.|  
|`_CRT_ERROR`|팝업 창이 표시됩니다. `_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_WNDW);`를 지정한 경우와 동일합니다.|  
|`_CRT_ASSERT`|`_CRT_ERROR`와 동일합니다.|  
  
 대상이 디버그 메시지 창이고 사용자가 **다시 시도** 단추를 선택하면 `_CrtDbgReport` 또는 `_CrtDbgReportW`가 1을 반환하고, 이에 따라 JIT(Just-In-Time) 디버깅이 사용하도록 설정된 경우 이러한 매크로가 디버거를 시작합니다. 이들 매크로를 디버깅 오류 처리 메커니즘으로 사용하는 방법에 대한 자세한 내용은 [확인 및 보고에 매크로 사용](/visualstudio/debugger/macros-for-reporting)을 참조하세요.  
  
 디버그 보고서를 생성하는 두 가지 다른 매크로가 있습니다. [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 매크로는 해당 식 인수가 FALSE인 경우에 한해 보고서를 생성합니다. [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)는 `_ASSERT`와 정확히 동일하지만 생성된 보고서에 실패한 식이 포함됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|매크로|필수 헤더|  
|-----------|---------------------|  
|`_RPT` 매크로|\<crtdbg.h>|  
|`_RPTF` 매크로|\<crtdbg.h>|  
|`_RPTW` 매크로|\<crtdbg.h>|  
|`_RPTFW` 매크로|\<crtdbg.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.  
  
 이러한 항목은 매크로이며 Crtdbg.h를 포함하면 가져올 수 있지만, 이러한 매크로는 다른 런타임 함수를 호출하므로 응용 프로그램을 디버그 라이브러리 중 하나와 연결해야 합니다.  
  
## <a name="example"></a>예  
 [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 항목의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)