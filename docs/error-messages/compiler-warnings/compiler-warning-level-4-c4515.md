---
title: "컴파일러 경고 (수준 4) C4515 | Microsoft Docs"
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
  - "C4515"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4515"
ms.assetid: 167b5177-3f89-418b-b6c8-7de634f6b28f
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4515
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'namespace' : 네임스페이스가 자신을 사용합니다.  
  
 네임스페이스를 재귀적으로 사용했습니다.  
  
 다음 샘플에서는 C4515 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4515.cpp  
// compile with: /W4  
namespace A  
{  
   using namespace A; // C4515  
}  
  
int main()  
{  
}  
```