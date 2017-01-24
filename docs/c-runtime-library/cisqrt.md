---
title: "_CIsqrt | Microsoft Docs"
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
  - "_CIsqrt"
apilocation: 
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_CIsqrt"
  - "CIsqrt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CIsqrt 내장 함수"
  - "_CIsqrt 내장 함수"
ms.assetid: 663548ea-398c-48ee-8397-a787c6ebb937
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CIsqrt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

스택의 맨 위에 있는 값의 제곱근을 계산합니다.  
  
## 구문  
  
```  
void __cdecl _CIsqrt();  
```  
  
## 설명  
 `sqrt` 함수의 이 버전은 컴파일러가 이해할 수 있는 특별한 호출 규칙을 가집니다.  이는 복사본의 생성을 막고 레지스터의 할당에 도움을 주기 때문에 실행 속도를 높입니다.  
  
 결과 값이 스택의 맨 위에 푸시됩니다.  
  
## 요구 사항  
 **플랫폼:** x86  
  
## 참고 항목  
 [사전순 함수 참조](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [sqrt, sqrtf, sqrtl](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)