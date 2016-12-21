---
title: "참조 형식 함수 반환 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "데이터 형식[C++], 함수 반환 형식"
  - "함수 반환 형식, 참조 형식"
  - "함수[C++], 반환 형식"
ms.assetid: 5b73be1d-2dc7-41df-ab0a-adcba36f2ad1
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 참조 형식 함수 반환
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

참조 형식을 반환하도록 함수를 선언할 수 있습니다.  이렇게 선언하는 데에는 다음과 같은 두 가지 이유가 있습니다.  
  
-   반환되는 정보가 충분히 큰 개체여서 복사본 대신 참조를 반환하는 것이 더 효율적입니다.  
  
-   함수의 형식이 l\-value여야 합니다.  
  
-   함수가 반환할 때 참조 개체는 범위를 벗어나지 않습니다.  
  
 참조를 통해 큰 개체를 함수*로* 전달하는 것이 더 효율적일 수도 있고 참조를 통해 큰 개체를 함수*에서* 반환하는 것이 더 효율적일 수도 있습니다.  참조 반환 프로토콜을 사용하면 반환하기 전에 개체를 임시 위치로 복사할 필요가 없어집니다.  
  
 함수가 l\-value로 계산되어야 하는 경우에도 참조 반환 형식이 유용할 수 있습니다.  대부분의 오버로드된 연산자, 특히 할당 연산자가 이 범주에 속합니다.  오버로드된 연산자는 [오버로드된 연산자](../cpp/operator-overloading.md)에서 다룹니다.  
  
## 예제  
 `Point` 예제를 참조하세요.  
  
```  
// refType_function_returns.cpp  
// compile with: /EHsc  
  
#include <iostream>  
using namespace std;  
  
class Point  
{  
public:  
// Define "accessor" functions as  
//  reference types.  
unsigned& x();  
unsigned& y();  
private:  
// Note that these are declared at class scope:  
unsigned obj_x;   
unsigned obj_y;   
};  
  
unsigned& Point :: x()  
{  
return obj_x;  
}  
unsigned& Point :: y()  
{  
return obj_y;  
}  
  
int main()  
{  
Point ThePoint;  
// Use x() and y() as l-values.  
ThePoint.x() = 7;  
ThePoint.y() = 9;  
  
// Use x() and y() as r-values.  
cout << "x = " << ThePoint.x() << "\n"  
<< "y = " << ThePoint.y() << "\n";  
}  
```  
  
## 출력  
  
```  
x = 7  
y = 9  
```  
  
 `x` 및 `y` 함수가 참조 형식을 반환하는 것으로 선언된 것을 볼 수 있습니다.  대입 문의 양쪽에 이러한 함수를 사용할 수 있습니다.  
  
 또한, main에서 ThePoint 개체가 범위 내에 있으므로 해당 참조 멤버가 여전히 활성 상태이며 이 멤버에 안전하게 액세스할 수 있습니다.  
  
 참조 형식의 선언에는 다음 경우를 제외하고 이니셜라이저를 포함해야 합니다.  
  
-   명시적 `extern` 선언  
  
-   클래스 멤버의 선언  
  
-   클래스 내의 선언  
  
-   함수의 인수 또는 함수의 반환 형식 선언  
  
## 로컬의 주소 반환 시 주의 사항  
 로컬 범위에서 개체를 선언하는 경우 함수가 반환할 때 이 개체는 제거됩니다.  함수가 이 개체에 대한 참조를 반환하는 경우 호출자가 null 참조를 사용하려고 하면 해당 참조는 런타임에 액세스 위반을 일으킬 수 있습니다.  
  
```  
// C4172 means Don’t do this!!!  
Foo& GetFoo()  
{  
    Foo f;  
    ...  
    return f;  
} // f is destroyed here  
```  
  
 이 경우 컴파일러는 다음과 같은 경고를 발생시킵니다. `warning C4172: 지역 변수 또는 임시 변수의 주소를 반환하고 있습니다`.  간단한 프로그램에서는 메모리 위치를 덮어쓰기 전에 호출자가 참조에 액세스하는 경우 일반적으로 액세스 위반이 발생하지 않습니다.  이 경우는 순전히 운이 작용한 것입니다.  경고에 주의하세요.  
  
## 참고 항목  
 [참조](../cpp/references-cpp.md)