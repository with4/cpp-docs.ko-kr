---
title: "컴파일러 오류 C3874 | Microsoft Docs"
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
  - "C3874"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3874"
ms.assetid: fd55fc05-69a7-4237-b3b7-dca1d5400b4f
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3874
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function'의 반환 형식이 'int'이어야 하는데 'type'입니다.  
  
 컴파일러에 필요한 반환 형식이 함수에 없습니다.  
  
 다음 샘플에서는 C3874 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3874b.cpp  
double main()  
{   // C3874  
}  
```