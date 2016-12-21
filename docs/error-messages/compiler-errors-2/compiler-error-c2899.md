---
title: "컴파일러 오류 C2899 | Microsoft Docs"
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
  - "C2899"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2899"
ms.assetid: a8942605-5bef-4d1c-b74a-41ae25423b22
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2899
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식 이름을 템플릿 선언 외부에서 사용할 수 없습니다.  
  
 [typename](../../cpp/typename.md) 키워드는 템플릿 정의 또는 선언에만 사용할 수 있습니다.  템플릿 선언에서는 두 가지 방식으로 사용할 수 있습니다.  
  
```  
// C2899.cpp  
// compile with: /c  
template<typename T>   
class X {};  
  
// Another way  
template<class T>   
struct XX {  
   typename T::A a;   // T::A is a type  
};  
```  
  
 다음 샘플에서는 C2899 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2899b.cpp  
// compile with: /c  
struct Y {  
   typedef int B;  
   typename Y::B b;   // C2899  
};  
  
```