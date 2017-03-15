---
title: "컴파일러 경고 (수준 1) C4216 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4216"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4216"
ms.assetid: 211079dc-59d0-42a7-801c-2ddab21d7232
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4216
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장을 사용했습니다 : float long입니다.  
  
 기본 Microsoft 확장\(\/Ze\)에서는 **float long**을 **double**로 간주합니다.  그러나, ANSI 규격\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서는 다르게 간주합니다.  **double**을 사용하여 호환성을 유지하십시오.  다음 샘플에서는 C4216 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4216.cpp  
// compile with: /W1  
float long a;   // C4216  
  
// use the line below to resolve the warning  
// double a;  
  
int main() {  
}  
```