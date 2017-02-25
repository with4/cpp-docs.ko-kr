---
title: "array 클래스(STL) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "array/std::tr1::array"
  - "std.tr1.array"
  - "array"
  - "std::tr1::array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array 클래스[TR1]"
ms.assetid: fdfd43a5-b2b5-4b9e-991f-93bf10fb4293
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# array 클래스(STL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

길이가 `N`인 `Ty` 형식의 요소 시퀀스를 제어하는 개체를 설명합니다.  시퀀스는 `array<Ty, N>` 개체에 포함된 `Ty`의 배열로 저장됩니다.  
  
## 구문  
  
```  
template<class Ty, std::size_t N>  
    class array;  
```  
  
#### 매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|`Ty`|요소의 형식입니다.|  
|`N`|요소의 수입니다.|  
  
## 멤버  
  
|||  
|-|-|  
|형식 정의|설명|  
|[array::const\_iterator](../Topic/array::const_iterator.md)|제어되는 시퀀스에 대한 상수 반복기의 형식입니다.|  
|[array::const\_pointer](../Topic/array::const_pointer.md)|요소에 대한 상수 포인터의 형식입니다.|  
|[array::const\_reference](../Topic/array::const_reference.md)|요소에 대한 상수 참조의 형식입니다.|  
|[array::const\_reverse\_iterator](../Topic/array::const_reverse_iterator.md)|제어되는 시퀀스에 대한 상수 역방향 반복기의 형식입니다.|  
|[array::difference\_type](../Topic/array::difference_type.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[array::iterator](../Topic/array::iterator.md)|제어되는 시퀀스에 대한 반복기의 형식입니다.|  
|[array::pointer](../Topic/array::pointer.md)|요소에 대한 포인터의 형식입니다.|  
|[array::reference](../Topic/array::reference.md)|요소에 대한 참조의 형식입니다.|  
|[array::reverse\_iterator](../Topic/array::reverse_iterator.md)|제어되는 시퀀스에 대한 반대 반복기의 형식입니다.|  
|[array::size\_type](../Topic/array::size_type.md)|두 요소 사이의 부호가 없는 거리의 형식입니다.|  
|[array::value\_type](../Topic/array::value_type.md)|요소의 형식입니다.|  
  
|||  
|-|-|  
|멤버 함수|설명|  
|[array::array](../Topic/array::array.md)|배열 개체를 생성합니다.|  
|[array::assign](../Topic/array::assign.md)|모든 요소를 바꿉니다.|  
|[array::at](../Topic/array::at.md)|지정된 위치에 있는 요소에 액세스합니다.|  
|[array::back](../Topic/array::back.md)|마지막 요소에 액세스합니다.|  
|[array::begin](../Topic/array::begin.md)|제어되는 시퀀스의 시작을 지정합니다.|  
|[array::cbegin](../Topic/array::cbegin.md)|배열의 첫 번째 요소에 대한 임의 액세스 const 반복기를 반환합니다.|  
|[array::cend](../Topic/array::cend.md)|배열 끝의 바로 다음을 가리키는 임의 액세스 const 반복기를 반환합니다.|  
|[array::crbegin](../Topic/array::crbegin.md)|역방향 배열의 첫 번째 요소에 대해 const 반복기를 반환합니다.|  
|[array::crend](../Topic/array::crend.md)|역방향 배열 끝에 대해 const 반복기를 반환합니다.|  
|[array::data](../Topic/array::data.md)|첫 번째 요소의 주소를 가져옵니다.|  
|[array::empty](../Topic/array::empty.md)|요소가 있는지 테스트합니다.|  
|[array::end](../Topic/array::end.md)|제어되는 시퀀스의 끝을 지정합니다.|  
|[array::fill](../Topic/array::fill.md)|지정된 값을 가진 모든 요소를 바꿉니다.|  
|[array::front](../Topic/array::front.md)|첫 번째 요소에 액세스합니다.|  
|[array::max\_size](../Topic/array::max_size.md)|요소의 수를 셉니다.|  
|[array::rbegin](../Topic/array::rbegin.md)|제어되는 역방향 시퀀스의 시작을 지정합니다.|  
|[array::rend](../Topic/array::rend.md)|제어되는 역방향 시퀀스의 끝을 지정합니다.|  
|[array::size](../Topic/array::size.md)|요소의 수를 셉니다.|  
|[array::swap](../Topic/array::swap.md)|두 컨테이너의 내용을 바꿉니다.|  
  
|||  
|-|-|  
|연산자|설명|  
|[array::operator\=](../Topic/array::operator=.md)|제어되는 시퀀스를 바꿉니다.|  
|[array::operator](../Topic/array::operator.md)|지정된 위치에 있는 요소에 액세스합니다.|  
  
## 설명  
 형식에 기본 생성자 `array()`와 기본 대입 연산자 `operator=`가 있고 `aggregate`에 대한 요구 사항을 충족합니다.  따라서 집계 이니셜라이저를 사용하여 `array<Ty, N>` 형식의 개체를 초기화할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
array<int, 4> ai = { 1, 2, 3 };  
```  
  
 4개의 정수 값을 보유하는 `ai` 개체를 만들고, 처음 세 개의 요소를 값 1, 2, 3으로 각각 초기화한 다음 네 번째 요소를 0으로 초기화합니다.  
  
## 요구 사항  
 **헤더:** \<array\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<array\>](../standard-library/array.md)