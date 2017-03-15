---
title: "_CIatan2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CIatan2"
apilocation: 
  - "msvcr80.dll"
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "CIatan2"
  - "_CIatan2"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CIatan2 내장 함수"
  - "CIatan2 내장 함수"
ms.assetid: 31f8cc78-b79f-4576-b73b-8add18e08680
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# _CIatan2
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*x* 및 *y* 의 *x* \/ *y* 의 아크탄젠트 계산은 스택의 맨 위에 있습니다.  
  
## 구문  
  
```  
void __cdecl _CIatan2();  
```  
  
## 설명  
 `atan2` 함수의 이 버전은 컴파일러가 이해할 수 있는 특별한 호출 규칙을 가집니다.  이는 복사본의 생성을 막고 레지스터의 할당에 도움을 주기 때문에 실행 속도를 높입니다.  
  
 결과 값이 스택의 맨 위에 푸시됩니다.  
  
## 요구 사항  
 **플랫폼:** x86  
  
## 참고 항목  
 [사전순 함수 참조](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)