---
title: "_RPT, _RPTF, _RPTW, _RPTFW 매크로 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
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
  - "RPT3"
  - "RPTF4"
  - "_RPT4"
  - "RPT1"
  - "_RPTF0"
  - "RPTF3"
  - "_RPTF4"
  - "RPTF1"
  - "RPT4"
  - "_RPT1"
  - "_RPT0"
  - "RPT0"
  - "_RPTF2"
  - "RPTF0"
  - "_RPT3"
  - "_RPT2"
  - "_RPTF3"
  - "RPT2"
  - "_RPTF1"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "디버깅[CRT], 매크로 사용"
  - "_RPTW3 매크로"
  - "_RPT0 매크로"
  - "RPTW4 매크로"
  - "_RPTF3 매크로"
  - "_RPTW4 매크로"
  - "RPTF4 매크로"
  - "RPTFW2 매크로"
  - "RPTW 매크로"
  - "RPT1 매크로"
  - "_RPTF 매크로"
  - "RPTFW3 매크로"
  - "_RPTW0 매크로"
  - "_RPTF0 매크로"
  - "매크로, 디버깅"
  - "_RPTW2 매크로"
  - "RPTF3 매크로"
  - "RPT3 매크로"
  - "RPT0 매크로"
  - "_RPT 매크로"
  - "RPTW3 매크로"
  - "_RPTFW 매크로"
  - "보고 매크로 디버그"
  - "RPTF 매크로"
  - "RPT 매크로"
  - "_RPTW 매크로"
  - "RPTF2 매크로"
  - "_RPTF1 매크로"
  - "_RPT1 매크로"
  - "_RPT4 매크로"
  - "_RPTFW2 매크로"
  - "_RPTFW1 매크로"
  - "RPTF0 매크로"
  - "_RPT2 매크로"
  - "RPTFW 매크로"
  - "_RPTW1 매크로"
  - "_RPTFW0 매크로"
  - "RPT4 매크로"
  - "_RPT3 매크로"
  - "_RPTFW3 매크로"
  - "_RPTF4 매크로"
  - "_RPTFW4 매크로"
  - "_RPTF2 매크로"
  - "RPTW0 매크로"
  - "RPTFW4 매크로"
  - "RPTFW0 매크로"
  - "RPTW2 매크로"
  - "RPTF1 매크로"
  - "RPT2 매크로"
  - "RPTFW1 매크로"
  - "RPTW1 매크로"
ms.assetid: a5bf8b30-57f7-4971-8030-e773b7a1ae13
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _RPT, _RPTF, _RPTW, _RPTFW 매크로
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\(디버그 버전에만 해당\) 디버그 보고서를 생성하여 응용 프로그램의 진행률을 추적합니다.  `args` 에서 인수의 갯수 *n* 을 지정합니다. 0,1,2,3,4 또는 5가 될 수 있습니다.  
  
## 구문  
  
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
  
#### 매개 변수  
 `reportType`  
 Report type: `_CRT_WARN`, `_CRT_ERROR`, 또는 `_CRT_ASSERT`.  
  
 `format`  
 사용자 메시지를 작성하는데 사용하는 컨트롤 서식 문자열입니다.  
  
 `args`  
 `format` 사용 되는 대체 인수입니다.  
  
## 설명  
 이러한 모든 매크로는 `reportType`와 `format`매개변수들을 받습니다.  또한, 매크로 이름에 추가 숫자를 넣어 표시하는 4개의 추가적인 인수들을 수행할 수 있습니다.  예를 들면, `_RPT0` 와 `_RPTF0` 는 추가적인 인수를 받지 않지만, `_RPT1` 와 `_RPTF1` 는 `arg1` 을 받고, `_RPT2` 와 `_RPTF2` 는 `arg1` 와 `arg2` 역시 받습니다.  
  
 `_RPT` 와 `_RPTF` 매크로는 디버깅 과정 동안 응용프로그램의 진행률을 추적하기 위해 사용될 수 있기 때문에 [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 와 유사합니다.  그러나, 이러한 매크로는 응용프로그램의 정식 빌드에서 호출됨으로 그들을 막기위해 `#ifdef` 문에서 묶을 필요가 없기 때문에, `printf` 보다 유연성을 갖고 있습니다.  이러한 유연성을 [DEBUG](../../c-runtime-library/debug.md) 매크로를 사용하여 얻을 수 있습니다: `_RPT` 와 `_RPTF` 매크로는 오직 `_DEBUG` 플래그가 정의되었을 때 이용할 수 있습니다.  `_DEBUG` 가 정의되지 않았을 때, 이러한 매크로를 호출하면 전처리시기에 제거됩니다.  
  
 `_RPTW` 와 `_RPTFW` 매크로는 이러한 매크로의 와이드 문자 벼전입니다.  이들은 `wprintf` 와 비슷하고 인수로써 와이드 문자열을 받습니다.  
  
 `_RPT` 매크로는 사용자 메시지와 함께 디버그 보고서를 생성하는 [\_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) 함수를 호출합니다.  `_RPTW` 매크로는 와이드 문자들과 함께 가틍ㄴ 보고서를 생성하기 위해 `_CrtDbgReportW` 함수를 호출합니다.  `_RPTF` 와 `_RPTFW` 매크로는 추가적으로 사용자 메시지를 위해 보고서 매크로가 호출되는 곳에서 줄 번호와 소스 파일을 사용하여 디버그 보고서를 생성합니다.  사용자 메시지는 [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 함수로 정의된 동일한 규칙을 사용하여 대체된 `arg`\[*n*\] 인수들을 `format` 문자열로 하여 생성됩니다.  
  
 `_CrtDbgReport` 와 `_CrtDbgReportW` 는 디버그 보고서를 생성하고 `reportType` 에 대해 정의된 파일과 현재 보고서 모드에 기반한 이것의 목적지를 결정합니다.  [\_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) 와 [\_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) 함수들은 각 보고서 형식에 대한 대상을 정의하기 위해 사용됩니다.  
  
 `_RPT` 매크로가 `_CrtSetReportMode` 와 `_CrtSetReportFile` 가 호출되어지지 않고 호출된 경우, 메시지는 다음과 같이 표시됩니다.  
  
|보고 형식|출력 대상|  
|-----------|-----------|  
|`_CRT_WARN`|경고 텍스트는 표시 되지 않습니다.|  
|`_CRT_ERROR`|팝업 창입니다.  `_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_WNDW);` 이 지정된 것과 같이|  
|`_CRT_ASSERT`|`_CRT_ERROR`와 동일합니다.|  
  
 대상이 디버그 메시지창이고 사용자가 **재시도** 버튼을 선택할 때, `_CrtDbgReport` 또는 `_CrtDbgReportW` 이 1을 반환하고, 디버를 시작하기위해 이 매크로를 시작하며, 적시\(JIT\) 디버깅이 활성화됩니다.  디버깅 오류를 처리하는 메커니즘으로 이 매크로를 사용하는 것에 관한 자세한 내용은 [확인과 보고에 대한 매크로 사용](../Topic/Macros%20for%20Reporting.md)을 참고하세요.  
  
 다른 두 개의 매크로가 디버그 보고서를 생성하기위해 존재합니다.  오직 인수식이 FLASE일 때. [\_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 매크로가 보고서를 생성합니다.  [\_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 는 정확하게 `_ASSERT` 와 같지만, 생성된 보고서에서 발생된 오류를 포함합니다.  
  
## 요구 사항  
  
|매크로|필수 헤더|  
|---------|-----------|  
|`_RPT` 매크로|\<crtdbg.h\>|  
|`_RPTF` 매크로|\<crtdbg.h\>|  
|`_RPTW` 매크로|\<crtdbg.h\>|  
|`_RPTFW` 매크로|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 의 유일한 디버그 버전입니다.  
  
 비록 이러한 매크로는 Crtdbg.h를 포함하여 얻게되지만, 응용프로그램은 이 매크로가 다른 런타임 함수들을 호출하기 때문에 디버그 라이브러리들 중 하나를 사용하여 연결해야 합니다.  
  
## 예제  
 [\_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 항목에서 이런 예제를 참조하세요.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)