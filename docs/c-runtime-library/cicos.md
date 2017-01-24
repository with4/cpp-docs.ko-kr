---
title: "_CIcos | Microsoft Docs"
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
  - "_CIcos"
apilocation: 
  - "msvcr90.dll"
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "CIcos"
  - "_CIcos"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CIcos 내장 함수"
  - "CIcos 내장 함수"
ms.assetid: 6fc203fb-66f3-4ead-9784-f85833c26f1b
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CIcos
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

스택의 맨 위에 있는 값의 코사인을 계산합니다.  
  
## 구문  
  
```  
void __cdecl _CIcos();  
```  
  
## 설명  
 `cos` 함수의 이 버전은 컴파일러가 이해할 수 있는 특별한 호출 규칙을 가집니다.  이는 복사본의 생성을 막고 레지스터의 할당에 도움을 주기 때문에 실행 속도를 높입니다.  
  
 결과 값이 스택의 맨 위에 푸시됩니다.  
  
## 요구 사항  
 **플랫폼:** x86  
  
## 참고 항목  
 [사전순 함수 참조](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)