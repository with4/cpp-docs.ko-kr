---
title: "컴파일러 오류 C3858 | Microsoft Docs"
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
  - "C3858"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3858"
ms.assetid: 46e178d5-a55f-4ac6-a9dc-561fbcba5c1f
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3858
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 현재 범위에서 다시 선언할 수 없습니다.  
  
 해당 형식은 같은 범위에서 두 번 선언할 수 없습니다.  
  
 다음 샘플에서는 C3858 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3858.cpp  
// compile with: /LD  
template <class T>  
struct Outer  
{  
   struct Inner;  
};  
  
template <class T>  
struct Outer<T>::Inner;   // C3858  
// try the following line instead  
// struct Outer<T>::Inner{};  
```