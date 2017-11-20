---
title: "컴파일러 경고 (수준 3) C4645 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4645
dev_langs: C++
helpviewer_keywords: C4645
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c327aa47f46ffa7d7533d818d5140fdc5a5933af
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4645"></a>컴파일러 경고(수준 3) C4645
__declspec(noreturn)으로 선언된 함수에 return 문이 있습니다.  
  
 A [return](../../cpp/return-statement-in-program-termination-cpp.md) 문이 [noreturn](../../cpp/noreturn.md) `__declspec` 한정자로 표시된 함수에 있습니다. `return` 문이 무시되었습니다.  
  
 다음 샘플에서는 C4645를 생성합니다.  
  
```  
// C4645.cpp  
// compile with:  /W3  
void __declspec(noreturn) func() {  
   return;   // C4645, delete this line to resolve  
}  
  
int main() {  
}  
```