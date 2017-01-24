---
title: "컴파일러 오류 C3063 | Microsoft Docs"
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
  - "C3063"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3063"
ms.assetid: 0ecf6f1f-e4a7-487a-9fd5-79d8ac470001
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3063
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

연산자 'operator': 모든 피연산자의 열거형 형식이 같아야 합니다.  
  
 열거자에 대한 연산자를 사용할 때는 두 피연산자의 열거형 형식이 동일해야 합니다.  자세한 내용은 [Using Operators and Enumerations](../../misc/operators-and-enumerations.md)를 참조하십시오.  
  
 다음 샘플에서는 C3063 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3063.cpp  
// compile with: /clr  
enum class E { a, b } e, mask;  
int main() {  
   if ( ( e & mask ) != 0 ) ;   // C3063 no operator!= (E, int)  
  
   if ( ( e & mask ) != E() )   // OK  
      ;  
}  
```