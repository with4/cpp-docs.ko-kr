---
title: "_get_terminate | Microsoft Docs"
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
  - "_get_terminate"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_terminate"
  - "_get_terminate"
  - "__get_terminate"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "__get_terminate 함수"
  - "_get_terminate 함수"
  - "get_terminate 함수"
ms.assetid: c8f168c4-0ad5-4832-a522-dd1ef383c208
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _get_terminate
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

종료 루틴이 `terminate` 으로 호출되어 반환합니다.  
  
## 구문  
  
```  
terminate_function _get_terminate( void );  
```  
  
## 반환 값  
 [set\_terminate](../../c-runtime-library/reference/set-terminate-crt.md) 로 등록된 함수에 대한 포인터를 반환합니다.  만일 함수가 설정되어지지 않았다면, 반환값은 기본 동작을 저장하기 위해 사용될 것입니다; 이 값은 NULL일 수 있습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_get_terminate`|\<eh.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [set\_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)