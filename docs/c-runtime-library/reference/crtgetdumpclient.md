---
title: "_CrtGetDumpClient | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtGetDumpClient"
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
  - "CrtGetDumpClient"
  - "_CrtGetDumpClient"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtGetDumpClient 함수"
  - "CrtGetDumpClient 함수"
ms.assetid: 9051867f-341b-493b-b53d-45d2b454a3ad
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _CrtGetDumpClient
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`_CLIENT_BLOCK`  메모리 블록 \(디버그 버전에만 해당\)을 덤프하는 동안, 현재 응용 프로그램 정의 함수를 검색합니다.  
  
## 구문  
  
```  
_CRT_DUMP_CLIENT _CrtGetDumpClient( void );  
```  
  
## 반환 값  
 현재 덤프 루틴을 반환합니다.  
  
## 설명  
 `_CrtGetDumpClient`  함수는 C 런타임 디버그 메모리 덤프 프로세스에서  `_CLIENT_BLOCK`  메모리 블록에 저장된 개체를 덤프하는 동안 현재 후크 함수를 검색합니다.  
  
 다른 후크를 사용할 수 있는 런타임 함수를 사용하는 방법과 자신의 클라이언트 정의 후크 함수를 작성하는 방법에 대한 자세한 내용은  [디버그 후크 함수 작성](../Topic/Debug%20Hook%20Function%20Writing.md)를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_CrtGetDumpClient`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 의 유일한 디버그 버전입니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [\_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)   
 [\_CrtSetDumpClient](../../c-runtime-library/reference/crtsetdumpclient.md)