---
title: "컴파일러 오류 C2014 | Microsoft Docs"
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
  - "C2014"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2014"
ms.assetid: 231d8e9c-48c0-4027-99a3-245d186275ec
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2014
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

전처리기 명령은 공백 아닌 문자로 시작해야 합니다.  
  
 줄의 첫 문자는 전처리기 지시문의 `#` 부호로 시작해야 하며 공백이면 안 됩니다.  
  
 다음 샘플에서는 C2014 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2014.cpp  
int k; #include <stdio.h>   // C2014  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2014b.cpp  
// compile with: /c  
int k;   
#include <stdio.h>  
```