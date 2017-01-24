---
title: "디버그 루틴 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.debug"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "디버깅[CRT], 매크로 사용"
  - "매크로, 디버깅"
  - "디버그 루틴"
  - "디버그 매크로"
  - "디버깅[CRT], 런타임 루틴"
ms.assetid: cb4d2664-10f3-42f7-a516-595558075471
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 디버그 루틴
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C 런타임 라이브러리의 디버그 버전은 개발자에게 디버깅 프로그램을 쉽게하고 수 많은 진단 서비스를 제공합니다.  
  
-   디버깅을 하는 동안 직접 런타임 함수를 한 단계씩 실행합니다.  
  
-   어설션, 오류 및 예외를 확인합니다.  
  
-   힙 할당을 추적하고 메모리 누수를 방지합니다.  
  
-   사용자에게 디버그 메시지를 보고합니다.  
  
 이러한 루틴을 사용하려면  [\_DEBUG](../c-runtime-library/debug.md) 플래그를 정의해야 합니다.  이 모든 루틴은 모든 응용 프로그램의 정식 버전 빌드에 아무 작업도 수행하지 않습니다.  새 디버그 루틴을 사용하는 방법에 대한 자세한 내용은  [CRT 디버깅 기술](../Topic/CRT%20Debugging%20Techniques.md)을 참조 하십시오.  
  
### C 런타임 라이브러리 루틴의 버전을 디버그합니다.  
  
|루틴|기능|해당 .NET Framework|  
|--------|--------|-----------------------|  
|[\_ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|식을 계산하고 결과가 FALSE일 경우 디버그 보고서를 생성합니다.|[\<caps:sentence id\="tgt15" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug:: 어설션\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[\_ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|`_ASSERT` 와 유사하지만 생성된 보고서에 오류가 발생한 식을 포함합니다.|[\<caps:sentence id\="tgt18" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug:: 어설션\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[\_CrtCheckMemory](../c-runtime-library/reference/crtcheckmemory.md)|디버그 힙에 할당된 메모리 블록의 무결성 확인합니다.|[\<caps:sentence id\="tgt20" sentenceid\="e42975224af21ff11a761e6a6bdbd602" class\="tgtSentence"\>System::Diagnostics::PerformanceCounter\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.performancecounter.aspx)|  
|[\_CrtDbgBreak](../c-runtime-library/reference/crtdbgbreak.md)|중단점을 설정합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_CrtDbgReport, \_CrtDbgReportW](../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)|사용자 메시지와 함께 디버그 보고서를 생성하고 세 가능한 대상에게 보고서를 보냅니다.|[System::Diagnostics::Debug::Write](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.write.aspx),  [System::Diagnostics::Debug::Writeline](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writeline.aspx),  [System::Diagnostics::Debug::WriteIf](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writeif.aspx),  [System::Diagnostics::Debug::WriteLineIf](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writelineif.aspx)|  
|[\_CrtDoForAllClientObjects](../c-runtime-library/reference/crtdoforallclientobjects.md)|힙의 모든  `_CLIENT_BLOCK`  형식에 대해 응용 프로그램에서 제공하는 함수를 호출합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_CrtDumpMemoryLeaks](../c-runtime-library/reference/crtdumpmemoryleaks.md)|중요한 메모리의 누수가 발생 하는 경우 디버그 힙의 모든 메모리 블록을 덤프합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_CrtIsMemoryBlock](../c-runtime-library/reference/crtismemoryblock.md)|올바른 디버그 힙 블록 형식 식별자가 있는지, 지정된 메모리 블록이 로컬 힙에 있는지 확인하십시오.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_CrtIsValidHeapPointer](../c-runtime-library/reference/crtisvalidheappointer.md)|로컬 힙에 대한 지정된 포인터인지 확인합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_CrtIsValidPointer](../c-runtime-library/reference/crtisvalidpointer.md)|지정한 메모리 범위가 읽기 및 쓰기에 대해 유효한지 확인합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_CrtMemCheckpoint](../c-runtime-library/reference/crtmemcheckpoint.md)|디버그 힙의 현재 상태를 가져오고 응용 프로그램에서 제공하는  `_CrtMemState`  구조에 저장합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_CrtMemDifference](../c-runtime-library/reference/crtmemdifference.md)|중요한 차이점에 대한 두 가지 메모리 상태를 비교 하고 결과를 반환합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_CrtMemDumpAllObjectsSince](../c-runtime-library/reference/crtmemdumpallobjectssince.md)|프로그램 실행의 시작 부분에서 지정한 검사점 찍은 후 힙 또는 개체에 대한 정보를 덤프합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_CrtMemDumpStatistics](../c-runtime-library/reference/crtmemdumpstatistics.md)|사용자가 읽을 수 있는 형식으로 지정된 메모리 상태에 대한 디버그 헤더 정보를 덤프합니다.|[\<caps:sentence id\="tgt64" sentenceid\="e42975224af21ff11a761e6a6bdbd602" class\="tgtSentence"\>System::Diagnostics::PerformanceCounter\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.performancecounter.aspx)|  
|[\_CrtReportBlockType](../c-runtime-library/reference/crtreportblocktype.md)|지정된 디버그 힙 블록 포인터와 관련된 블록 형식\/하위 형식을 반환합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_CrtSetAllocHook](../c-runtime-library/reference/crtsetallochook.md)|C 런타임 디버그 메모리 할당 프로세스에 연결하여 클라이언트 정의 할당 함수를 설치합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_CrtSetBreakAlloc](../c-runtime-library/reference/crtsetbreakalloc.md)|지정된 개체 할당 순서 번호에 중단점을 설정합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md)|해당  `_crtDbgFlag` 의 상태를 수정하거나 검색하여 디버그 힙 관리자의 할당 동작을 제어합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_CrtSetDumpClient](../c-runtime-library/reference/crtsetdumpclient.md)|`_CLIENT_BLOCK` 형식 메모리 블록을 덤프하기위해 디버그 덤프 함수를 호출할 때마다 호출되는 응용 프로그램 정의 함수를 설치합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_CrtSetReportFile](../c-runtime-library/reference/crtsetreportfile.md)|`_CrtDbgReport`의 특정 보고서 형식에 대한 대상으로 사용되는 파일 또는 스트림을 확인합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_CrtSetReportHook](../c-runtime-library/reference/crtsetreporthook.md)|C 런타임 디버그 보고 프로세스에 연결하여 클라이언트 정의 보고 함수를 설치합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_CrtSetReportHook2, \_CrtSetReportHookW2](../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md)|C 런타임 디버그 보고 프로세스에 연결하여 클라이언트 정의 보고 함수를 설치하거나 제거합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_CrtSetReportMode](../c-runtime-library/reference/crtsetreportmode.md)|`_CrtDbgReport`에 의해 생성된 특정 보고서 형식에 대한 일반적인 대상을 지정합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_RPT&#91;0,1,2,3,4&#93;](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|형식 문자열과 여러 개의 인수와 함께  `_CrtDbgReport`  호출하여 디버그 보고서를 생성하여 응용 프로그램의 진행률을 추적합니다.  원본 파일 및 줄 번호 정보를 제공합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_RPTF&#91;0,1,2,3,4&#93;](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|`_RPTn` 와 유사하지만 보고서 요청이 발생하는 줄번호와 소스 파일 이름을 제공합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_calloc\_dbg](../c-runtime-library/reference/calloc-dbg.md)|디버깅 헤더의 추가 공간을 사용하거나 버퍼를 덮어써서 힙에서 지정된 메모리 블록의 수를 할당합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_expand\_dbg](../c-runtime-library/reference/expand-dbg.md)|블록 크기를 확장 또는 축소하여 지정된 힙 메모리의 블록의 크기를 조절합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_free\_dbg](../c-runtime-library/reference/free-dbg.md)|힙에서 메모리 블록을 해제합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_fullpath\_dbg, \_wfullpath\_dbg](../c-runtime-library/reference/fullpath-dbg-wfullpath-dbg.md)|지정된 상대 경로 이름의 절대 경로나 전체 경로 이름을 만들고, [\_malloc\_dbg](../c-runtime-library/reference/malloc-dbg.md)을 사용하여 메모리를 할당할 수 있습니다.|[\<caps:sentence id\="tgt129" sentenceid\="57f5d14fd2f1847b8e44146f72e48f72" class\="tgtSentence"\>System::IO::File::Create\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)|  
|[\_getcwd\_dbg, \_wgetcwd\_dbg](../c-runtime-library/reference/getcwd-dbg-wgetcwd-dbg.md)|현재 작업 디렉터리를 얻고,  [\_malloc\_dbg](../c-runtime-library/reference/malloc-dbg.md)를 사용하여  메모리를 할당할 수 있습니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_malloc\_dbg](../c-runtime-library/reference/malloc-dbg.md)|디버깅 헤더의 추가 공간을 사용하거나 버퍼를 덮어써서 힙에서 메모리의 블록을 할당합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_msize\_dbg](../c-runtime-library/reference/msize-dbg.md)|힙에서 메모리 블록의 크기를 계산합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_realloc\_dbg](../c-runtime-library/reference/realloc-dbg.md)|블록의 크기를 조정하거나 이동하여 지정된 힙의 메모리 블록 할당합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_strdup\_dbg, \_wcsdup\_dbg](../c-runtime-library/reference/strdup-dbg-wcsdup-dbg.md)|문자열을 복제하고, [\_malloc\_dbg](../c-runtime-library/reference/malloc-dbg.md)를 사용하여 메모리를 할당할 수 있습니다.|[\<caps:sentence id\="tgt151" sentenceid\="74a4ca1462af4bfed5950888b5c554e1" class\="tgtSentence"\>System::String::Clone\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.string.clone.aspx)|  
|[\_tempnam\_dbg, \_wtempnam\_dbg](../c-runtime-library/reference/tempnam-dbg-wtempnam-dbg.md)|임시 파일을 만드는 데 사용할 수 있는 이름을 생성하고,  [\_malloc\_dbg](../c-runtime-library/reference/malloc-dbg.md)를 사용하여 메모리를 할당할 수 있습니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
  
 디버그 루틴은 디버깅 하는 동안 대부분의 다른 C 런타임 루틴에 대한 소스 코드를 통해 단계별로 사용할 수 있습니다.  그러나, Microsoft는 일부 기술을 독점하는 것으로 간주하여, 이러한 루틴에 대한 소스 코드는 제공하지 않습니다.  이러한 루틴 대부분은 예외 처리 또는 부동 소수점 처리 그룹에 속해 있지만 몇 가지 다른 사용자도 포함됩니다.  다음 표에서는 이러한 루틴들을 보여줍니다.  
  
### 소스 코드 형태로 제공되지 않는 C 런타임 루틴  
  
||||  
|-|-|-|  
|[acos, acosf, acosl](../c-runtime-library/reference/acos-acosf-acosl.md)|[\_fpclass](../c-runtime-library/reference/fpclass-fpclassf.md)|[\_nextafter](../c-runtime-library/reference/nextafter-functions.md)|  
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|[\_fpieee\_flt](../c-runtime-library/reference/fpieee-flt.md)|[pow](../c-runtime-library/reference/pow-powf-powl.md)|  
|[atan, atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[\_fpreset](../c-runtime-library/reference/fpreset.md)|[printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)\*|  
|[\_cabs](../c-runtime-library/reference/cabs.md)|[frexp](../c-runtime-library/reference/frexp.md)|[\_scalb](../c-runtime-library/reference/scalb.md)|  
|[ceil](../c-runtime-library/reference/ceil-ceilf-ceill.md)|[\_hypot](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|[scanf, \_scanf\_l, wscanf, \_wscanf\_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md), [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)\*|  
|[\_chgsign, \_chgsignf, \_chgsignl](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)|[\_isnan](../c-runtime-library/reference/isnan-isnan-isnanf.md)|[setjmp](../c-runtime-library/reference/setjmp.md)|  
|[\_clear87, \_clearfp](../c-runtime-library/reference/clear87-clearfp.md)|[\_j0](../misc/bessel-functions-j0-j1-jn.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|  
|[\_control87, \_controlfp, \_\_control87\_2](../c-runtime-library/reference/control87-controlfp-control87-2.md)|[\_j1](../misc/bessel-functions-j0-j1-jn.md)|[sinh](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|  
|[copysign, copysignf, copysignl, \_copysign, \_copysignf, \_copysignl](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)|[\_jn](../misc/bessel-functions-j0-j1-jn.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|  
|[cos](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|[ldexp](../c-runtime-library/reference/ldexp.md)|[\_status87, \_statusfp](../c-runtime-library/reference/status87-statusfp-statusfp2.md)|  
|[cosh](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|[log](../c-runtime-library/reference/log-logf-log10-log10f.md)|[tan](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[Exp](../c-runtime-library/reference/exp-expf.md)|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|[tanh](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[\_logb](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)|[\_y0](../Topic/Bessel%20Functions:%20_y0,%20_y1,%20_yn.md)|  
|[\_finite](../c-runtime-library/reference/finite-finitef.md)|[longjmp](../c-runtime-library/reference/longjmp.md)|[\_y1](../Topic/Bessel%20Functions:%20_y0,%20_y1,%20_yn.md)|  
|[floor](../c-runtime-library/reference/floor-floorf-floorl.md)|[\_matherr](../c-runtime-library/reference/matherr.md)|[\_yn](../Topic/Bessel%20Functions:%20_y0,%20_y1,%20_yn.md)|  
|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|[modf](../c-runtime-library/reference/modf-modff-modfl.md)||  
  
 \* 소스 코드를이 루틴들을 사용할 수 있지만 소스 코드가 제공 되지 않는 다른 루틴에 대한 내부 호출을 만듭니다.  
  
 일부 C 런타임 함수 및 c \+ \+ 연산자는 응용 프로그램의 디버그 빌드를 호출할 때 다르게 동작합니다. \(응용 프로그램의 디버그 빌드는   `_DEBUG`  플래그를 정의하거나 C 런타임 라이브러리의 디버그 버전과 연결하여 수행할 수 있습니다.\) 동작의 차이는 일반적으로 디버깅 프로세스를 지원하는 루틴에 의해 제공된 정보 또는 추가 기능을 구성합니다.  다음 표에서는 이러한 루틴들을 보여줍니다.  
  
### 응용 프로그램의 빌드 디버그에서 다르게 작동하는 루틴  
  
|||  
|-|-|  
|C  [중단](../c-runtime-library/reference/abort.md) 루틴|C\+\+ [delete](../cpp/delete-operator-cpp.md) 연산자|  
|C  [assert](../c-runtime-library/reference/assert-macro-assert-wassert.md) 루틴|C\+\+ [new](../cpp/new-operator-cpp.md) 연산자|  
  
## 참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)   
 [런타임 오류 검사](../c-runtime-library/run-time-error-checking.md)