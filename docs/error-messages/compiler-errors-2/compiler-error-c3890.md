---
title: "컴파일러 오류 C3890 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3890"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3890"
ms.assetid: 2f22c2fd-c14e-45e1-b936-b739ffc0b135
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C3890
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : 리터럴 데이터 멤버의 주소를 가져올 수 없습니다.  
  
 리터럴 데이터 멤버가 가비지 수집된 힙에 있습니다.  가비지 수집된 힙의 개체은 옮길 수 없으므로 주소를 가져와도 아무런 의미가 없습니다.  
  
 다음 샘플에서는 C3890 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3890.cpp  
// compile with: /clr  
ref struct Y1 {  
   literal int staticConst = 9;  
};  
  
int main() {  
   int p = &Y1::staticConst;   // C3890  
   int p2 = Y1::staticConst;   // OK  
}  
```