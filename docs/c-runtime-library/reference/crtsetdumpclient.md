---
title: "_CrtSetDumpClient | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetDumpClient"
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
  - "_CrtSetDumpClient"
  - "CrtSetDumpClient"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtSetDumpClient 함수"
  - "CrtSetDumpClient 함수"
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _CrtSetDumpClient
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

응용 프로그램 정의 함수를 설치하여,  `_CLIENT_BLOCK`  메모리 블록 \(디버그 버전에만 해당\)를 덤프합니다.  
  
## 구문  
  
```  
  
      _CRT_DUMP_CLIENT _CrtSetDumpClient(   
   _CRT_DUMP_CLIENT dumpClient   
);  
```  
  
#### 매개 변수  
 `dumpClient`  
 C 런타임 디버그 메모리 덤프 프로세스에 연결한 새 클라이언트 메모리 덤프 함수  
  
## 반환 값  
 이전에 정의 된 클라이언트 블록 덤프 함수를 반환합니다.  
  
## 설명  
 `_CrtSetDumpClient` 함수는 응용프로그램이 C 런타임 디버그 메모리 덤프 프로세스의  `_CLIENT_BLOCK`  메모리 블록에 저장된 개체를 덤프하기위해 후크 자체 함수에 연결하도록 합니다.   따라서, [\_CrtMemDumpAllObjectsSince](../../c-runtime-library/reference/crtmemdumpallobjectssince.md) 또는  [\_CrtDumpMemoryLeaks](../../c-runtime-library/reference/crtdumpmemoryleaks.md) 와 같은디버그 덤프 함수가  `_CLIENT_BLOCK`  메모리 블록을 덤프할 떄마다, 응용 프로그램의 덤프 함수도 호출됩니다.  `_CrtSetDumpClient`는 유효성 검사와  `_CLIENT_BLOCK`  블록에 저장된 데이터의 내용을 보고 메모리 누수를 탐지를 쉽게 방법을 사용하여 응용 프로그램을 제공합니다.  [\_DEBUG](../../c-runtime-library/debug.md)가 정의되어 있지 않으면 `_CrtSetDumpClient` 에 대한 호출은 전처리 동안 제거됩니다.  
  
 `_CrtSetDumpClient`  함수는  `dumpClient` 에 지정 된 새 응용프로그램 정의 덤프 함수를 설치하고  이전에 정의 된 덤프 함수를 반환합니다.  클라이언트 블록 덤프 함수의 예는 다음과 같습니다.  
  
```  
void DumpClientFunction( void *userPortion, size_t blockSize );  
```  
  
 `userPortion`  인수는 메모리 블록의 사용자 데이터 부분의 시작 부분에 대한 포인터이며   `blockSize` 는 바이트 블록 할당된 된 메모리의 크기를 지정합니다.  클라이언트 블록 덤프 함수는  `void` 를 반환해야 합니다.  `_CrtSetDumpClient`에 전달한 클라이언트 덤프 함수에 대한 포인터는 CRTDBG.H에 정의된 것과 같은 `_CRT_DUMP_CLIENT` 형식입니다.  
  
```  
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );  
```  
  
 `_CLIENT_BLOCK`  형식 메모리 블록에서 작동 하는 함수에 대한 자세한 내용은 [클라이언트 블록 후크 함수](../Topic/Client%20Block%20Hook%20Functions.md)을 참조하십시오.   [\_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md) 함수는 블록 형식 및 하위 형식에 대한 정보를 반환할 때 사용합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_CrtSetDumpClient`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 의 유일한 디버그 버전입니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [\_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)   
 [\_CrtGetDumpClient](../../c-runtime-library/reference/crtgetdumpclient.md)