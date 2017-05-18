---
title: "컴파일러 경고 (수준 3) C4281 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4281
dev_langs:
- C++
helpviewer_keywords:
- C4281
ms.assetid: a9771261-5725-4fc6-87b6-16cf92113a25
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: cfe21418e4f5fdbdfb82c79c7cd50a1d3fa0a97e
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="compiler-warning-level-3-c4281"></a>컴파일러 경고(수준 3) C4281
'type' 형식이 'operator->' 재귀가 발생 했습니다.  
  
 코드 허용 **-> 연산자** 자신을 호출 하 합니다.  
  
 다음 샘플에서는 C4281 오류가 생성 됩니다.  
  
```  
// C4281.cpp  
// compile with: /W3 /WX  
struct A;  
struct B;  
struct C;  
  
struct A  
{  
   int z;  
   B& operator->();  
};  
  
struct B  
{  
   C& operator->();  
};  
  
struct C  
{  
   A& operator->();  
};  
  
void f(A p)  
{  
   int i = p->z; // C4281  
}  
```
