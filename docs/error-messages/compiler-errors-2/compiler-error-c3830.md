---
title: "컴파일러 오류 C3830 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3830
dev_langs:
- C++
helpviewer_keywords:
- C3830
ms.assetid: c9798f88-5001-4067-9fb1-09957ddc6fa8
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
ms.openlocfilehash: 970a3f032ac367ec24cb5b036e3f3723732da754
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3830"></a>컴파일러 오류 C3830
'type1': 'type2', 값 형식은 인터페이스 클래스에서 상속만 수에서 상속할 수 없습니다  
  
 값 형식이 기본 클래스를 상속할 수 없습니다.  자세한 내용은 참조 [클래스 및 구조체](../../windows/classes-and-structs-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3830 오류가 생성 됩니다.  
  
```  
// C3830a.cpp  
// compile with: /clr /c  
public value struct MyStruct4 {  
   int i;  
};  
  
public value class MyClass : public MyStruct4 {};   // C3830  
  
// OK  
public interface struct MyInterface4 {  
   void i();  
};  
  
public value class MyClass2 : public MyInterface4 {  
public:  
   virtual void i(){}  
};  
```  

