---
title: "initializer_list Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 1f2c0ff4-5636-4f79-b008-e75426e3d2ab
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# initializer_list Class
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

각 멤버가 지정된 형식인 요소 배열에 대한 액세스를 제공합니다.  
  
## 구문  
  
```cpp  
template<  
    class Type >  
    class initializer_list  
```  
  
#### 매개 변수  
  
|매개 변수|설명|  
|-----------|--------|  
|`_Elem`|`initializer_list`에 저장되는 요소 데이터 형식입니다.|  
|`_First`|`initializer_list`의 첫 번째 요소에 대한 포인터입니다.|  
|`_Last`|`initializer_list`의 마지막 요소에 대한 포인터입니다.|  
  
## 설명  
 중괄호로 묶인 이니셜라이저 목록을 사용하여 `initializer_list`를 생성할 수 있습니다.  
  
```cpp  
initializer_list<int> i1{ 1, 2, 3, 4 };  
```  
  
 컴파일러는 함수 서명에 `initializer_list`가 필요할 때마다 같은 요소가 포함된 중괄호로 묶인 이니셜라이저 목록을 `initializer_list`로 변환합니다.  `initializer_list` 사용 방법에 대한 자세한 내용은 [균일 초기화 및 생성자 위임](../cpp/uniform-initialization-and-delegating-constructors.md)을 참조하세요.  
  
### 생성자  
  
|||  
|-|-|  
|[initializer\_list](../Topic/forward_list::forward_list.md)|`initializer_list` 형식의 개체를 생성합니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|value\_type|`initializer_list` 요소의 형식입니다.|  
|참조|`initializer_list`의 요소에 대한 참조를 제공하는 형식입니다.|  
|const\_reference|`initializer_list`의 요소에 대한 상수 참조를 제공하는 형식입니다.|  
|size\_type|`initializer_list`의 요소 수를 나타내는 형식입니다.|  
|iterator|`initializer_list`에 대한 반복기를 제공하는 형식입니다.|  
|const\_iterator|`initializer_list`에 대한 상수 반복기를 제공하는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[begin](../Topic/initializer_list::begin.md)|`initializer_list`의 첫 번째 요소에 대한 포인터를 반환합니다.|  
|[end](../Topic/initializer_list::end.md)|`initializer_list`의 마지막 요소를 지난 다음 요소에 대한 포인터를 반환합니다.|  
|[size](../Topic/initializer_list::size.md)|`initializer_list`에 있는 요소 수를 반환합니다.|  
  
## 요구 사항  
 **헤더:** \<initializer\_list\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<forward\_list\>](../standard-library/forward-list.md)