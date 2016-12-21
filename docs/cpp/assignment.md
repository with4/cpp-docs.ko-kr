---
title: "할당 | Microsoft Docs"
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
  - "대입 연산자, 오버로드"
  - "연산자[C++], 대입"
ms.assetid: d87e4f89-f8f5-42c1-9d3c-184bca9d0e15
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 할당
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

할당 연산자\(**\=**\)는 엄밀하게 말하면 이항 연산자입니다.  할당 연산자의 선언은 다음을 제외하고 다른 모든 이항 연산자와 동일합니다.  
  
-   비정적 멤버 함수여야 합니다.  `operator=`가 비멤버 함수로 선언될 수 없습니다.  
  
-   파생 클래스가 상속하지 않습니다.  
  
-   기본 `operator=` 함수가 클래스 형식에 대해 컴파일러에서 생성될 수 있습니다\(없는 경우\). 기본 `operator=` 함수에 대한 자세한 내용은 [멤버 단위 할당 및 초기화](http://msdn.microsoft.com/ko-kr/94048213-8b49-4416-8069-b1b7a6f271f9)를 참조하십시오.  
  
 다음 예제에서는 할당 연산자를 선언하는 방법을 보여 줍니다.  
  
```  
// assignment.cpp  
class Point  
{  
public:  
   Point &operator=( Point & );  // Right side is the argument.  
   int _x, _y;  
};  
  
// Define assignment operator.  
Point &Point::operator=( Point &ptRHS )  
{  
   _x = ptRHS._x;  
   _y = ptRHS._y;  
  
   return *this;  // Assignment operator returns left side.  
}  
  
int main()  
{  
}  
```  
  
 제공된 인수는 식의 오른쪽입니다.  연산자는 개체를 반환하여 할당 연산자의 동작을 보존하고, 할당 연산자는 할당이 완료된 후 왼쪽의 값을 반환합니다.  이에 따라 다음과 같은 문을 작성할 수 있습니다.  
  
```  
pt1 = pt2 = pt3;  
```  
  
## 참고 항목  
 [연산자 오버로드](../cpp/operator-overloading.md)