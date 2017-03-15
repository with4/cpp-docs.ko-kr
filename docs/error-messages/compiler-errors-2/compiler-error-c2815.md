---
title: "컴파일러 오류 C2815 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2815
dev_langs:
- C++
helpviewer_keywords:
- C2815
ms.assetid: d0256fd6-0721-4c99-b03c-52d96e77a613
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
ms.openlocfilehash: 129ad6a0359fbee402b39c5e7ff498602e97479d
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2815"></a>컴파일러 오류 C2815
operator delete: 첫 번째 형식 매개 변수 여야 ' void *', 'param' 사용 하지만  
  
 사용자 정의 된 [delete 연산자](../../standard-library/new-operators.md#operator_delete) 함수 형식의 첫 번째 형식 매개 변수를 사용 해야 `void *`합니다.  
  
 다음 샘플에서는 C2815 오류가 생성 됩니다.  
  
```  
// C2815.cpp  
// compile with: /c  
class CMyClass {  
public:  
   void mf1(int *a);  
   void operator delete(CMyClass *);   // C2815  
   void operator delete(void *);   
};  
```
