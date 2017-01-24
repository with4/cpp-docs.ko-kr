---
title: "컴파일러 오류 C2971 | Microsoft Docs"
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
  - "C2971"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2971"
ms.assetid: fdb5467b-9a41-41ef-ac20-2e9428d5a4fc
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2971
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : 템플릿 인수 'param' : 'arg' : 지역 변수를 비형식 인수로 사용할 수 없습니다.  
  
 지역 변수의 주소 또는 이름을 템플릿 인수로 사용할 수 없습니다.  
  
 다음 샘플에서는 C2971 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2971.cpp  
template <int *pi>   
class Y {};  
  
int global_var = 0;  
  
int main() {  
   int local_var = 0;  
   Y<&local_var> aY;   // C2971  
   // try the following line instead  
   // Y<&global_var> aY;  
}  
```