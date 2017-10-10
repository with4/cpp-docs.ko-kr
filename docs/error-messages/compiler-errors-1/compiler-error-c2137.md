---
title: "컴파일러 오류 C2137 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2137
dev_langs:
- C++
helpviewer_keywords:
- C2137
ms.assetid: 984687ee-7766-4f6b-ae15-0c9a010e2366
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 81cb3b0f227db9093f64b5f5af4aadf5ee45baa1
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2137"></a>컴파일러 오류 C2137
문자 상수가 비어 있습니다.  
  
 빈 문자 상수(' ')는 허용되지 않습니다.  
  
 다음 샘플에서는 C2137을 생성합니다.  
  
```  
// C2137.cpp  
int main() {  
   char c = '';   // C2137  
   char d = ' ';   // OK  
}  
```
