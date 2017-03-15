---
title: "_seh_filter_dll, _seh_filter_exe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_XcptFilter"
  - "_seh_filter_dll"
  - "_seh_filter_exe"
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
  - "XcptFilter"
  - "_XcptFilter"
  - "_seh_filter_dll"
  - "_seh_filter_exe"
  - "corecrt_startup/_seh_filter_exe"
  - "corecrt_startup/_seh_filter_dll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "XcptFilter 함수"
  - "_XcptFilter 함수"
  - "_seh_filter_dll 함수"
  - "_seh_filter_exe 함수"
ms.assetid: 747e5963-3a12-4bf5-b5c4-d4c1b6068e15
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _seh_filter_dll, _seh_filter_exe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

예외 및 수행할 관련 작업을 식별합니다.  
  
## 구문  
  
```  
int __cdecl _seh_filter_dll(  
   unsigned long _ExceptionNum,  
   struct _EXCEPTION_POINTERS* _ExceptionPtr  
);  
int __cdecl _seh_filter_exe(  
   unsigned long _ExceptionNum,  
   struct _EXCEPTION_POINTERS* _ExceptionPtr  
);  
```  
  
#### 매개 변수  
 \[in\] `_ExceptionNum`  
 예외의 식별자입니다.  
  
 \[in\] `_ExceptionPtr`  
 예외 정보에 대한 포인터입니다.  
  
## 반환 값  
 예외 처리의 결과를 기반으로 수행할 작업을 나타내는 정수입니다.  
  
## 설명  
 이러한 메서드는 [try\-except 문](../../cpp/try-except-statement.md)의 예외 필터 식으로 호출합니다. 메서드는 다음과 같이 상수 내부 테이블을 참조하여 예외를 식별하고 적절한 작업을 결정합니다. 예외 번호는 winnt.h에 정의되어 있고 신호 번호는 signal.h에 정의되어 있습니다.  
  
|예외 번호\(부호 없는 long\)|신호 번호|  
|-------------------------|-----------|  
|STATUS\_ACCESS\_VIOLATION|SIGSEGV|  
|STATUS\_ILLEGAL\_INSTRUCTION|SIGILL|  
|STATUS\_PRIVILEGED\_INSTRUCTION|SIGILL|  
|STATUS\_FLOAT\_DENORMAL\_OPERAND|SIGFPE|  
|STATUS\_FLOAT\_DIVIDE\_BY\_ZERO|SIGFPE|  
|STATUS\_FLOAT\_INEXACT\_RESULT|SIGFPE|  
|STATUS\_FLOAT\_INVALID\_OPERATION|SIGFPE|  
|STATUS\_FLOAT\_OVERFLOW|SIGFPE|  
|STATUS\_FLOAT\_STACK\_CHECK|SIGFPE|  
|STATUS\_FLOAT\_UNDERFLOW|SIGFPE|  
  
## 요구 사항  
 **헤더:** corecrt\_startup.h  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)