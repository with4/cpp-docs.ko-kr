---
title: "컴파일러 경고 (수준 1) C4553 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4553
dev_langs:
- C++
helpviewer_keywords:
- C4553
ms.assetid: d8aacbe0-3cb5-4367-a6e5-fd7e28f0ff9d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 526bc1efc428100764b7d17fc110e7196bcaf98b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4553"></a>컴파일러 경고(수준 1) C4553
'operator': 연산자에 영향을 주지 않습니다. 'operator' 사용 하려고 했습니까?  
  
 식 문의 top 식의 영향을 주지 쪽 연산자가 있으면 실수 한 부분 때문일 수 있습니다.  
  
 다음 샘플에서는 C4553 오류가 생성 됩니다.  
  
```  
// C4553.cpp  
// compile with: /W1  
int func()  
{  
   return 0;  
}  
  
int main()  
{  
   int i;  
   i == func();   // C4553  
   // try the following line instead  
   // i = func();  
}  
```