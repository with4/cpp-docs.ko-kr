---
title: "컴파일러 오류 C2722 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2722"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2722"
ms.assetid: 4cc2c7fa-cb12-4bcf-9df1-6d627ef62973
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2722
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'::operator' : 다음 연산자 명령이 잘못되었습니다. 'operator operator'을\(를\) 사용하십시오.  
  
 `operator` 문에서 `::new` 또는 `::delete`를 다시 정의하고 있습니다.  `new`와 `delete`는 전역 연산자이므로 범위 결정 연산자\(`::`\)는 의미가 없습니다.  `::` 연산자를 제거하십시오.