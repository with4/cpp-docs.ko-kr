---
title: "컴파일러 오류 C2897 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2897"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2897"
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C2897
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

destructor\/finalizer은\(는\) 함수 템플릿일 수 없습니다.  
  
 소멸자 또는 종료자는 오버로드할 수 없으므로 소멸자를 템플릿으로 선언\(소멸자 집합을 정의\)할 수 없습니다.  
  
 다음 샘플에서는 C2897 오류가 발생하는 경우를 보여 줍니다.  
  
## 예제  
 다음 샘플에서는 C2897 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2897.cpp  
// compile with: /c  
class X {  
public:  
   template<typename T> ~X() {}   // C2897  
};  
```  
  
## 예제  
 다음 샘플에서는 C2897 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2897_b.cpp  
// compile with: /c /clr  
ref struct R2 {  
protected:  
   template<typename T> !R2(){}   // C2897 error  
};  
```