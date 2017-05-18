---
title: "컴파일러 경고 (수준 4) C4130 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4130
dev_langs:
- C++
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
caps.latest.revision: 6
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
ms.openlocfilehash: 32ec1055c5da769c026b778897a5bd9b741b2d40
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4130"></a>컴파일러 경고(수준 4) C4130
'operator': 문자열 상수의 주소에서 논리 연산을 수행했습니다.  
  
 문자열 리터럴의 주소와 함께 연산자를 사용하면 예기치 않은 코드가 생성됩니다.  
  
 다음 샘플에서는 C4130을 생성합니다.  
  
```  
// C4130.cpp  
// compile with: /W4  
int main()  
{  
   char *pc;  
   pc = "Hello";  
   if (pc == "Hello") // C4130  
   {  
   }  
}  
```  
  
 **if** 문은 `pc` 포인터에 저장된 값을 코드에서 문자열이 발생할 때마다 개별적으로 할당되는 "Hello" 문자열의 주소와 비교합니다. **if** 문은 `pc` 가 가리키는 문자열을 "Hello" 문자열과 비교하지 않습니다.  
  
 문자열을 비교하려면 `strcmp` 함수를 사용합니다.
