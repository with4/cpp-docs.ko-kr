---
title: "컴파일러 오류 C3490 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 42923edc2d238e7f0b64858561f7d23d211abd80
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3490"></a>컴파일러 오류 C3490
'var'는 const 개체를 통해 액세스되고 있으므로 수정할 수 없습니다.  
  
 `const` 메서드에서 선언된 람다 식은 변경할 수 없는 멤버 데이터를 수정할 수 없습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   메서드 선언에서 `const` 한정자를 제거합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `_i` 메서드의 멤버 변수 `const` 를 수정하므로 C3490을 생성합니다.  
  
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
