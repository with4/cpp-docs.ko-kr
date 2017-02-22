---
title: "컴파일러 오류 C3227 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3227"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3227"
ms.assetid: 7939c23a-96c8-43c2-89e9-f217d132d155
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# 컴파일러 오류 C3227
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'parameter' : 'keyword'을\(를\) 사용하여 제네릭 형식을 할당할 수 없습니다.  
  
 형식을 인스턴스화하려면 적절한 생성자가 필요합니다.  그러나 적절한 생성자를 사용할 수 있는지 컴파일러에서 확인할 수 없습니다.  
  
 이 오류를 해결하려면 제네릭 대신 템플릿을 사용하거나 여러 메서드 중 하나를 사용하여 형식의 인스턴스를 만드십시오.  
  
## 예제  
 다음 샘플에서는 C3227 오류가 발생하는 경우를 보여 줍니다.  
  
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