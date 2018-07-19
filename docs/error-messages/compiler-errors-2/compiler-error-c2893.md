---
title: 컴파일러 오류 C2893 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2893
dev_langs:
- C++
helpviewer_keywords:
- C2893
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db3b71a05ece6b79672d47699dc68e0eb5bb1f60
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246700"
---
# <a name="compiler-error-c2893"></a>컴파일러 오류 C2893
'템플릿 이름' 함수 템플릿을 특수화 하지 못했습니다.  
  
 컴파일러는 함수 템플릿을 특수화 하지 못했습니다. 이 오류를 일으키는 많은 원인이 있을 수 있습니다.  
  
 일반적으로 C2893 오류를 해결 하려면 방법은 함수의 서명이 검토 하 고 모든 형식을 인스턴스화할 수 있는지 확인 하는 것입니다.  
  
## <a name="example"></a>예제  
 C2893 때문에 발생 `f`의 템플릿 매개 변수 `T` 것으로 추론 `std::map<int,int>`, 하지만 `std::map<int,int>` 멤버가 없는 `data_type` (`T::data_type` 인스턴스화할 수 있습니다 `T = std::map<int,int>`.). 다음 샘플에서는 C2893 오류가 발생 합니다.  
  
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