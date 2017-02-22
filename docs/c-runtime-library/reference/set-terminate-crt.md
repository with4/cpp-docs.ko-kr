---
title: "set_terminate(CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "set_terminate"
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
  - "set_terminate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "예외 처리, 종료"
  - "set_terminate 함수"
  - "terminate 함수"
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# set_terminate(CRT)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`terminate` 에게 호출되기 위해 종료 루틴을 설치합니다.  
  
## 구문  
  
```  
terminate_function set_terminate(  
   terminate_function termFunction  
);  
```  
  
#### 매개 변수  
 `termFunction`  
 작성한 종료 함수 대한 포인터입니다.  
  
## 반환 값  
 `set_terminate` 가 등록한 이전의 함수를 가르키는 포인터를 반환합니다. 그러므로 이전 함수는 이후에 복원될 수 있습니다.  만일 이전 함수가 설정되어지지 않았다면, 반환값은 기본 동작을 저장하기 위해 사용될 것입니다; 이 값은 NULL일 수 있습니다.  
  
## 설명  
 `set_terminate` 함수는 `terminate` 에 호출되는 함수로서 `termFunction` 를 설치합니다.  `set_terminate` 는 C\+\+ 예외 처리와 함께 사용되며 예외가 throw 되기 전에 프로그램에서 어떠한 포인터에서도 호출될 수 있습니다.  `terminate`는 `abort`를 기본적으로 호출합니다.  사용자는 자신만의 종료 함수를 작성하고 `set_terminate`를 사용자의 함수 이름과 매개변수로 호출함으로써 이 기본값을 변경할 수 있습니다.  `terminate` 루틴은 `set_terminate`에 대한 인수로 주어진 마지막 함수를 항상 호출합니다.  필요한 정리 작업이 끝난 후, `termFunction` 는 프로그램을 끝냅니다.  종료 되지 않는 경우\(호출자에게 반환 되는 경우\) `abort` 가 호출됩니다.  
  
 다중 스레드 환경에서 종료 기능은 각 스레드에 대해 개별적으로 유지됩니다  각 새 스레드에 종료 기능을 설치 해야 합니다.  따라서 각 스레드는 종료 처리를 가집니다.  
  
 `terminate_function` 형식은 EH.H 에 `void` 을 반환하는 사용자 정의 종료 함수`termFunction` 로 정의되어 있습니다.  사용자 지정 함수 `termFunction` 는 인수를 사용할 수 있고 해당 호출자에게 반환 해서는 안 됩니다.  그런 경우, `abort` 가 호출됩니다.  `termFunction` 내에서 예외는 throws 되지 않을 수도 있습니다.  
  
```  
typedef void ( *terminate_function )( );  
```  
  
> [!NOTE]
>  `set_terminate` 함수는 디버거 외부 에서만 작동 합니다.  
  
 이것은 동적 링크된 DLL 또는 EXE 에 대해 단일 `set_terminate` 처리기 입니다. `set_terminate` 를 호출하는 경우에도 처리기를 다른 것으로 교체 될수 있으며 또한 다른 DLL 또는 EXE 로 처리기 설정을 교체할 수도 있습니다.  
  
 이 함수는 **\/clr:pure** 에서는 지원되지 않습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`set_terminate`|\<eh.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 [terminate](../../c-runtime-library/reference/terminate-crt.md) 에 대한 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [\_get\_terminate](../../c-runtime-library/reference/get-terminate.md)   
 [set\_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)