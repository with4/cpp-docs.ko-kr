---
title: "컴파일러 오류 C3069 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3069"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3069"
ms.assetid: ca94291b-2bb4-4e3f-9acf-534234b83513
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C3069
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator': 열거형 형식에 사용할 수 없습니다.  
  
 CLR 열거형에 대해서는 연산자가 지원되지 않습니다.  자세한 내용은 [연산자 및 열거형 사용](../../misc/operators-and-enumerations.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3069를 생성합니다.  
  
```  
// C3069.cpp // compile with: /clr enum struct E { e1 }; enum F { f1 }; int main() { E e = E::e1; bool tf; tf = !e;   // C3069 // supported for native enums F f = f1; tf = !f; }  
```