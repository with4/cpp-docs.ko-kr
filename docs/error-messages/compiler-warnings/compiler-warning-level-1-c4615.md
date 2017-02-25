---
title: "컴파일러 경고 (수준 1) C4615 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4615"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4615"
ms.assetid: 7b107c01-0da2-4e01-8b40-93813e30b94c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4615
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma warning : 알 수 없는 사용자 경고 형식입니다.  
  
 **pragma** [warning](../../preprocessor/warning.md)에 잘못된 경고 지정자를 사용했습니다.  이 오류를 해결하려면 올바른 경고 지정자를 사용하십시오.  
  
 다음 샘플에서는 C4615 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4615.cpp  
// compile with: /W1 /LD  
#pragma warning(enable : 4401)   // C4615, 'enable' not valid specifier  
  
// use the code below to resolve the error  
// #pragma warning(default : 4401)  
```