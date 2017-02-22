---
title: "컴파일러 오류 C2638 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2638"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2638"
ms.assetid: 9d4275e8-406d-455e-afee-3a37799230e0
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2638
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : \_\_based 한정자를 멤버에 대한 포인터로 사용할 수 없습니다.  
  
 `__based` 한정자는 멤버에 대한 포인터에 사용할 수 없습니다.  
  
 다음 샘플에서는 C2638 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2638.cpp  
void *a;  
  
class C {  
public:  
   int i;  
   int j;  
   int func();  
};  
int __based (a) C::* cpi = &C::i;  // C2638  
int (__based (a) C::* cpf)() = &C::func; // c2638  
```