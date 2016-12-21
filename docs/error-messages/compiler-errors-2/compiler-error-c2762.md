---
title: "컴파일러 오류 C2762 | Microsoft Docs"
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
  - "C2762"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2762"
ms.assetid: 8b81a801-fd48-40a1-8bee-0748795b12e4
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2762
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : 'argument'의 템플릿 인수로 사용한 식이 잘못되었습니다.  
  
 [\/Za](../../build/reference/za-ze-disable-language-extensions.md)를 사용할 경우 컴파일러는 정수 계열을 포인터로 변환하지 않습니다.  
  
 다음 샘플에서는 C2762 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2762.cpp  
// compile with: /Za  
template<typename T, T *pT>  
class X2 {};  
  
void f2() {  
   X2<int, 0> x21;   // C2762  
   // try the following line instead  
   // X2<int, static_cast<int *>(0)> x22;  
}  
```