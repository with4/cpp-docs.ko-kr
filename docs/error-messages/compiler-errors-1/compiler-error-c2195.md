---
title: "컴파일러 오류 C2195 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2195"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2195"
ms.assetid: 9f9f035c-9c51-4173-a8ea-c6f907fc5c63
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2195
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 데이터 세그먼트입니다.  
  
 `code_seg` pragma가 `data_seg` pragma에서 사용되는 세그먼트 이름을 사용합니다.  
  
 다음 샘플에서는 C2195 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2195.cpp  
#pragma data_seg("MYDATA")  
#pragma code_seg("MYDATA")   // C2195  
#pragma code_seg("MYDATA2")   // OK  
```