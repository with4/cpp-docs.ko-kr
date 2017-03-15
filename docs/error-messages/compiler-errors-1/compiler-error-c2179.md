---
title: "컴파일러 오류 C2179 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2179"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2179"
ms.assetid: f929bfc6-3964-4e54-87d6-7529b9b6c0b9
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2179
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 특성 인수는 형식 매개 변수를 사용할 수 없습니다.  
  
 제네릭 형식 매개 변수는 런타임에 확인됩니다.  그러나 특성 매개 변수는 컴파일할 때 확인해야 합니다.  따라서 제네릭 형식 매개 변수를 특성에 대한 인수로 사용할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C2179 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2179.cpp  
// compile with: /clr  
using namespace System;  
  
public ref struct Attr : Attribute {  
   Attr(Type ^ a) {  
      x = a;  
   }  
  
   Type ^ x;  
};  
  
ref struct G {};  
  
generic<typename T>   
public ref class Z {   
public:  
   Type ^ d;  
   [Attr(T::typeid)]   // C2179  
   // try the following line instead  
   // [Attr(G::typeid)]  
   T t;  
};  
```