---
title: "_cexit, _c_exit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_c_exit"
  - "_cexit"
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
  - "_cexit"
  - "c_exit"
  - "_c_exit"
  - "cexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_c_exit 함수"
  - "_cexit 함수"
  - "c_exit 함수"
  - "cexit 함수"
  - "프로세스 중간의 정리 작업"
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _cexit, _c_exit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

정리 작업을 수행하고 프로세스를 종료하지 않고 반환 합니다.  
  
## 구문  
  
```  
void _cexit( void );  
void _c_exit( void );  
```  
  
## 설명  
 이 `_cexit` 함수는 후입선출\(LIFO\) 순으로, 호출합니다, 이 함수는 `atexit` 와 `_onexit` 으로 등록됬습니다.  그런 다음 `_cexit` 는 모든 I\/O 버퍼를 플러시하고 반환 하기 전에 모든 열린 스트림을 닫습니다.  `_c_exit` 는 `_exit` 와 동일하지만 `atexit` 또는 `_onexit` 또는 스트림 버퍼를 플러시하는 프로세싱을 제외한 호출 프로세스를 반환합니다.   `exit`, `_exit`, `_cexit`, 및 `_c_exit` 의 동작은 다음 표에 나와있습니다.  
  
|Function|동작|  
|--------------|--------|  
|`exit`|전체 C 라이브러리 종료 절차를 수행하고 프로세스를 종료하고 제공된 상태 코드와 함께 종료합니다.|  
|`_exit`|빠르게 C 라이브러리 종료 절차를 수행하고 프로세스를 종료하면 제공된 상태 코드와 함께 종료합니다.|  
|`_cexit`|전체 C 라이브러리 종료 절차를 수행하면 호출자에게 반환되지만 프로세스는 종료되지 않습니다.|  
|`_c_exit`|빠르게 C 라이브러리 종료 절차를 수행하고 호출자에게 반환되지만 프로세스는 종료되지 않습니다.|  
  
 `_cexit` 또는 `_c_exit` 함수를 호출할 때, 호출되는 시점에서 존재하는 자동 또는 임시 개체에 대한 소멸자는 호출되지 않습니다.  자동 개체는 static으로 선언되지 않은 개체의 위치의 함수에서 정의됩니다.  임시 개체는 컴파일러에 의해 생성되는 개체입니다.  `_cexit` 또는 `_c_exit`를 호출하기 전에 자동 개체를 소멸시키려면, 다음과 같이 명시적으로 개체에 대한 소멸자를 호출해야 합니다:  
  
```  
myObject.myClass::~myClass( );  
```  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_cexit`|\<process.h\>|  
|`_c_exit`|\<process.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Diagnostics::Process::CloseMainWindow](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)  
  
## 참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [\_exec, \_wexec 함수](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [\_spawn, \_wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)