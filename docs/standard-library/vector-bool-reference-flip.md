---
title: vector&lt;bool&gt;::reference::flip | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vector<bool>::reference::flip
- std::vector<bool>::reference::flip
dev_langs:
- C++
helpviewer_keywords:
- reference::flip method
ms.assetid: ef940365-cbe4-4a87-a3e2-1f3cfa357e29
caps.latest.revision: 21
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
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: 3df75ecbe47a1e6da00aa1b7a6bf55982a307d2d
ms.lasthandoff: 02/24/2017

---
# <a name="vectorltboolgtreferenceflip"></a>vector&lt;bool&gt;::reference::flip
참조된 [vector\<bool>](../standard-library/vector-bool-class.md) 요소의 부울 값을 반전합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void flip();
```  
  
## <a name="example"></a>예제  
  
```cpp  
// vector_bool_ref_flip.cpp  
// compile with: /EHsc /W4  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    cout << boolalpha;  
  
    vector<bool> vb = { true, false, false, true, true };  
  
    cout << "The vector is: " << endl << "    ";  
    for (const auto& b : vb) {  
        cout << b << " ";  
    }  
    cout << endl;  
  
    vector<bool>::reference vbref = vb.front();  
    vbref.flip();  
  
    cout << "The vector with first element flipped is: " << endl << "    ";  
    for (const auto& b : vb) {  
        cout << b << " ";  
    }  
    cout << endl;  
}  
  
```  
  
## <a name="output"></a>출력  
  
```  
The vector is:  
    true false false true true  
The vector with first element flipped is:  
    false false false true true  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<vector>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [vector\<bool>::reference 클래스](../standard-library/vector-bool-reference-class.md)   
 [C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)


