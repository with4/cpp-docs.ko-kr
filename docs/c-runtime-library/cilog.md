---
title: "_CIlog | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CIlog"
apilocation: 
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcrt.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_CIlog"
  - "CIlog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CIlog 내장 함수"
  - "CIlog 내장 함수"
ms.assetid: 23503854-ddaa-4fe0-a4a3-7fbb3a43bdec
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# _CIlog
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

스택의 맨 위에 있는 값의 자연 로그를 계산합니다.  
  
## 구문  
  
```  
void __cdecl _CIlog();  
```  
  
## 설명  
 `log` 함수의 이 버전은 컴파일러가 이해할 수 있는 특별한 호출 규칙을 가집니다.  이는 복사본의 생성을 막고 레지스터의 할당에 도움을 주기 때문에 실행 속도를 높입니다.  
  
 결과 값이 스택의 맨 위에 푸시됩니다.  
  
## 요구 사항  
 **플랫폼:** x86  
  
## 참고 항목  
 [사전순 함수 참조](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [log, logf, log10, log10f](../c-runtime-library/reference/log-logf-log10-log10f.md)