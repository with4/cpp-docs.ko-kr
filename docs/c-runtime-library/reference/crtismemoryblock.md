---
title: "_CrtIsMemoryBlock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtIsMemoryBlock"
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
  - "CrtlsMemoryBlock"
  - "_CrtIsMemoryBlock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtIsMemoryBlock 함수"
  - "CrtIsMemoryBlock 함수"
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _CrtIsMemoryBlock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 메모리 블록이 로컬 힙에 있는지, 그리고 올바른 디버그 힙의 블록 형식 식별자 \(디버그 버전에만 해당\)를 가지는지 확인합니다.  
  
## 구문  
  
```  
int _CrtIsMemoryBlock(   
   const void *userData,  
   unsigned int size,  
   long *requestNumber,  
   char **filename,  
   int *linenumber   
);  
```  
  
#### 매개 변수  
 \[in\] `userData`  
 확인하기 위한 메모리 블록의 시작 부분에 대한 포인터입니다.  
  
 \[in\] `size`  
 지정된 블록 크기\(바이트\).  
  
 \[out\] `requestNumber`  
 블록의 할당 번호에 대한 포인터 또는  `NULL` .  
  
 \[out\] `filename`  
 `NULL` 또는 블록을 요청하는 소스 파일의 이름에 대한 포인터입니다.  
  
 \[out\] `linenumber`  
 소스 파일의 줄 번호에 대한 포인터 또는  `NULL` .  
  
## 반환 값  
 지정 된 메모리 블록이 로컬 힙에 있고 올바른 디버그 힙의 블록 형식 식별자를 가질 경우, `_CrtIsMemoryBlock`는  `TRUE` 합니다.  그렇지 않으면 함수는  `FALSE` 를 반환합니다.  
  
## 설명  
 `_CrtIsMemoryBlock`  함수는 올바른 블록 형식 식별자를 가지는지, 응용 프로그램의 로컬 힙 내에 지정된 메모리 블록임을 확인합니다.  이 함수는 원래 메모리 블록 할당 요청된 개체 할당 순서 번호와 소스 파일 이름과 줄 번호 구하는 데도 사용할 수 있습니다.   `requestNumber` ,  `filename` , 또는  `linenumber`  매개변수에 대한 NULL이 아닌 값을 전달하는 것은  `_CrtIsMemoryBlock` 가  로컬 힙에 블록이 발견되면 디버그 메모리 블록 헤더의 값을 매개 변수로 설정하도록 만듭니다.  [\_DEBUG](../../c-runtime-library/debug.md)가 정의되어 있지 않으면 `_CrtIsMemoryBlock` 에 대한 호출은 전처리 동안 제거됩니다.  
  
 `_CrtIsMemoryBlock` 가 실패할 경우,  `FALSE` 을 반환하고 출력 매개 변수를 기본값으로 초기화 됩니다:  `requestNumber`  와  `lineNumber` 는  0으로 설정 되고  `filename`  는  `NULL` 로 설정됩니다.  
  
 이 함수는 `TRUE` 또는 `FALSE`를 반환 하기 때문에, [\_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)매크로 중 하나에 전달 되어 간단한 디버깅 오류 처리 메커니즘을 만들 수 있습니다.  다음 예제에서는 지정한 주소가 로컬 힙에 없을 때, 어설션 오류가 발생하는 것을 보여줍니다:  
  
```  
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,   
&filename, &linenumber ) );  
```  
  
 `_CrtIsMemoryBlock` 가 어떻게 기타 디버그 함수 및 매크로 함께 사용할 수 있는지에 대한 자세한 내용은[보고서 매크로](../Topic/Macros%20for%20Reporting.md)를 참조 하십시오.   기본 힙의 디버그 버전에서 메모리 블록이 어떻게 할당되고 초기화되고 관리되는지에 대한 자세한 내용은 [CRT 디버그 힙 정보](../Topic/CRT%20Debug%20Heap%20Details.md) 를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_CrtIsMemoryBlock`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 의 유일한 디버그 버전입니다.  
  
## 예제  
 [\_CrtIsValidHeapPointer](../../c-runtime-library/reference/crtisvalidheappointer.md) 항목의 대한 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)