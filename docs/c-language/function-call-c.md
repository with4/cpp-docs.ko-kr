---
title: "함수 호출 (C) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "함수 호출"
  - "함수 호출, C 함수"
  - "함수[C++], 호출"
ms.assetid: 35c66719-3f15-4d3b-97da-4e19dc97b308
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 함수 호출 (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

"함수 호출"은 호출되는 함수의 이름 또는 함수 포인터의 값 및 선택적으로 함수에 전달되는 인수를 포함하는 식입니다.  
  
## 구문  
 후위 식:  
 후위 식**\(**인수 식 목록선택**\)**  
  
 인수 식 목록:  
 *인수 식*  
  
 인수 식 목록**,** 인수 식  
  
 후위 식은 반드시 함수 식별자 또는 함수 포인터 값과 같은 함수 주소를 반드시 계산하여야 하고 인수 식 목록은 해당 식 목록의 값\("인수"\)이 함수로 전달되는 식 목록\(쉼표로 구분\)입니다.  *인수 식 목록* 인수는 비워둘 수 있습니다.  
  
 함수 호출 식에는 함수 반환 값의 값과 형식이 있습니다.  함수는 배열 형식의 개체를 반환할 수 없습니다.  함수의 반환 형식이 `void`인 경우, 즉, 함수가 값을 반환하지 않도록 선언된 경우 함수 호출 식 또한 `void` 형식을 가집니다. 자세한 내용은 [함수 호출](../c-language/function-calls.md)을 참조하십시오.  
  
## 참고 항목  
 [함수 호출 연산자: \(\)](../cpp/function-call-operator-parens.md)