---
title: "컴파일러 오류 C3414 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3414
dev_langs:
- C++
helpviewer_keywords:
- C3414
ms.assetid: 715f5432-b509-4f8f-84f5-e1463bac490f
caps.latest.revision: 8
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
ms.openlocfilehash: 0aee8d8860183f73f638e1ec41c6841ad45573d7
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3414"></a>컴파일러 오류 C3414
'member': 가져온된 멤버 함수를 정의할 수 없습니다  
  
 멤버는 참조 된 어셈블리에 정의 된 코드에서 정의 되었습니다.  
  
 다음 샘플에서는 C3414 오류가 생성 됩니다.  
  
```  
// C3414a2.cpp  
// compile with: /clr /LD  
public ref class MyClass {  
public:  
   void Test(){}  
};  
```  
  
 그리고  
  
```  
// C3414b2.cpp  
// compile with: /clr  
#using <C3414a2.dll>  
  
void MyClass::Test() {    // C3414  
}  
  
System::Object::Object() {    // C3414  
}  
```  

