---
title: 컴파일러 경고 (수준 3) C4521 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4521
dev_langs:
- C++
helpviewer_keywords:
- C4521
ms.assetid: 057d770c-ebcf-44cd-b943-1b1bb1ceaa8c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a81fe751521e5f2f43d3c96fb15098bac914c614
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4521"></a>컴파일러 경고(수준 3) C4521
'class': 복사 생성자를 여러 개 지정  
  
 클래스에 단일 형식의 복사 생성자를 여러 개 있습니다. 이 경고는 정보를 제공 합니다. 생성자는 프로그램에서 호출할 수 있습니다.  
  
 사용 하 여는 [경고](../../preprocessor/warning.md) pragma를이 경고를 표시 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4521 오류가 발생 합니다.  
  
```  
// C4521.cpp  
// compile with: /EHsc /W3  
#include <iostream>  
  
using namespace std;  
class A {  
public:  
   A() { cout << "A's default constructor" << endl; }  
   A( A &o ) { cout << "A&" << endl; }  
   A( const A &co ) { cout << "const A&" << endl; }   // C4521  
};  
  
int main() {  
   A o1;         // Calls default constructor.  
   A o2( o1 );   // Calls A( A& ).  
   const A o3;   // Calls default constructor.  
   A o4( o3 );   // Calls A( const A& ).  
}  
```