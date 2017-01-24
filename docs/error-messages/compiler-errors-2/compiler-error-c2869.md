---
title: "컴파일러 오류 C2869 | Microsoft Docs"
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
  - "C2869"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2869"
ms.assetid: 6e30c001-47f3-4101-b9f1-cc542c9fffae
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2869
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name' : 이미 네임스페이스로 선언했습니다.  
  
 네임스페이스로 이미 사용된 이름은 다시 사용할 수 없습니다.  
  
 다음 샘플에서는 C2869 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2869.cpp  
// compile with: /c  
namespace A { int i; };  
  
class A {};   // C2869, A is already used  
```