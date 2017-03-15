---
title: "__uncaught_exception | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__uncaught_exception"
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
  - "__uncaught_exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__uncaught_exception"
ms.assetid: 4d9b75c6-c9c7-4876-b761-ea9ab1925e96
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# __uncaught_exception
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

하나 또는 이상의 예외가 발생되었지만 [try\-catch](../../cpp/try-throw-and-catch-statements-cpp.md)문의 해당하는 `catch` 블록으로 처리되지 않았음을 나타냅니다.  
  
## 구문  
  
```cpp  
bool __uncaught_exception(  
   );  
```  
  
## 반환 값  
 매칭되는 `catch` 블록이 초기화되었을 때 `try` 블록에서 예외가 발생한 경우에만 `true`입니다. 그렇지 않으면 `false`입니다.  
  
## 설명  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|\_\_uncaught\_exception|eh.h|  
  
## 참고 항목  
 [Try, Throw 및 Catch 문\(C\+\+\)](../../cpp/try-throw-and-catch-statements-cpp.md)