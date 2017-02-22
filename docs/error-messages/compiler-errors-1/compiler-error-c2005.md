---
title: "컴파일러 오류 C2005 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2005"
ms.assetid: 090530ed-e0ec-4358-833a-ca24260e7ffe
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#line에 줄 번호가 있어야 하는데 'token'이\(가\) 있습니다.  
  
 `#line` 지시문 다음에 줄 번호가 와야 합니다.  
  
 다음 샘플에서는 C2005 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2005.cpp  
int main() {  
   int i = 0;  
   #line i   // C2005  
}  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2005b.cpp  
int main() {  
   int i = 0;  
   #line 0  
}  
```