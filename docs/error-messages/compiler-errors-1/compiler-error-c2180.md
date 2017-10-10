---
title: "컴파일러 오류 C2180 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2180
dev_langs:
- C++
helpviewer_keywords:
- C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 181309cca171c872a7c3767729a755d6e73bd288
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2180"></a>컴파일러 오류 C2180
제어 식이 'type' 형식입니다.  
  
 `if`, `while`, `for` 또는 `do` 문의 제어 식은 `void`로 캐스팅되는 식입니다. 이 문제를 해결하려면 `bool` 또는 `bool`로 변환할 수 있는 형식을 생성하는 식으로 제어 식을 변경합니다.  
  
 다음 샘플에서는 C2180 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2180.c  
  
int main() {  
   while ((void)1)   // C2180  
      return 1;  
   while (1)         // OK  
      return 0;  
}  
```
