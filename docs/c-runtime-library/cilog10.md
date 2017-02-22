---
title: "_CIlog10 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CIlog10"
apilocation: 
  - "msvcr100.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "CIlog10"
  - "_CIlog10"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CIlog10 내장 함수"
  - "CIlog10 내장 함수"
ms.assetid: 05d7fcaa-3cff-4cc5-8d44-015e7cacba24
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# _CIlog10
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

스택의 맨 위에 있는 값에 대해 `log10` 작업을 수행합니다.  
  
## 구문  
  
```  
void __cdecl _CIlog10();  
```  
  
## 설명  
 `log10` 함수의 이 버전은 컴파일러가 이해할 수 있는 특별한 호출 규칙을 가집니다.  복사본 생성 되지 못하기 때문에 함수는 실행 속도를 높이고 레지스터를 할당 하는 데 도움을 줍니다.  
  
 결과 값이 스택의 맨 위에 푸시됩니다.  
  
## 요구 사항  
 **플랫폼:** x86  
  
## 참고 항목  
 [사전순 함수 참조](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [log, logf, log10, log10f](../c-runtime-library/reference/log-logf-log10-log10f.md)