---
title: "컴파일러 경고 (수준 1) C4346 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4346"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4346"
ms.assetid: 68ee562d-cca9-4a2a-9a1b-14ad1a1e7396
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4346
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name': 종속 이름이 형식이 아닙니다.  
  
 종속 이름을 형식으로 처리하려면 [typename](../../cpp/typename.md) 키워드를 사용해야 합니다.  이는 ISO C\+\+ 표준에 맞도록 Visual C\+\+ .NET 2003 컴파일러에 이루어진 주요 변경 내용입니다.  
  
 모든 버전의 Visual C\+\+에서 코드가 똑같은 방식으로 작동하도록 하려면 `typename`을 선언에 추가하십시오.  
  
 다음 샘플에서는 C4346 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4346.cpp  
// compile with: /WX /LD  
template<class T>  
struct C {  
   T::X* x;   // C4346  
   // try the following line instead  
   // typename T::X* x;  
};  
```  
  
 다음 샘플에서는 **typename** 키워드를 사용해야 하는 다른 예를 보여 줍니다.  
  
```  
// C4346b.cpp  
// compile with: /LD /W1  
template<class T>  
const typename T::X& f(typename T::Z* p);   // Required in both places  
  
template<class T, int N>  
struct L{};  
  
template<class T>  
struct M : public L<typename T::Type, T::Value>   
{   // required on type argument, not on non-type argument  
   typedef typename T::X   Type;  
   Type f();   // OK: "Type" is a type-specifer  
   typename T::X g();   // typename required  
   operator typename T::Z();   // typename required      
};  
```  
  
 또 다른 예입니다.  
  
```  
// C4346c.cpp  
// compile with: /LD /WX  
struct Y {  
   typedef int Y_t;  
};  
  
template<class T>  
struct A {  
   typedef Y A_t;  
};  
  
template<class T>  
struct B {  
   typedef /*typename*/ A<T>::A_t B_t;   // C4346 typename needed here  
   typedef /*typename*/ B_t::Y_t  B_t2;   // typename also needed here  
};  
```