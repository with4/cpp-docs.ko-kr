---
title: "컴파일러 오류 C2877 | Microsoft Docs"
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
  - "C2877"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2877"
ms.assetid: 0b54837e-fcae-4d90-9658-623250435e24
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2877
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol'은\(는\) 'class'에서 액세스할 수 없습니다.  
  
 파생 클래스는 기본 클래스에서 파생된 모든 멤버에 액세스할 수 있어야 합니다.  
  
 다음 샘플에서는 C2877 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2877.cpp  
// compile with: /c  
class A {  
private:  
   int a;  
};  
  
class B : public A {  
   using A::a;   // C2877  
};  
```