---
title: "컴파일러 경고 (수준 3) C4390 | Microsoft Docs"
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
  - "C4390"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4390"
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 3) C4390
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

';' : 제어된 빈 문이 있습니다. 이 문이 필요합니까?  
  
 명령이 없는 제어문 뒤에 세미콜론이 있습니다.  
  
 매크로로 인해 C4390이 발생한 경우 [warning](../../preprocessor/warning.md) pragma를 사용하여 매크로를 포함하고 있는 모듈에서 C4390을 사용하지 않도록 해야 합니다.  
  
 다음 샘플에서는 C4390 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4390.cpp  
// compile with: /W3  
int main() {  
   int i = 0;  
   if (i);   // C4390  
      i++;  
}  
```