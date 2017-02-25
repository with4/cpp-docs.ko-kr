---
title: "_CrtSetReportHook | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetReportHook"
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
  - "_CrtSetReportHook"
  - "CrtSetReportHook"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CrtSetReportHook 함수"
  - "_CrtSetReportHook 함수"
ms.assetid: 1ae7c64f-8c84-4797-9574-b59f00f7a509
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _CrtSetReportHook
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C 런타임 디버그 보고 프로세스 \(디버그 버전에만 해당\)에 연결하여 클라이언트 정의 보고 함수를 설치합니다.  
  
## 구문  
  
```  
_CRT_REPORT_HOOK _CrtSetReportHook(   
   _CRT_REPORT_HOOK reportHook   
);  
```  
  
#### 매개 변수  
 `reportHook`  
 C 런타임에 연결된 새 클라이언트 정의 보고 함수는 보고 프로세스를 디버깅합니다.  
  
## 반환 값  
 이전의 클라이언트 정의 보고 함수를 반환합니다.  
  
## 설명  
 `_CrtSetReportHook`는 C 런타임 디버그 라이브러리 보고 프로세스에서 응용을 프로그램이 보고 기능을 사용할 수 있도록합니다.  결과적으로, [\_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)가 디버그 보고서를 생성하기 위해 호출될 때마다, 응용 프로그램의 보고 함수는 처음으로 호출됩니다.  이 기능을 사용하면 응용프로그램이 디버그 보고서를 필터링 하는 등의 작업을 수행할 수 있습니다. 그래서 특정한 할당 형식에 초점을 두거나   `_CrtDbgReport` 을 사용해 목적지로 보고서를 보낼 수 있습니다.  [\_DEBUG](../../c-runtime-library/debug.md)가 정의되어 있지 않으면 `_CrtSetReportHook` 에 대한 호출은 전처리 동안 제거됩니다.  
  
 `_CrtSetReportHook` 더 강력한 버전에 대한 내용은 [\_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md)을 참조하십시오.  
  
 `_CrtSetReportHook`  함수는  `reportHook` 에 지정된 새로운 클라이언트 정의 보고 함수를 설치하며, 이전 클라이언트 정의 연결을 반환합니다.  다음 예제에서는 어떻게 클라이언트 정의 보고서 후크 프로토타입화 되어야하는지를 증명합니다.  
  
```  
int YourReportHook( int reportType, char *message, int *returnValue );  
```  
  
 `reportType`  는 디버그 보고서 형식 \(`_CRT_WARN`,  `_CRT_ERROR` , 또는  `_CRT_ASSERT` \)이며,  `message` 는 완전하게 조립된 디버그 사용자 메시지이며 보고서에 포함됩니다.  그리고  `returnValue`  는  `_CrtDbgReport` 에서 반환 되어야하는 클라이언트 정의 지정 함수에 의해 특별히 지정된 값입니다.  사용 가능한 보고서 유형의 설명에 대한 내용은 [\_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) 함수를 참조하십시오.  
  
 클라이언트 정의 보고 함수가 더이상 보고가 필요하지 않도록 디버그 메시지를 처리할 경우엔 , 함수는  `TRUE` 를 반환해야 합니다.  함수가   `FALSE`  반환 하는 경우엔, 보고서 형식, 모드 및 파일에 대한 현재 설정을 사용하여 디버그 보고서를 생성하기 위해  `_CrtDbgReport` 가  호출됩니다.  또한,  `returnValue` 에서  `_CrtDbgReport`  반환 값을 지정하여 , 응용 프로그램은 디버그 중단 발생 여부를 제어할 수 있습니다.  디버그 보고서를 구성하고 생성하는 방법의 자세한 내용은  `_CrtSetReportMode` ,  [\_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md), 및  `_CrtDbgReport` 을 참조 하십시오.  
  
 다른 후크를 사용할 수 있는 런타임 함수를 사용하는 방법과 자신의 클라이언트 정의 후크 함수를 작성하는 방법에 대한 자세한 내용은  [디버그 후크 함수 작성](../Topic/Debug%20Hook%20Function%20Writing.md)를 참조하십시오.  
  
> [!NOTE]
>  응용 프로그램이  `/clr` 로 컴파일되거나 보고 함수가 응용 프로그램이 종료될 때 호출될 떄,  보고 함수가 CRT 함수를 호출 하면 CLR은 예외를 throw 합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_CrtSetReportHook`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 의 유일한 디버그 버전입니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [\_CrtGetReportHook](../../c-runtime-library/reference/crtgetreporthook.md)