---
title: "컴파일러 오류 C2803 | Microsoft Docs"
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
  - "C2803"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2803"
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2803
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator operator'에는 클래스 형식의 형식 매개 변수가 적어도 하나는 있어야 합니다.  
  
 오버로드된 연산자에 클래스 형식의 매개 변수가 부족합니다.  
  
 포인터가 아닌 참조를 사용하여 참조별로 매개 변수를 적어도 하나 이상 전달하거나 값별로 하나 이상 전달하여 "a \< b"를 작성할 수 있도록 해야 합니다. a\<b는 클래스 A 형식입니다.  
  
 두 매개 변수가 모두 포인터인 경우에는 포인터 주소를 순수하게 비교하며 사용자 정의 변환을 사용하지 않습니다.  
  
 다음 샘플에서는 C2803 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2803.cpp  
// compile with: /c  
class A{};  
bool operator< (const A *left, const A *right);   // C2803  
// try the following line instead  
// bool operator< (const A& left, const A& right);  
```