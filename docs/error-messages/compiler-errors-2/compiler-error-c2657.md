---
title: "컴파일러 오류 C2657 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2657"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2657"
ms.assetid: f7cf29a9-684a-4605-9469-ecfee9ba4b03
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2657
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문의 시작에 'class::\*'가 있습니다. 형식을 지정했어야 합니다.  
  
 줄이 pointer\-to\-member 식별자로 시작되었습니다.  
  
 이 오류는 멤버에 대한 포인터의 선언에 형식 지정자가 누락된 경우에 발생할 수 있습니다.  
  
 다음 샘플에서는 C2657 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2657.cpp  
class C {};  
int main() {  
   C::* pmc1;        // C2657  
   int C::* pmc2;   // OK  
}  
```