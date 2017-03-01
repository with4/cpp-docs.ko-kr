---
title: "컴파일러 오류 C2976 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2976
dev_langs:
- C++
helpviewer_keywords:
- C2976
ms.assetid: d9bf9836-325e-4f72-a7e3-a67cf19d32e7
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
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: d691eba50403819e1a468b850995f4ae55a3731f
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2976"></a>컴파일러 오류 C2976
'identifier': 인수가 너무 적습니다.  
  
 제네릭 또는 템플릿 하나 이상의 실제 인수가 없습니다. 제네릭 또는 템플릿 선언을 확인하여 올바른 매개 변수 개수를 찾습니다.  
  
 이 오류는 c + + 표준 라이브러리 구성 요소에 템플릿 인수가 없는 경우에 발생할 수 있습니다.  
  
 다음 샘플에서는 C2976 오류가 생성 됩니다.  
  
```  
// C2976.cpp  
template <class T>   
struct TC {  
   T t;  
};  
int main() {  
   TC<>* t;   // C2976  
   TC<int>* t2;   // OK  
}  
```  
  
 C2976은 제네릭을 사용 하는 경우에 발생할 수 있습니다.  
  
```  
// C2976b.cpp  
// compile with: /clr  
generic <class T>  
ref struct GC {  
   T t;  
};  
  
int main() {  
   GC<>^ g;   // C2976  
   GC<int>^ g2;   // OK  
}  
```
