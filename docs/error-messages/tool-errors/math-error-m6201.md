---
title: "수학 오류 M6201 | Microsoft Docs"
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
  - "M6201"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6201"
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 수학 오류 M6201
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : \_DOMAIN 오류  
  
 지정한 함수에 대한 인수는 이 함수의 유효한 입력 값의 도메인 밖에 있습니다.  
  
## 예제  
  
```  
result = sqrt(-1.0)   // C statement  
result = SQRT(-1.0)   !  FORTRAN statement  
```  
  
 이 오류는 함수 이름, 해당 인수 및 오류 유형을 가진 `_matherr` 함수를 호출합니다.  특정 런타임 부동 소수점의 수학 오류 처리를 사용자 지정하려면 `_matherr` 함수를 다시 씁니다.