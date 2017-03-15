---
title: "컴파일러 오류 C3697 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3697"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3697"
ms.assetid: 2d3f63c4-b7f8-421d-a7a5-2bf17fd054f9
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3697
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'qualifier' : '^'에 이 한정자를 사용할 수 없습니다.  
  
 한정자에 적용한 추적 핸들\(^\)이 해당 한정자에 사용할 수 없는 핸들입니다.  
  
 다음 샘플에서는 C3697 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3697.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String ^__restrict s;   // C3697  
   String ^ s2;   // OK  
}  
```