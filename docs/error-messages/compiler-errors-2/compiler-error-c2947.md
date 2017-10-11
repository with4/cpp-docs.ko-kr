---
title: "컴파일러 오류 C2947 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2947
dev_langs:
- C++
helpviewer_keywords:
- C2947
ms.assetid: 6c056f62-ec90-4883-8a67-aeeb6ec13546
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: bb5b22d4fd4b874e19cff564dec96609f9da0789
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2947"></a>컴파일러 오류 C2947
construct을(를) 끝내려면 '>' 기호가 있어야 하는데 'syntax'이(가) 있습니다.  
  
 제네릭 또는 템플릿 인수 목록은 올바르게 종료 되지 않을 수 있습니다.  
  
 C2947 구문 오류로 인해 발생할 수도 있습니다.  
  
 다음 샘플에서는 C2947 오류가 생성 됩니다.  
  
```  
// C2947.cpp  
// compile with: /c  
template <typename T>=   // C2947  
// try the following line instead  
// template <typename T>  
struct A {};  
```
