---
title: "컴파일러 오류 C2766 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2766"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2766"
ms.assetid: 8032f4ca-6827-4f04-9c61-c44643c85cc4
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2766
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

명시적 특수화. 'template'은\(는\) 이미 정의되어 있습니다.  
  
 명시적 특수화는 중복하여 사용할 수 없습니다.  자세한 내용은 [Explicit Specialization of Function Templates](../../cpp/explicit-specialization-of-function-templates.md)를 참조하십시오.  
  
 다음 샘플에서는 C2766 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2766.cpp  
// compile with: /c  
template<class T>   
struct A {};  
  
template<>   
struct A<int> {};  
  
template<>   
struct A<int> {};   // C2766  
// try the following line instead  
// struct A<char> {};  
```