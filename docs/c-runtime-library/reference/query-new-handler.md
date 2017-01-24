---
title: "_query_new_handler | Microsoft Docs"
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
  - "_query_new_handler"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_query_new_handler"
  - "query_new_handler"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_query_new_handler 함수"
  - "오류 처리"
  - "처리기 루틴"
  - "query_new_handler 함수"
ms.assetid: 9a84b5c3-fe33-4c01-83a0-be87dc3ec518
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _query_new_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 새 처리기 루틴의 주소를 반환합니다.  
  
## 구문  
  
```  
  
      _PNH _query_new_handler(  
   void   
);  
```  
  
## 반환 값  
 `_set_new_handler` 로 설정함으로써 현재 새 처리기 루틴의 주소를 반환합니다.  
  
## 설명  
 C\+\+ `_query_new_handler` 함수는 [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md) 함수로 설정된 현재 예외 처리 함수의 주소를 반환합니다.  `_set_new_handler` 는 만일 **new** 연산자가 메모리 할당에 실패하는 경우 제어를 얻도록 지정된 예외 처리 함수를 사용합니다.  보다 자세한 내용은, [new 연산자](../../misc/operator-new-function.md) *C\+\+ 언어 참조* 에서 [delete 연산자](../../misc/operator-delete-function.md) 함수들을 참조하세요.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_query_new_handler`|\<new.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)