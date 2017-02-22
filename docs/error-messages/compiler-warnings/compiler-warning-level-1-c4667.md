---
title: "컴파일러 경고 (수준 1) C4667 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4667"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4667"
ms.assetid: 5d2b7fe0-4f0e-4cd6-b432-ca02c3d194ab
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 1) C4667
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 강제 인스턴스화와 일치하도록 정의된 함수 템플릿이 없습니다.  
  
 선언하지 않은 함수 템플릿은 인스턴스화할 수 없습니다.  
  
 다음 샘플에서는 C4667이 발생합니다.  
  
```  
// C4667a.cpp  
// compile with: /LD /W1  
template  
void max(const int &, const int &); // C4667 expected  
```  
  
 이 경고가 발생하지 않도록 하려면 먼저 다음과 같이 함수 템플릿을 선언하십시오.  
  
```  
// C4667b.cpp  
// compile with: /LD  
// Declare the function template  
template<typename T>  
const T &max(const T &a, const T &b) {  
   return (a > b) ? a : b;  
}  
// Then forcibly instantiate it with a desired type ... i.e. 'int'  
//  
template  
const int &max(const int &, const int &);  
```