---
title: "컴파일러 오류 C2691 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2691
dev_langs:
- C++
helpviewer_keywords:
- C2691
ms.assetid: 6925f8f3-ea60-4909-91e6-b781492c645d
caps.latest.revision: 11
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: eb9610c1540b07485a8fa4b4124346b4ee4281d6
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2691"></a>컴파일러 오류 C2691
데이터 형식: 관리 되는 또는 WinRTarray이 요소 형식을 사용할 수 없습니다  
  
 관리되는 배열 또는 WinRT 배열의 요소 형식은 값 형식이나 참조 형식일 수 있습니다.  
  
 다음 샘플에서는 C2691 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2691a.cpp  
// compile with: /clr  
class A {};  
  
int main() {  
   array<A>^ a1 = gcnew array<A>(20);   // C2691  
   array<int>^ a2 = gcnew array<int>(20);   // value type OK  
}  
```  

