---
title: "컴파일러 오류 C2755 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2755"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2755"
ms.assetid: 8ee4eeb6-4757-4efe-9100-38ff4a96f1de
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2755
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'param' : 부분 특수화의 비형식 매개 변수는 단순 식별자여야 합니다.  
  
 비형식 매개 변수는 컴파일러가 컴파일 타임에 단일 식별자나 상수 값으로 확인할 수 있는 단순 식별자여야 합니다.  
  
 다음 샘플에서는 C2755 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2755.cpp  
template<int I, int J>  
struct A {};  
  
template<int I>   
struct A<I,I*5> {};   // C2755  
// try the following line instead  
// struct A<I,5> {};  
```