---
title: "vector&lt;bool&gt;::reference::operator= | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "="
  - "operator="
  - "vector<bool>::reference::operator="
  - "std::vector<bool>::reference::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "= 연산자, 특정 표준 C++ 라이브러리 개체와 사용"
  - "reference::operator="
ms.assetid: eed20d81-36b9-40b2-a3b6-340ed0bb4f34
caps.latest.revision: 20
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# vector&lt;bool&gt;::reference::operator=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

비트에 부울 값을 할당하거나 참조된 요소에 저장된 값을 비트에 할당합니다.  
  
## 구문  
  
```  
reference& operator=(  
   const reference& Right  
);  
reference& operator=(  
   bool Val  
);  
```  
  
#### 매개 변수  
 `Right`  
 해당 값을 비트에 할당할 요소 참조입니다.  
  
 `Val`  
 비트에 할당될 부울 값입니다.  
  
## 예제  
  
```cpp  
// vector_bool_ref_op_assign.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
#include <string>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    cout << boolalpha;  
  
    vector<bool> vb = { true, false, false, true, true };  
  
    print("The vector is: ", vb);  
  
    // Invoke vector<bool>::reference::operator=()  
    vector<bool>::reference refelem1 = vb[0];  
    vector<bool>::reference refelem2 = vb[1];  
    vector<bool>::reference refelem3 = vb[2];  
  
    bool b1 = refelem1;  
    bool b2 = refelem2;  
    bool b3 = refelem3;  
    cout << "The original value of the 1st element stored in a bool: " << b1 << endl;  
    cout << "The original value of the 2nd element stored in a bool: " << b2 << endl;  
    cout << "The original value of the 3rd element stored in a bool: " << b3 << endl;  
    cout << endl;  
  
    refelem2 = refelem1;  
  
    print("The vector after assigning refelem1 to refelem2 is now: ", vb);  
  
    refelem3 = true;  
  
    print("The vector after assigning false to refelem1 is now: ", vb);  
  
    // The initial values are still stored in the bool variables and remained unchanged  
    cout << "The original value of the 1st element still stored in a bool: " << b1 << endl;  
    cout << "The original value of the 2nd element still stored in a bool: " << b2 << endl;  
    cout << "The original value of the 3rd element still stored in a bool: " << b3 << endl;  
    cout << endl;  
}  
  
```  
  
## Output  
  
```  
The vector is: true false false true true  
The original value of the 1st element stored in a bool: true  
The original value of the 2nd element stored in a bool: false  
The original value of the 3rd element stored in a bool: false  
  
The vector after assigning refelem1 to refelem2 is now: true true false true true  
The vector after assigning false to refelem1 is now: true true true true true  
The original value of the 1st element still stored in a bool: true  
The original value of the 2nd element still stored in a bool: false  
The original value of the 3rd element still stored in a bool: false  
```  
  
## 요구 사항  
 **헤더:** \<vector\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [vector\<bool\>::reference 클래스](../standard-library/vector-bool-reference-class.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)