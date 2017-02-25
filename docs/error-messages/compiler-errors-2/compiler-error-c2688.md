---
title: "컴파일러 오류 C2688 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2688"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2688"
ms.assetid: 168c9e9d-8f65-4664-af86-db71d3e6ee46
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C2688
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'C2::fgrv': 다중 또는 가상 상속을 사용하는 공변 반환은 varargs 함수에 지원되지 않습니다.  
  
 함수에 가변 인수가 포함된 경우에는 Visual C\+\+에서 공변 반환 형식이 지원되지 않습니다.  
  
 이 오류를 해결하려면 가변 인수를 사용하지 않는 함수를 정의하거나 반환 값을 모든 가상 함수에 대해 동일하게 만드십시오.  
  
 다음 샘플에서는 C2688 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2688.cpp  
struct G1 {};  
struct G2 {};  
struct G3 : G1, G2 {};  
struct G4 {};  
struct G5 {};  
struct G6 : G4, G5 {};  
struct G7 : G3, G6 {};  
  
struct C1 {  
   virtual G4& fgrv(int,...);  
};  
  
struct C2 : C1 {  
   virtual G7& fgrv(int,...);   // C2688, does not return G4&  
};  
```