---
title: "컴파일러 오류 C2319 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2319
dev_langs:
- C++
helpviewer_keywords:
- C2319
ms.assetid: 25263e6e-f5ba-4d2c-8727-8c2d8ca2e5ce
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 83856c006effc92319afb7a3afd5360344e7b746
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2319"></a>컴파일러 오류 C2319
'try/catch'는 복합 문이 뒤에 와야 합니다. '{'가 없습니다.  
  
 `try` 또는 `catch` 블록이 `try` 또는 `catch` 문 다음에 오지 않습니다. 블록은 중괄호로 묶어야 합니다.  
  
 다음 샘플에서는 C2319를 생성합니다.  
  
```  
// C2319.cpp  
// compile with: /EHsc  
#include <eh.h>  
class C {};  
int main() {  
   try {  
      throw "ooops!";  
   }  
   catch( C ) ;    // C2319  
   // try the following line instead  
   // catch( C ) {}  
}  
```
