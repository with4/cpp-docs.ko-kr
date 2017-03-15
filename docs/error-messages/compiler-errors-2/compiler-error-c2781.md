---
title: "컴파일러 오류 C2781 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2781"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2781"
ms.assetid: f29b9963-f55b-427c-8db6-50f37713df5a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2781
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'declaration' : 인수가 적어도 value1개는 있어야 하는데 value2개를 사용했습니다.  
  
 변수 매개 변수 목록을 사용하는 함수 템플릿에 인수가 너무 적습니다.  
  
 다음 샘플에서는 C2781 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2781.cpp  
template<typename T>  
void f(T, T, ...){}  
  
int main() {  
   f(1);   // C2781  
  
   // try the following line instead  
   f(1,1);  
}  
```