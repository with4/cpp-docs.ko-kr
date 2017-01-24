---
title: "컴파일러 경고 (수준 1) C4172 | Microsoft Docs"
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
  - "C4172"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4172"
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4172
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지역 변수 또는 임시 변수의 주소를 반환하고 있습니다.  
  
 함수가 임시 개체 또는 지역 변수의 주소를 반환합니다.  함수가 반환할 때 지역 변수 및 임시 개체가 소멸되므로 반환된 주소는 사용할 수 없습니다.  
  
 지역 개체의 주소를 반환하지 않도록 함수를 다시 디자인하십시오.  
  
 다음 샘플에서는 C4172 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4172.cpp  
// compile with: /W1 /LD  
float f = 10;  
  
const double& bar() {  
// try the following line instead  
// const float& bar() {  
   return f;   // C4172  
}  
```