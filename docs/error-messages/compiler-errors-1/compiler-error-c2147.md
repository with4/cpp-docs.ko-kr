---
title: "컴파일러 오류 C2147 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2147
dev_langs:
- C++
helpviewer_keywords:
- C2147
ms.assetid: d1adb3bf-7ece-4815-922c-ad7492fb6670
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f26a7df3605c01a56e8efcc0f569f9803a0755e4
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2147"></a>컴파일러 오류 C2147
구문 오류: '' 식별자가 새 키워드  
  
 식별자는 이제 언어의 예약 된 키워드를 사용 했습니다.  
  
 다음 샘플에서는 C2147 오류가 생성 됩니다.  
  
```  
// C2147.cpp  
// compile with: /clr  
int main() {  
   int gcnew = 0;   // C2147  
   int i = 0;   // OK  
}  
```
