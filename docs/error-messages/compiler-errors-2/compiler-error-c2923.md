---
title: "컴파일러 오류 c 2923 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2923
dev_langs:
- C++
helpviewer_keywords:
- C2923
ms.assetid: 6b92933b-13ef-4124-99d9-b89f9fdae030
caps.latest.revision: 11
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
ms.openlocfilehash: 62068119ea345a8df30bd0e23384016801ee0857
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2923"></a>컴파일러 오류 C2923
'type': 'identifier'는 'param' 매개 변수에 대한 올바른 템플릿 형식 인수가 아닙니다.  
  
 인수 목록에 템플릿 또는 제네릭을 인스턴스화하는 데 필요한 형식이 없습니다. 템플릿 또는 제네릭 선언을 확인합니다.  
  
 다음 샘플에서는 C2923을 생성합니다.  
  
```  
// C2923.cpp  
template <class T> struct TC {};  
int x;  
int main() {  
   TC<x>* tc2;   // C2923  
   TC<int>* tc2;   // OK  
}  
```  
  
 제네릭을 사용할 때도 C2923이 발생할 수 있습니다.  
  
```  
// C2923b.cpp  
// compile with: /clr /c  
generic <class T> ref struct GC {};  
  
int x;  
  
int main() {  
   GC<x>^ gc2;   // C2923  
   GC<int>^ gc2;   // OK  
}  
```
