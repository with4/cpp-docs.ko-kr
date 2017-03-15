---
title: "__setusermatherr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__setusermatherr"
apilocation: 
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__setusermatherr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__setusermatherr"
ms.assetid: f306818d-381a-4d68-8739-71b92bacb5ea
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# __setusermatherr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대신 수학 오류를 처리 하는 사용자가 제공한 지정된 [\_matherr](../c-runtime-library/reference/matherr.md) 루틴입니다.  
  
## 구문  
  
```cpp  
void __setusermatherr(  
   _HANDLE_MATH_ERROR pf   
   )  
  
```  
  
#### 매개 변수  
 `pf`  
 구현에 대한 포인터 `_matherr` 는 사용자가 제공 합니다.  
  
 형식인 `pf` 매개변수는 `typedef int (__cdecl * _HANDLE_MATH_ERROR)(struct _exception *)` 로 선언됬습니다.  
  
## 설명  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|\_\_setusermatherr|matherr.c|