---
title: "컴파일러 오류 C2244 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2244"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2244"
ms.assetid: d9911c12-ceb5-4f93-ac47-b44a485215c2
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C2244
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 함수 정의를 기존 선언과 일치시킬 수 없습니다.  
  
 괄호를 사용하지 않는 단항 \+ 연산자를 함수 호출 앞에 예외적으로 사용했습니다.  
  
 이 오류는 C\+\+ 프로젝트에서만 발생합니다.  
  
 다음 샘플에서는 C2244 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2244.cpp  
int func(char) {  
   return 0;  
}   
  
int func(int) {  
   return 0;  
}  
  
int main() {  
   +func;   // C2244  
}  
```  
  
 C2244는 클래스 템플릿의 멤버 함수에 대해 잘못된 함수 시그니처를 사용하는 경우에도 발생할 수 있습니다.  
  
```  
// C2244b.cpp  
// compile with: /c  
template<class T>   
class XYZ {  
   void func(T t);  
};  
  
template<class T>  
void XYZ<T>::func(int i) {}   // C2244 wrong function signature  
// try the following line instead  
// void XYZ<T>::func(T t) {}  
```  
  
 C2244는 멤버 함수 템플릿에 대해 잘못된 함수 시그니처를 사용하는 경우에도 발생할 수 있습니다.  
  
```  
// C2244c.cpp  
// compile with: /c  
class ABC {  
   template<class T>   
   void func(int i, T t);  
};  
  
template<class T>  
void ABC::func(int i) {}   // C2244 wrong signature  
// try the following line instead  
// void ABC::func(int i, T t) {}  
```  
  
 함수 템플릿은 부분적으로 특수화할 수 없습니다.  
  
```  
// C2244d.cpp  
template<class T, class U>  
class QRS {  
   void func(T t, U u);  
};  
  
template<class T>  
void QRS<T,int>::func(T t, int u) {}   // C2244  
```