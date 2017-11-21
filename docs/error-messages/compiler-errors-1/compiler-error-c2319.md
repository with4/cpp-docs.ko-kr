---
title: "컴파일러 오류 C2319 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2319
dev_langs: C++
helpviewer_keywords: C2319
ms.assetid: 25263e6e-f5ba-4d2c-8727-8c2d8ca2e5ce
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 23db7e68a5f590d7c20f70e122b746b0f43fd2fd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
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