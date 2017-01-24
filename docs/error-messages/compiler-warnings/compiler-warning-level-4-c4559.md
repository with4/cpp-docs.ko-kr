---
title: "컴파일러 경고 (수준 4) C4559 | Microsoft Docs"
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
  - "C4559"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4559"
ms.assetid: ed542f60-454d-45cb-85da-987ede61b1ab
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4559
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 재정의: 함수에 \_\_declspec\(modifier\)가 추가됩니다.  
  
 함수를 다시 정의하거나 다시 선언했습니다. 두 번째 정의 또는 선언에서 \_\_**declspec** 한정자\(***modifier***\)를 추가했습니다.  이 경고는 정보를 제공하기 위한 것입니다.  이 경고를 해결하려면 정의 중 하나를 삭제해야 합니다.  
  
 다음 샘플에서는 C4559 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4559.cpp  
// compile with: /W4 /LD  
void f();  
__declspec(noalias) void f();   // C4559  
```