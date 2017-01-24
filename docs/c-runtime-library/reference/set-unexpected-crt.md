---
title: "set_unexpected(CRT) | Microsoft Docs"
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
  - "set_unexpected"
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
  - "set_unexpected"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "예외 처리, 종료"
  - "set_unexpected 함수"
  - "예기치 않은 함수"
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# set_unexpected(CRT)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`unexpected`로 호출될 자체 종료 함수를 설치하세요.  
  
## 구문  
  
```  
unexpected_function set_unexpected(  
   unexpected_function unexpFunction   
);  
```  
  
#### 매개 변수  
 `unexpFunction`  
 `unexpected` 함수를 대체하기 위해 작성한 함수에 대해 포인터하세요.  
  
## 반환 값  
 `_set_unexpected`로 등록된 이전의 종료 함수를 가리키는 포인터를 반환하면 이전 함수는 이후에 복원될 수 있습니다.  만일 이전 함수가 설정되어지지 않았다면, 반환값은 기본 동작을 저장하기 위해 사용될 것입니다; 이 값은 NULL일 수 있습니다.  
  
## 설명  
 `set_unexpected` 함수는 `unexpected` 에 호출되는 함수로서 `unexpFunction` 를 설치합니다.  `unexpected`는 현재 c\+\+ 예외 처리 구현에서 사용 되지 않습니다.  `unexpected_function` 형식은 EH.H 에 `void`을 반환하는 사용자 정의 종료 함수인 `unexpFunction`에 대한 포인터로 정의되어 있습니다.  사용자 지정 `unexpFunction` 함수는 해당 호출자에게 반환하지 않아야 합니다.  
  
```  
typedef void ( *unexpected_function )( );  
```  
  
 기본적으로, `unexpected`는 `terminate`를 호출합니다.  `set_unexpected`를 사용자의 함수 이름과 매개변수로 호출하고 사용자의 종료 함수를 작성함으로써 이 기본동작을 변경할 수 있습니다.  `unexpected` 루틴은 `set_unexpected`에 대한 인수로 주어진 마지막 함수를 항상 호출합니다.  
  
 `set_terminate`을 호출하여 설치된 사용자 지정 종료 함수와 달리 `unexpFunction`내에서 예외가 throw될 수 있습니다.  
  
 다중 스레드 환경에서 unexpected 함수들은 각 스레드에 대해 개별적으로 유지됩니다.  각각의 새로운 스레드에는 unexpected 함수를 설치 해야 합니다.  따라서 각 스레드는 unexpected 처리를 담당합니다.  
  
 현재 Microsoft c \+ \+ 예외 처리 구현에서는 `unexpected`가 기본으로 `terminate`를 호출하고 예외 처리 런타임 라이브러리에 의해서는 호출 되지 않습니다.  `unexpected`를 `terminate`대신 호출하는 것에 대해 특별한 이점은 없습니다.  
  
 이것은 동적 링크된 DLL 또는 EXE에 대해 단일 `set_unexpected` 처리기 입니다. `set_unexpected` 를 호출하는 경우에도 사용자의 처리기는 다른 것으로 교체되거나 다른 DLL 또는 EXE 로 처리기 설정을 교체할 수도 있습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`set_unexpected`|\<eh.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [\_get\_unexpected](../../c-runtime-library/reference/get-unexpected.md)   
 [set\_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)