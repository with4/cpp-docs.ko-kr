---
title: "컴파일러 오류 C2635 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2635"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2635"
ms.assetid: 9deca2a8-2d61-42eb-9783-6578132ee3fb
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2635
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier1\*'을\(를\) 'identifier2\*'\(으\)로 변환할 수 없습니다. 가상 기본 클래스에서 변환하는 것으로 간주됩니다.  
  
 변환에는 `virtual` 기본 클래스에서 파생 클래스로의 캐스트가 필요하지만 이를 사용할 수 없습니다.  
  
 다음 샘플에서는 C2635 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2635.cpp  
class B {};  
class D : virtual public B {};  
class E : public B {};  
  
int main() {  
   B b;  
   D d;  
   E e;  
  
   D * pD = &d;  
   E * pE = &e;  
   pD = (D*)&b;   // C2635  
   pE = (E*)&b;   // OK  
}  
```