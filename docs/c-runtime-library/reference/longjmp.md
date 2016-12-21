---
title: "longjmp | Microsoft Docs"
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
  - "longjmp"
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
  - "longjmp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "longjmp 함수"
  - "스택 환경 및 실행 로캘 복원"
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# longjmp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스택 환경 및 실행 로캘 복원  
  
## 구문  
  
```  
  
      void longjmp(  
   jmp_buf env,  
   int value   
);  
```  
  
#### 매개 변수  
 `env`  
 환경이 저장되어 있는 변수입니다.  
  
 *value*  
 `setjmp` 호출에 대해 반환 되는 값입니다.  
  
## 설명  
 `longjmp` 함수는 스택 환경과 이전에 `setjmp` 에 의해 `env` 에 저장된 실행 로캘을 복원합니다.  `setjmp` 및 `longjmp` 은 로캘이 아닌 `goto` 을 실행하는 방법을 제공합니다. 일반적으로 표준 호출이나 반환 규식을 사용하지 않고 전에 호출된 루틴에서 오류 핸들링이나 복원 코드에 실행을 전달하는데 사용 됩니다.  
  
 `setjmp` 에 대한 호출은 현재 스택 환경을 `env` 에 저장합니다.  `longjmp` 에 대한 후속 호출은 저장된 환경을 복원하고 포인터에 컨트롤을 `setjmp` 호출에 따라 즉시 반환합니다.  실행은 *value* 가 `setjmp` 호출에 의해 반환된 것이라고 가정합니다.  루틴 수신 컨트롤에 액세스 할 수 있는 모든 변수의 값은 \(레지스터 변수를 제외하고\) `longjmp` 가 호출 될 때 있던 값을 포함합니다.  레지스터 변수 값을 예측할 수 없습니다.  `setjmp` 가 반환한 값은 0이 아니어야 합니다.  *value* 값이 0으로 전달 되는 경우, 값 1은 실제 반환에 대체 됩니다.  
  
 `setjmp` 을 호출하는 함수가 반환하기 전에 `longjmp` 을 호출하십시오. 그렇지 않으면 결과는 예측할 수 없습니다.  
  
 `longjmp` 을 사용 할때 아래의 사항을 준수하십시오.  
  
-   레지스터 변수 값이 그대로 유지 된다고 가정 하지 마십시오.  루틴 호출 `setjmp` 에서 레지스터 변수의 값은 `longjmp` 가 실행된 후에는 적절한 값으로 복원되지 않을 수 있습니다.  
  
-   수동 소수점 예외가 인터럽트를 발생시키지 않는 한 인터럽트 처리 루틴의 컨트롤을 전달하기 위해 `longjmp` 를 사용하지 마십시오.  이 경우, 먼저 `_fpreset` 를 호출하여 부동 소수점 연산 패키지를 다시 초기화 하는 경우 프로그램은 `longjmp` 를 통해 인터럽트 핸들러에서 반환될 수 있습니다.  
  
     **참고** C 프로그램에서 `setjmp` 및 `longjmp` 를 사용할 때 주의 하십시오.  이러한 함수는 C \+ \+ 의미 객체를 지원하지 않기 때문에, C \+ \+ 예외 처리 메커니즘을 사용하는 것이 더 안전합니다.  
  
 자세한 내용은 [Using setjmp and longjmp](../../cpp/using-setjmp-longjmp.md) 를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`longjmp`|\<setjmp.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
 [\_fpreset](../../c-runtime-library/reference/fpreset.md) 의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [setjmp](../../c-runtime-library/reference/setjmp.md)