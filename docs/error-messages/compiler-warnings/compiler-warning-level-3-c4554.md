---
title: "컴파일러 경고 (수준 3) C4554 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4554
dev_langs: C++
helpviewer_keywords: C4554
ms.assetid: 55bb68f0-2e80-4330-8921-51083c4f8d53
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 063c317e25be808c14b65c08fe005bbbac7109e4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4554"></a>컴파일러 경고(수준 3) C4554
'operator': 연산자 우선 순위에 오류가; 확인 우선 순위를 명확 하 게 괄호를 사용 합니다.  
  
 다음 샘플에서는 C4554 오류가 생성 됩니다.  
  
```  
// C4554.cpp  
// compile with: /W3 /WX  
int main() {  
   int a = 0, b = 0, c = 0;  
   a = a << b + c;   // C4554  
   // probably intended (a << b) + c,  
   // but will get a << (b + c)  
}  
```