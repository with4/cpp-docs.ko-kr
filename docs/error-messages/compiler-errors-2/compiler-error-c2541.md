---
title: "컴파일러 오류 C2541 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2541
dev_langs:
- C++
helpviewer_keywords:
- C2541
ms.assetid: ed95180f-00df-4e62-a8e9-1b6dab8281bf
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 24bb63554f67d5496e46fb1ab8fa7133fadc38c5
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2541"></a>컴파일러 오류 C2541
'delete': 삭제: 포인터가 아닌 개체를 삭제할 수 없습니다  
  
 [삭제](../../cpp/delete-operator-cpp.md) 연산자가 포인터가 아닌 개체에 사용 되었습니다.  
  
 다음 샘플에서는 C2541 오류가 생성 됩니다.  
  
```  
// C2541.cpp  
int main() {  
   int i;  
   delete i;   // C2541 i not a pointer  
  
   // OK  
   int *ip = new int;  
   delete ip;  
}  
```
