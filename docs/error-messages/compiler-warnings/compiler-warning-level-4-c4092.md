---
title: "컴파일러 경고 (수준 4) C4092 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4092"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4092"
ms.assetid: 396ae826-a892-4327-bd66-f4762376d72b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 4) C4092
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

sizeof가 'unsigned long'을 반환합니다.  
  
 `sizeof` 연산자의 피연산자가 너무 크기 때문에 `sizeof`가 부호 없는 **long**을 반환했습니다.  이 경고는 Microsoft 확장\([\/Ze](../../build/reference/za-ze-disable-language-extensions.md)\)에서 발생합니다.  ANSI 규격\(\/Za\)에서는 결과가 잘립니다.