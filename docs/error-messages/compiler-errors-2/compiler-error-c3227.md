---
title: "컴파일러 오류 C3227 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3227
dev_langs:
- C++
helpviewer_keywords:
- C3227
ms.assetid: 7939c23a-96c8-43c2-89e9-f217d132d155
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2f65791d709b5790144cd919bf06b61fd94da973
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3227"></a>컴파일러 오류 C3227
'parameter': 제네릭 형식에 할당할 'keyword'를 사용할 수 없습니다  
  
 형식을 인스턴스화하려면는 적절 한 생성자가 필요 합니다. 그러나, 컴파일러는 적절 한 생성자를 사용할 수 있도록 수 없습니다.  
  
 이 오류를 해결 하려면 템플릿 제네릭 대신 사용할 수 있습니다 또는 형식의 인스턴스를 만드는 여러 가지 방법 중 하나를 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3227 오류가 발생 합니다.  
  
```  
// C3227.cpp  
// compile with: /clr /c  
generic<class T> interface class ICreate {  
   static T Create();  
};  
  
generic <class T>  
where T : ICreate<T>  
ref class C {  
   void f() {  
      T t = new T;   // C3227  
  
      // OK  
      T t2 = ICreate<T>::Create();  
      T t3 = safe_cast<T>( System::Activator::CreateInstance(T::typeid) );  
   }  
};  
```
