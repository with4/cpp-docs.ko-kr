---
title: "컴파일러 오류 C2807 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2807
dev_langs:
- C++
helpviewer_keywords:
- C2807
ms.assetid: bd7a207a-f379-4de6-8ee8-c7cab78b3480
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5fbea2518dabf2851ff6d620095c898f7a2a35c6
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2807"></a>컴파일러 오류 C2807
'operator 연산자' 후 위 두 번째 형식 매개 변수 'int' 여야 합니다.  
  
 후 위 연산자는 두 번째 매개 변수 형식이 잘못 되었습니다.  
  
 다음 샘플에서는 C2807 오류가 생성 됩니다.  
  
```  
// C2807.cpp  
// compile with: /c  
class X {  
public:  
   X operator++ ( X );   // C2807 nonvoid parameter  
   X operator++ ( int );   // OK, int parameter  
};  
```
