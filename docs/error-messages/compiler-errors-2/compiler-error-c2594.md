---
title: "컴파일러 오류 C2594 | Microsoft Docs"
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
  - "C2594"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2594"
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2594
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : 'type1'에서 'type2'\(으\)로의 변환이 모호합니다.  
  
 *type1*에서 *type2*로의 변환이 다른 변환보다 직접적이지 않습니다.  *type1*에서 *type2*로의 변환에 사용할 수 있는 해결 방법으로는 두 가지가 있습니다.  첫 번째 옵션은 *type1*에서 *type2*로의 직접 변환을 정의하는 것이고, 두 번째 옵션은 *type1*에서 *type2*로의 변환 순서를 지정하는 것입니다.  
  
 다음 샘플에서는 C2594 오류가 발생하는 경우를 보여 줍니다.  이 오류의 권장 해결 방법은 다음과 같이 변환 순서를 지정하는 것입니다.  
  
```  
// C2594.cpp  
// compile with: /c  
struct A{};  
struct I1 : A {};  
struct I2 : A {};  
struct D : I1, I2 {};  
  
A *f (D *p) {  
   return (A*) (p);    // C2594  
  
// try the following line instead  
// return static_cast<A *>(static_cast<I1 *>(p));  
}  
```