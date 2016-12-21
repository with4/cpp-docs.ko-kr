---
title: "_initterm, _initterm_e | Microsoft Docs"
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
  - "_initterm_e"
  - "_initterm"
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
  - "_initterm_e"
  - "initterm"
  - "_initterm"
  - "initterm_e"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "initterm 함수"
  - "initterm_e 함수"
  - "_initterm 함수"
  - "_initterm_e 함수"
ms.assetid: 85131efe-c747-429a-8897-bcdedb000172
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _initterm, _initterm_e
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

함수 포인터의 표를 실행하고 그들을 초기화하는 내부 방법입니다.  
  
 첫 번째 포인터는 테이블의 시작 위치이고 두 번째 포인터의 끝 위치입니다.  
  
## 구문  
  
```  
void __cdecl _initterm(  
   PVFV *,  
   PVFV *  
);  
  
int __cdecl _initterm_e(  
   PVFV *,  
   PVFV *  
);  
```  
  
## 반환 값  
 초기화를 실패하거나 오류가 발생하면 0이 아닌 값입니다. 오류가 발생하지 않으면 0입니다.  
  
## 설명  
 이러한 방법은 오직 C\+\+ 프로그램을 초기화 하는 동안에만 내부적으로 호출됩니다.  프로그램에서 이러한 방법을 호출하지 마십시오.  
  
 이러한 방법이 함수 입력 표를 실행했을 때, 그들은 `NULL` 입력을 생략하고 계속합니다.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)