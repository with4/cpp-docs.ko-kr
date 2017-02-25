---
title: "컴파일러 오류 C2645 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2645"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2645"
ms.assetid: 6609c2fa-c3b2-4a6b-8e8d-58fb52f67175
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2645
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

멤버에 대한 포인터의 정규화된 이름이 아닙니다. ':: \*'가 있습니다.  
  
 멤버에 대한 포인터 선언에서 클래스를 지정하지 않았습니다.  
  
 다음 샘플에서는 C2645 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2645.cpp  
class A {};  
int main() {  
   int B::* bp;   // C2645 B not defined  
   int A::* ap;   // OK  
}  
```