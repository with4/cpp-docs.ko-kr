---
title: "컴파일러 오류 C2947 | Microsoft Docs"
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
  - "C2947"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2947"
ms.assetid: 6c056f62-ec90-4883-8a67-aeeb6ec13546
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2947
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

construct을\(를\) 끝내려면 '\>' 기호가 있어야 하는데 'syntax'이\(가\) 있습니다.  
  
 제네릭 또는 템플릿 인수 목록이 올바르게 끝나지 않았을 수 있습니다.  
  
 C2947은 구문 오류로 인해 발생할 수도 있습니다.  
  
 다음 샘플에서는 C2947 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2947.cpp  
// compile with: /c  
template <typename T>=   // C2947  
// try the following line instead  
// template <typename T>  
struct A {};  
```