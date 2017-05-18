---
title: "컴파일러 경고 (수준 1) C4602 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4602
dev_langs:
- C++
helpviewer_keywords:
- C4602
ms.assetid: c1f0300f-e2a2-4c9e-a7c3-4c7318d10509
caps.latest.revision: 8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: b47b7c0cb0271aa6ab463fb5505af348bc5e75af
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4602"></a>컴파일러 경고(수준 1) C4602
\#pragma pop_macro: '매크로 이름'이 식별자에 대 한 이전 #pragma push_macro가 없습니다  
  
 사용 하는 경우 [pop_macro](../../preprocessor/pop-macro.md) 특정 매크에 대해 해야 먼저 전달한 해당 매크로 이름을 [push_macro](../../preprocessor/push-macro.md)합니다. 예를 들어 다음 샘플에서는 C4602를 생성합니다.  
  
```  
// C4602.cpp  
// compile with: /W1  
int main()  
{  
   #pragma pop_macro("x")   // C4602 x is not on the stack  
}  
```
