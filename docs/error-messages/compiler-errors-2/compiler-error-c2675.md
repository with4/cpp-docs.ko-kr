---
title: "컴파일러 오류 C2675 | Microsoft Docs"
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
  - "C2675"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2675"
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2675
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

단항 'operator' : 'type'이\(가\) 이 연산자를 정의하지 않거나 미리 정의된 연산자에 허용되는 형식으로의 변환을 정의하지 않습니다.  
  
 C2675는 단항 연산자를 사용할 때 형식에서 연산자를 정의하지 않거나 미리 정의된 연산자에 허용되는 형식으로의 변환을 정의하지 않은 경우에도 발생할 수 있습니다.  연산자를 사용하려면 연산자를 지정된 형식에 대해 오버로드하거나 연산자에 정의된 형식으로 변환을 정의해야 합니다.  
  
## 예제  
 다음 샘플에서는 C2675 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2675.cpp  
struct C {   
   C(){}  
} c;  
  
struct D {   
   D(){}  
   void operator-(){}  
} d;  
  
int main() {  
   -c;   // C2675  
   -d;   // OK  
}  
```