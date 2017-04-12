---
title: "컴파일러 오류 C3490 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3490
dev_langs:
- C++
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
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
translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 83a215b1c4883ba7ed4b285af8c4efafe2cfaa05
ms.lasthandoff: 04/04/2017

---
# <a name="compiler-error-c3490"></a>컴파일러 오류 C3490
'var'는 const 개체를 통해 액세스되고 있으므로 수정할 수 없습니다.  
  
 `const` 메서드에서 선언된 람다 식은 변경할 수 없는 멤버 데이터를 수정할 수 없습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   메서드 선언에서 `const` 한정자를 제거합니다.  
  
## <a name="example"></a>예제  
 멤버 변수를 수정 하기 때문에 다음 예제에서는 c 3490 `_i` 에 `const` 메서드:  
  
```  
// C3490a.cpp  
// compile with: /c  
  
class C  
{  
   void f() const   
   {  
      auto x = [=]() { _i = 20; }; // C3490  
   }  
  
   int _i;  
};  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 메서드 선언에서 `const` 한정자를 제거하여 C3490를 해결합니다.  
  
```  
// C3490b.cpp  
// compile with: /c  
  
class C  
{  
   void f()  
   {  
      auto x = [=]() { _i = 20; };  
   }  
  
   int _i;  
};  
```  
  
## <a name="see-also"></a>참고 항목  
 [람다 식](../../cpp/lambda-expressions-in-cpp.md)
