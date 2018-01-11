---
title: "컴파일러 오류 C2244 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2244
dev_langs: C++
helpviewer_keywords: C2244
ms.assetid: d9911c12-ceb5-4f93-ac47-b44a485215c2
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4aae196f2acf59f8a06659e94583240ecd8a5653
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2244"></a>컴파일러 오류 C2244
'identifier': 함수 정의를 기존 선언과 일치 시킬 수 없습니다.  
  
 단항 + 연산자의 비정상적인 사용 괄호 되어 있지 않은 함수 호출 앞에 사용 되었습니다.  
  
 이 오류는 c + + 프로젝트에만 발생합니다.  
  
 다음 샘플에서는 C2244 오류가 생성 됩니다.  
  
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
  
 C2244는 클래스 템플릿의 멤버 함수에 대 한 잘못 된 함수 시그니처 사용 되는 경우에 발생할 수 있습니다.  
  
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
  
 C2244 멤버 함수 템플릿이 잘못 된 함수 시그니처를 사용할 때에 발생할 수 있습니다.  
  
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
  
 함수 템플릿에 부분적으로 특수화할 수 없습니다.  
  
```  
// C2244d.cpp  
template<class T, class U>  
class QRS {  
   void func(T t, U u);  
};  
  
template<class T>  
void QRS<T,int>::func(T t, int u) {}   // C2244  
```