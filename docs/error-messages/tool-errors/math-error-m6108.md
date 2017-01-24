---
title: "수학 오류 M6108 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "M6108"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6108"
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 수학 오류 M6108
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

제곱근  
  
 제곱근 연산의 피연산자가 음수입니다.  
  
 프로그램은 종료 코드 136로 종료됩니다.  
  
> [!NOTE]
>  C 런타임 라이브러리의 `sqrt` 함수와 FORTRAN의 내장 함수인 **SQRT**는 이 오류를 생성하지 않습니다.  C `sqrt` 함수는 연산을 수행하기 전에 인수를 확인하여 피연산자가 음수이면 오류 값을 반환합니다.  FORTRAN **SQRT** 함수는 이 오류 대신에 DOMAIN 오류 [M6201](../../error-messages/tool-errors/math-error-m6201.md)을 생성합니다.