---
title: "fwide | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fwide"
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
  - "fwide"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fwide 함수"
ms.assetid: a4641f5b-d74f-4946-95d5-53a64610d28d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# fwide
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구현되지 않았습니다.  
  
## 구문  
  
```  
int fwide(  
   FILE *stream,  
   int mode;  
);  
```  
  
#### 매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다\(무시됩니다\).  
  
 `mode`  
 스트림의 새 너비: 와이드 문자에 대한 양수, 바이트에 대한 음수, 0은 변경되지 않습니다. \(이 값은 무시됩니다.\)  
  
## 반환 값  
 이 함수는 현재 단지 `mode` 을 반환합니다.  
  
## 설명  
 이 함수의 현재 버전은 표준에 맞지 않습니다.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`fwide`|\<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 [](../../c-runtime-library/compatibility.md "Compatibility")을 참조하십시오.