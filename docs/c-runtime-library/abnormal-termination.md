---
title: "_abnormal_termination | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_abnormal_termination"
apilocation: 
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_abnormal_termination"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_abnormal_termination"
ms.assetid: 952970a4-9586-4c3d-807a-db729448c91c
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# _abnormal_termination
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

시스템이 종료 처리기의 내부 목록을 실행 하는 중에 입력된 [try\-finally 문](../cpp/try-finally-statement.md) 의 `__finally` 블록인지 여부를 나타냅니다.  
  
## 구문  
  
```cpp  
int   _abnormal_termination(  
   );  
```  
  
## 반환 값  
 만일 시스템이 스택을 *해제* 한다면, `true` 입니다; 그렇지 않으면, `false`입니다.  
  
## 설명  
 이것은 해제 예외를 관리하기 위해 사용되는 내부 함수이고, 사용자 코드로부터 호출될 수 없습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|\_abnormal\_termination|excpt.h|  
  
## 참고 항목  
 [try\-finally 문](../cpp/try-finally-statement.md)