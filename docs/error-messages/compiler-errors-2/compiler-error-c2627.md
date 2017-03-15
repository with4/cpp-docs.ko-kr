---
title: "컴파일러 오류 C2627 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2627
dev_langs:
- C++
helpviewer_keywords:
- C2627
ms.assetid: 7fc6c5ac-c7c9-4f0b-ad52-f52252526458
caps.latest.revision: 9
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
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: 2d0354971d4f512c7ba98a1e6d0f7cb014cba5af
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2627"></a>컴파일러 오류 C2627
'function': 멤버 함수가 익명 공용 구조체에서 허용 되지 않습니다  
  
 [익명 공용 구조체](../../cpp/unions.md#anonymous_unions) 멤버 함수를 사용할 수 없습니다.  
  
 다음 샘플에서는 C2627 오류가 생성 됩니다.  
  
```  
// C2627.cpp  
int main() {  
   union { void f(){} };   // C2627  
   union X { void f(){} };  
}  
```
