---
title: "컴파일러 경고 (수준 3) C4646 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4646
dev_langs:
- C++
helpviewer_keywords:
- C4646
ms.assetid: 23677e8e-603e-40e0-b99a-2e4894a1278e
caps.latest.revision: 7
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
ms.openlocfilehash: 9fe7c1ca87dd80133e4073f41ad434dd24052db5
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-3-c4646"></a>컴파일러 경고(수준 3) C4646
__declspec(noreturn)으로 선언된 함수에 void가 아닌 반환 형식이 있습니다.  
  
 로 표시 한 함수는 [noreturn](../../cpp/noreturn.md) `__declspec` 한정자 있어야는 [void](../../cpp/void-cpp.md) 형식을 반환 합니다.  
  
 다음 샘플에서는 C4646을 생성합니다.  
  
```  
// C4646.cpp  
// compile with: /W3 /WX  
int __declspec(noreturn) TestFunction()  
{   // C4646  make return type void  
}  
```
