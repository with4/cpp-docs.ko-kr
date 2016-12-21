---
title: "reinterpret_cast 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "reinterpret_cast"
  - "reinterpret_cast_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reinterpret_cast 키워드[C++]"
ms.assetid: eb3283c7-7f88-467e-affd-407d37b46d6c
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# reinterpret_cast 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

포인터가 다른 포인터 형식으로 변환될 수 있도록 합니다.  또한 정수 계열 형식이 포인터 형식으로 변환될 수 있도록 하고 그 반대로도 변환될 수 있도록 합니다.  
  
## 구문  
  
```  
reinterpret_cast < type-id > ( expression )  
```  
  
## 설명  
 `reinterpret_cast` 연산자를 잘못 사용하면 쉽게 위험해질 수 있습니다.  원하는 변환이 본질적으로 낮은 수준이 아닌 한 다른 캐스트 연산자 중 하나를 사용해야 합니다.  
  
 `reinterpret_cast` 연산자는 `char*`에서 `int*`로의 변환이나 `One_class*`에서 `Unrelated_class*`로의 변환에 사용할 수 있습니다. 이러한 변환은 본질적으로 안전하지 않습니다.  
  
 `reinterpret_cast`의 결과는 원래 형식으로 다시 캐스팅되는 것 이외의 용도로 안전하게 사용할 수 없습니다.  다른 용도로 사용하는 경우에는 기껏해야 이식할 수 없는 결과가 생성됩니다.  
  
 `reinterpret_cast` 연산자는 **const**, `volatile` 또는 **\_\_unaligned** 특성을 캐스팅할 수 없습니다.  이러한 특성을 제거하는 방법에 대한 자세한 내용은 [const\_cast 연산자](../cpp/const-cast-operator.md)를 참조하십시오.  
  
 `reinterpret_cast` 연산자는 null 포인터 값을 대상 형식의 null 포인터 값으로 변환합니다.  
  
 두 고유 값이 동일한 인덱스가 되기 드문 방식으로 값을 인덱스에 매핑하는 해시 함수에서 `reinterpret_cast`를 유용하게 사용할 수 있습니다.  
  
```  
#include <iostream>  
using namespace std;  
  
// Returns a hash code based on an address  
unsigned short Hash( void *p ) {  
   unsigned int val = reinterpret_cast<unsigned int>( p );  
   return ( unsigned short )( val ^ (val >> 16));  
}  
  
using namespace std;  
int main() {  
   int a[20];  
   for ( int i = 0; i < 20; i++ )  
      cout << Hash( a + i ) << endl;  
}  
  
Output:   
64641  
64645  
64889  
64893  
64881  
64885  
64873  
64877  
64865  
64869  
64857  
64861  
64849  
64853  
64841  
64845  
64833  
64837  
64825  
64829  
```  
  
 `reinterpret_cast`를 통해 포인터를 정수 계열 형식으로 취급할 수 있습니다.  결과는 비트 이동되고 자신과 XOR 연산이 수행되어 고유한 인덱스\(높은 확률로 고유함\)를 생성합니다.  이 인덱스는 표준 C 스타일 캐스트를 통해 함수의 반환 형식으로 잘립니다.  
  
## 참고 항목  
 [캐스팅 연산자](../cpp/casting-operators.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)