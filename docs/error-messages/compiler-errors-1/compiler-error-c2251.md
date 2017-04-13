---
title: "컴파일러 오류 C2251 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2251
dev_langs:
- C++
helpviewer_keywords:
- C2251
ms.assetid: fefe050c-f8d3-4316-b237-8007dbcdd3bf
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: e9450ea2547043f80130cf6484d1d4975cba9219
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2251"></a>컴파일러 오류 C2251
네임스페이스 'namespace'에 멤버 'member'가 없습니다. 'member'를 사용하시겠습니까?  
  
 컴파일러에서 지정된 네임스페이스의 식별자를 찾을 수 없습니다.  
  
 다음 샘플에서는 C2251을 생성합니다.  
  
```  
// C2251.cpp  
// compile with: /c  
namespace A {  
   namespace B {  
      void f1();  
   }  
  
   using namespace B;  
}  
  
void A::f1() {}   // C2251  
void A::B::f1() {}   // OK  
```
