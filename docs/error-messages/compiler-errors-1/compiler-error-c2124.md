---
title: "컴파일러 오류 C2124 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2124
dev_langs:
- C++
helpviewer_keywords:
- C2124
ms.assetid: 93392aaa-5582-4d68-8cc5-bd9c62a0ae7e
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 773cb5b9e2e6a7d52bfb75d64ebf5af7f88e3805
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2124"></a>컴파일러 오류 C2124
0으로 나누기 또는 나머지 연산을 수행했습니다.  
  
 상수 식의 분모가 0입니다. 이 오류를 해결하려면 0으로 나누지 마세요.  
  
 다음 샘플에서는 C2124를 생성합니다.  
  
```  
// C2124.cpp  
int main() {  
  int i = 1 / 0;   // C2124  do not divide by zero  
  int i2 = 12 / 2;   // OK  
}  
```
