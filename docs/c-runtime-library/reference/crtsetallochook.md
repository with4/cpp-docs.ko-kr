---
title: "_CrtSetAllocHook | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetAllocHook"
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
  - "_CrtSetAllocHook"
  - "CrtSetAllocHook"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CrtSetAllocHook 함수"
  - "CrtSetAllocHook 함수"
ms.assetid: 405df37b-2fd1-42c8-83bc-90887f17f29d
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtSetAllocHook
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C 런타임 디버그 메모리 할당 프로세스 \(디버그 버전에만 해당\)에 연결하여 클라이언트 정의 할당 함수를 설치합니다.  
  
## 구문  
  
```  
_CRT_ALLOC_HOOK _CrtSetAllocHook(  
   _CRT_ALLOC_HOOK allocHook   
);  
```  
  
#### 매개 변수  
 `allocHook`  
 C 런타임 디버그 메모리 할당 프로세스에 연결한 새 클라이언트 정의 할당 함수  
  
## 반환 값  
 `allocHook` 가  `NULL` 일 경우, 이전에 정의 된 할당 후크 함수 또는  `NULL` 을 반환합니다.  
  
## 설명  
 `_CrtSetAllocHook`는 응용프로그램이 C 런타임 디버그 라이브러리 메모리 할당 프로세스에 자신의 할당 기능을 연결하도록 합니다.  그 결과, 메모리 블록을 할당하거나 재할당하거나 해제하는 디버그 할당 함수를 호출 할 때마다 응용 프로그램의 후크 함수에 대한 호출을 트리거합니다.  `_CrtSetAllocHook`는 나중에 분석하기 위해 할당 정보를 기록하고 할당 패턴을 검사하는 기능, 테스트 응용 프로그램 메모리 부족 상황을 처리 하는 방법을 쉬운 메소드와 함께 응용프로그램을 제공합니다.  [\_DEBUG](../../c-runtime-library/debug.md)가 정의되어 있지 않으면 `_CrtSetAllocHook` 에 대한 호출은 전처리 동안 제거됩니다.  
  
 `_CrtSetAllocHook`  함수는  `allocHook` 에 지정 된 새 클라이언트 정의 할당 함수를 설치하고  이전에 정의 된 후크 함수를 반환합니다.  다음 예제에서는 클라이언트 정의 할당 후크가 어떻게 프로토타입화 되어야하는지를 증명합니다.  
  
```  
int YourAllocHook( int allocType, void *userData, size_t size, int   
blockType, long requestNumber, const unsigned char *filename, int   
lineNumber);  
```  
  
 `allocType` 인수는 할당 후크 함수에 대한 호출을 발생시키는  `(_HOOK_ALLOC` ,  `_HOOK_REALLOC` , 및  `_HOOK_FREE` \) 할당 작업의 종류를 지정합니다.   트리거 할당 형식이  `_HOOK_FREE` 일 때,  `userData` 는 메모리 블록을 해제할 수 있는 사용자 데이터 섹션에 대한 포인터입니다.  그러나, 트리거 할당 형식이  `_HOOK_ALLOC`  또는  `_HOOK_REALLOC`  일 때, 메모리 블록 할당이 되지 않았기 때문에   `userData`  는  `NULL` 입니다..  
  
 `size`는 메모리 블록의 크기를 바이트 단위로 지정하고,  `blockType` 은 메모리 블록의 형식을 나타냅니다  `requestNumber` 는 메모리 블록의 할당 순서 개체 수이고 사용 가능한 경우   `filename`  및  `lineNumber` 는 트리거 할당 작업이 시작 된 위치로 소스 파일 이름과 줄 번호를 지정합니다.  
  
 후크 함수에서 처리를 한 후, 주 C 런타임 할당 프로세스에 계속 하는 방법을 알려주는 부울 값을 반환해야 합니다.  후크 함수가 후크 함수가 호출되지 않은 것처럼 주 할당 프로세스가 계속되기를 원할 때, 후크 함수는  `TRUE` 를 반환합니다.  따라서 원래 트리거 할당 작업이 실행될 수 있습니다.  이 구현에서는 후크 함수는 디버그 힙 상태 또는 현재 할당 작업을 방해하지 않고 나중에 분석하기 위해 할당 정보를 모으고 저장할 수 있습니다.  
  
 후크 함수가 기본 할당 프로세스가 트리거 할당 작업이 호출 및 실패되는 것처럼 지속되기를 원할 경우, 후크 함수는  `FALSE` 을 반환해야 합니다.  구현을 사용하여, 후크 함수는 다양한 메모리 조건을 시뮬레이션할 수 있고 힙 상태를 디버그함으로써 응용프로그램이 어떻게 각 상황을 컨트롤하는지 테스트 할 수 있습니다.  
  
 후크 함수를 깨끗이 만드려면  `NULL` 을  `_CrtSetAllocHook` 에 전달합니다.  
  
 `_CrtSetAllocHook` 가 어떻게 다른 메모리 관리 함수를 사용하는지 그리고 어떻게 클라이언트 정의 후크 함수를 직접 작성하는지에 대한 자세한 내용은[디버그 후크 함수 작성](../Topic/Debug%20Hook%20Function%20Writing.md)을 참조하십시오.  
  
> [!NOTE]
>  `_CrtSetAllocHook` 는 `/clr:pure`에서 지원되지 않습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_CrtSetAllocHook`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 의 유일한 디버그 버전입니다.  
  
## 예제  
 `_CrtSetAllocHook` 을 사용하는 방법에 대한 예제는  [crt\_dbg2](http://msdn.microsoft.com/ko-kr/21e1346a-6a17-4f57-b275-c76813089167)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [\_CrtGetAllocHook](../../c-runtime-library/reference/crtgetallochook.md)