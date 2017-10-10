---
title: "컴파일러 오류 C2019 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2019
dev_langs:
- C++
helpviewer_keywords:
- C2019
ms.assetid: 4f37b1e1-9eca-418f-a4c3-141e8512d7b6
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 93c91bccf1b9bc709d006696b22e0e8c2febb713
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2019"></a>컴파일러 오류 C2019
전처리기 지시문이 있어야 하는데 'character'가 있습니다.  
  
 다음에 오는 문자는 `#` 부호는 전처리기 지시문의 첫 번째 문자가 아닙니다.  
  
 다음 샘플에서는 C2019 오류가 생성 됩니다.  
  
```  
// C2019.cpp  
#!define TRUE 1   // C2019  
```  
  
 해결 방법:  
  
```  
// C2019b.cpp  
// compile with: /c  
#define TRUE 1  
```
