---
title: "setjmp | Microsoft Docs"
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
  - "setjmp"
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
  - "setjmp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "프로그램[C++], 상태 저장"
  - "현재 상태"
  - "setjmp 함수"
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# setjmp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프로그램의 현재 상태를 저장합니다.  
  
## 구문  
  
```  
int setjmp(  
   jmp_buf env   
);  
```  
  
#### 매개 변수  
 `env`  
 환경이 저장되어 있는 변수입니다.  
  
## 반환 값  
 스택 환경을 저장한 이후 0을 반환합니다.  `setjmp`이 `longjmp` 호출의 결과를 반환하면, `longjmp`의 `value` 인수를 반환합니다. 또는 `longjmp`의 `value` 인수가 0이면, `setjmp`는 1을 반환합니다.  반환되는 오류가 없습니다.  
  
## 설명  
 `setjmp` 함수는 `longjmp`를 사용하여 이후에 복원할 수 있는 스택 환경을 저장합니다.  `setjmp` 및 `longjmp`를 함께 사용하면 비로컬 `goto`를 실행할 수 있습니다.  setjmp와 longjmp는 표준 호출이나 반환 규칙을 사용하지 않고 전에 호출된 루틴에서 오류 처리 또는 복구 코드에 실행 제어를 전달하는 데 주로 사용됩니다.  
  
 `setjmp`의 호출은 현재 스택 환경을 `env`에 저장합니다.  `longjmp`에 대한 후속 호출은 저장된 환경을 복원하고 포인터에 컨트롤을 `setjmp` 호출에 따라 즉시 반환합니다.  루틴 수신 컨트롤에 액세스 할 수 있는 모든 변수의 값은 \(레지스터 변수를 제외하고\) `longjmp` 가 호출 될 때 있던 값을 포함합니다.  
  
 네이티브 코드에서 관리 코드로 이동하기 위해 `setjmp`를 사용할 수 없습니다.  
  
 **편지지** `setjmp` 및 `longjmp`는 C\+\+ 개체 의미 체계를 지원하지 않습니다.  C\+\+ 프로그램에서, C\+\+ 예외 처리 메커니즘을 사용합니다.  
  
 자세한 내용은 [Using setjmp and longjmp](../../cpp/using-setjmp-longjmp.md) 를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`setjmp`|\<setjmp.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 [\_fpreset](../../c-runtime-library/reference/fpreset.md) 의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [longjmp](../../c-runtime-library/reference/longjmp.md)   
 [\_setjmp3](../../c-runtime-library/setjmp3.md)