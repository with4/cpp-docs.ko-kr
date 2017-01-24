---
title: "unexpected(CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "unexpected"
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
  - "unexpected"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "예기치 않은 함수"
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# unexpected(CRT)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`terminate` 또는 `set_unexpected`를 사용하여 사용자가 지정한 함수를 호출하세요.  
  
## 구문  
  
```  
void unexpected( void );  
```  
  
## 설명  
 `unexpected` 루틴은 C\+\+ 예외 처리의 현재 구현과 함께 사용되지 않습니다.  `unexpected`는 `terminate`를 기본적으로 호출합니다.  사용자는 자신만의 종료 함수를 작성하고 `set_unexpected`를 사용자의 함수 이름과 매개변수로 호출함으로써 이 기본작동을 변경할 수 있습니다.  `unexpected` 루틴은 `set_unexpected`에 대한 인수로 주어진 마지막 함수를 항상 호출합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`unexpected`|\<eh.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Exception Class](https://msdn.microsoft.com/en-us/library/system.exception.aspx)  
  
## 참고 항목  
 [예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [\_set\_se\_translator](../../c-runtime-library/reference/set-se-translator.md)   
 [set\_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set\_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)