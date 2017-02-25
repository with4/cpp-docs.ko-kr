---
title: "reverse_iterator 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "reverse_iterator"
  - "std::reverse_iterator"
  - "std.reverse_iterator"
  - "xutility/std::reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reverse_iterator 클래스"
ms.assetid: c0b34d04-ae9a-4999-9aff-28b313897ffa
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# reverse_iterator 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

템플릿 클래스는 임의 액세스, 양방향 반복기 또는 역방향으로만 동작하는 역방향 반복기 개체에 대해 설명하는 반복기 어댑터입니다.  범위를 뒤로 이동할 수 있습니다.  
  
## 구문  
  
```  
template <class RandomIterator>  
class reverse_iterator  
```  
  
#### 매개 변수  
 RandomIterator  
 반복기를 조정하여 역방향으로 작동할 수 있는 형식입니다.  
  
## 설명  
 기존 표준 템플릿 라이브러리에는 `reverse_iterator` 및 `const_reverse_iterator` 형식이 정의되어 있으며 역방향 반복기를 반환하는 멤버 함수 `rbegin` 및 `rend`이 있습니다.  이러한 반복기는 덮어쓰기 의미 체계가 있습니다.  `reverse_iterator` 어댑터는 이 기능을 제안 삽입 의미 체계로 보완하며 스트림과 함께 사용할 수 있습니다.  
  
 양방향 반복기가 필요한 `reverse_iterator`는 `operator+=`, `operator+`, `operator-=`, `operator-`, `operator[]` 멤버 함수 전부를 호출하지 않아야 합니다. 이러한 멤버 함수는 임의 액세스 반복기에서만 사용해야 합니다.  
  
 반복기의 범위가 \[`_First`, \_Last\)일 경우 왼쪽 대괄호는 \_*First*에서 포함함을 나타내고, 오른쪽의 괄호는 \_*Left*까지의 요소를 포함함을 나타내지만, \_*Left* 자체는 제외합니다.  동일한 요소가 역방향 시퀀스에 포함된 경우 \[**rev** – `_First`, **rev** – \_*Left*\), \_*Left*가 시퀀스에서 끝 요소 하나 다음에 있는 경우 역방향 시퀀스의 첫 번째 요소 **rev** – \_*First*는 \*\(\_*Left* – 1 \)을 가리킵니다.  모든 역방향 반복기를 기본 역방향과 연결하는 ID는 다음과 같습니다.  
  
 &\*\(**reverse\_iterator** \( *i* \) \) \=\= &\*\( *i* – 1 \).  
  
 실제로, 역방향 시퀀스에서 reverse\_iterator는 반복기가 원래 시퀀스에서 참조한 요소에서 하나 다음의\(오른쪽으로\) 요소를 참조함을 의미합니다.  따라서 반복기가 시퀀스\(2, 4, 6, 8\)에서 요소 6을 주소 지정한 경우 `reverse_iterator`는 역방향 시퀀스\(8, 6, 4, 2\)에서 요소 4를 주소 지정합니다.  
  
### 생성자  
  
|||  
|-|-|  
|[reverse\_iterator](../Topic/reverse_iterator::reverse_iterator.md)|기본 반복기에서 기본 `reverse_iterator` 또는 `reverse_iterator`를 생성합니다.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[difference\_type](../Topic/reverse_iterator::difference_type.md)|동일한 컨테이너 안에서 요소를 참조하는 두 `reverse_iterator` 사이의 차이를 제공하는 형식입니다.|  
|[iterator\_type](../Topic/reverse_iterator::iterator_type.md)|`reverse_iterator`의 기본 반복기를 제공하는 형식입니다.|  
|[포인터](../Topic/reverse_iterator::pointer.md)|`reverse_iterator`로 주소를 지정하는 요소에 포인터를 제공하는 형식입니다.|  
|[참조](../Topic/reverse_iterator::reference.md)|`reverse_iterator`로 주소를 지정하는 요소에 참조를 제공하는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[base](../Topic/reverse_iterator::base.md)|`reverse_iterator`에서 기본 반복기를 복구합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[operator\*](../Topic/reverse_iterator::operator*.md)|`reverse_iterator`가 주소 지정하는 요소를 반환합니다.|  
|[연산자\+](../Topic/reverse_iterator::operator+.md)|반복기에 오프셋을 추가하고 새 오프셋 위치에서 삽입된 요소를 주소 지정하는 새 `reverse_iterator`를 반환합니다.|  
|[operator\+\+](../Topic/reverse_iterator::operator++.md)|`reverse_iterator`를 다음 요소로 증가시킵니다.|  
|[연산자\+\=](../Topic/reverse_iterator::operator+=.md)|`reverse_iterator`에서 지정된 오프셋을 추가합니다.|  
|[연산자\-](../Topic/reverse_iterator::operator-.md)|`reverse_iterator`에서 오프셋을 차감하고 오프셋 위치에서 요소를 주소 지정하는 `reverse_iterator`를 반환합니다.|  
|[연산자\-\-](../Topic/reverse_iterator::operator--.md)|`reverse_iterator`를 이전 요소로 감소시킵니다.|  
|[연산자\-\=](../Topic/reverse_iterator::operator-=.md)|`reverse_iterator`에서 지정된 오프셋을 차감합니다.|  
|[연산자\-\>](../Topic/reverse_iterator::operator-%3E.md)|`reverse_iterator`에서 주소 지정하는 요소로 포인터를 반환합니다.|  
|[operator&#91;&#93;](../Topic/reverse_iterator::operator.md)|`reverse_iterator`에서 주소 지정하는 요소의 요소 오프셋으로 지정된 위치 수만큼 참조를 반환합니다.|  
  
## 요구 사항  
 **헤더:** \<iterator\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<iterator\>](../standard-library/iterator.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)