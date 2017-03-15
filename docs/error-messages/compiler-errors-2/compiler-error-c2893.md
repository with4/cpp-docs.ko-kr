---
title: "컴파일러 오류 C2893 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2893"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2893"
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 컴파일러 오류 C2893
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'template name' 함수 템플릿을 특수화하지 못했습니다.  
  
 컴파일러가 함수 템플릿을 특수화하지 못했습니다.  이 오류는 여러 원인으로 인해 발생할 수 있습니다.  
  
 일반적으로 C2893 오류를 해결하려면 함수의 시그니처를 검토하고 모든 형식을 인스턴스화할 수 있는지 확인해야 합니다.  
  
## 예제  
 C2893은 `f`의 템플릿 매개 변수 `T`가 `std::map<int,int>`인 것으로 추론되지만 `std::map<int,int>`에 멤버 `data_type`이 없는 경우에 발생합니다. 즉, `T = std::map<int,int>`를 사용하여 `T::data_type`을 인스턴스화할 수 없는 경우입니다.  다음 샘플에서는 C2893 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2893.cpp  
// compile with: /c /EHsc  
#include<map>  
using namespace std;  
class MyClass {};  
  
template<class T>   
inline typename T::data_type  
// try the following line instead  
// inline typename  T::mapped_type  
f(T const& p1, MyClass const& p2);  
  
template<class T>  
void bar(T const& p1) {  
    MyClass r;  
    f(p1,r);   // C2893  
}  
  
int main() {  
   map<int,int> m;  
   bar(m);  
}  
```