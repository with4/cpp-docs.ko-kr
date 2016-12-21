---
title: "컴파일러 오류 C2679 | Microsoft Docs"
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
  - "C2679"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2679"
ms.assetid: 1a5f9d00-9190-4aa6-bc72-949f68ec136f
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2679
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이항 'operator' : 오른쪽 피연산자로 'type' 형식을 사용하는 연산자가 없거나 허용되는 변환이 없습니다.  
  
 연산자를 사용하려면 연산자를 지정된 형식에 대해 오버로드하거나 연산자에 정의된 형식으로 변환을 정의해야 합니다.  
  
 다음 샘플에서는 C2679 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2679.cpp  
class C {  
public:  
   C();   // no constructor with an int argument  
} c;  
  
class D {  
public:  
   D(int) {}  
   D(){}  
} d;  
  
int main() {  
   c = 10;   // C2679  
   d = 10;   // OK  
}  
```