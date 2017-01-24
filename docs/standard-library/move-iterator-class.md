---
title: "move_iterator 클래스 | Microsoft Docs"
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
  - "std.move_iterator"
  - "move_iterator"
  - "iterator/std::move_iterator"
  - "std::move_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "move_iterator 클래스"
ms.assetid: a5e5cdd8-a264-4c6b-9f9c-68b0e8edaab7
caps.latest.revision: 20
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# move_iterator 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

클래스 템플릿 `move_iterator`는 반복기에 대한 래퍼입니다.  move\_iterator는 저장된 반복기의 역참조 연산자를 rvalue 참조로 전환하여 복사본을 이동으로 전환하는 것을 제외하고, 래핑\(저장\)하는 반복기와 동일한 동작을 제공합니다.  rvalue에 대한 자세한 내용은 [Rvalue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md)를 참조하십시오.  
  
## 구문  
  
```  
template<class Iterator>  
    class move_iterator {  
public:  
    typedef Iterator iterator_type;  
    typedef typename      
        iterator_traits<Iterator>::iterator_category  
            iterator_category;  
    typedef typename iterator_traits<Iterator>::value_type  
        value_type;  
    typedef typename iterator_traits<Iterator>::difference_type  
        difference_type;  
    typedef Iterator  
        pointer;  
    typedef value_type&&  
        reference;  
  
    move_iterator();  
    explicit move_iterator (Iterator right);  
    template<class Type>  
        move_iterator (const move_iterator<Type>& right);  
    template <class Type>   
        move_iterator& operator=(const move_iterator<Type>& right);  
  
    iterator_type base () const;  
    reference operator* () const;  
    pointer operator-> () const;  
  
    move_iterator& operator++ ();  
    move_iterator operator++ (int);  
    move_iterator& operator-- ();  
    move_iterator operator-- (int);  
  
    move_iterator& operator+= (difference_type off);  
    move_iterator operator+ (difference_type off) const;  
    move_iterator& operator-= (difference_type off);  
    move_iterator operator- (difference_type off) const;  
    reference operator[] (difference_type off) const;  
    };  
```  
  
## 설명  
 템플릿 클래스는 역참조된 경우를 제외하고 반복기와 유사하게 동작합니다.  멤버 함수 `base``()`로 액세스하는 임의 액세스 반복기 `Iterator`를 저장합니다.  `move_iterator`에 대한 모든 작업은 `operator*` 결과가 `value_type&&`으로 묵시적으로 캐스팅되어 rvalue 참조를 만드는 것을 제외하고, 저장된 반복기에서 직접 수행됩니다.  
  
 `move_iterator`는 래핑된 반복기에서 정의하지 않은 작업을 수행할 수 있습니다.  이러한 작업을 사용하지 마십시오.  
  
### 생성자  
  
|||  
|-|-|  
|[move\_iterator](../Topic/move_iterator::move_iterator.md)|`move_iterator` 형식의 개체에 대한 생성자.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[move\_iterator::iterator\_type](../Topic/move_iterator::iterator_type.md)|템플릿 매개 변수 `RandomIterator`의 동의어.|  
|[move\_iterator::iterator\_category](../Topic/move_iterator::iterator_category.md)|동일한 이름의 긴 `typename` 식에 대한 동의어. `iterator_category`는 반복기의 일반 기능을 식별합니다.|  
|[move\_iterator::value\_type](../Topic/move_iterator::value_type.md)|동일한 이름의 긴 `typename` 식에 대한 동의어. `value_type`은 반복기 요소의 형식에 대해 설명합니다.|  
|[move\_iterator::difference\_type](../Topic/move_iterator::difference_type.md)|동일한 이름의 긴 `typename` 식에 대한 동의어. `difference_type`은 요소 간 차이 값을 표시하는 데 필요합니다.|  
|[move\_iterator::pointer](../Topic/move_iterator::pointer.md)|템플릿 매개 변수 `RandomIterator`에 대한 동의어.|  
|[move\_iterator::reference](../Topic/move_iterator::reference.md)|`rvalue` 참조 `value_type&&`에 대한 동의어.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[move\_iterator::base](../Topic/move_iterator::base.md)|멤버 함수는 이 `move_iterator`에서 래핑한 저장된 반복기를 반환합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[move\_iterator::operator\*](../Topic/move_iterator::operator*.md)|`(reference)*` `base` `().`를 반환합니다.|  
|[move\_iterator::operator\+\+](../Topic/move_iterator::operator++.md)|저장된 반복기를 증가시킵니다.  정확한 동작은 사전 증가인지 또는 사후 증가인지에 따라 다릅니다.|  
|[move\_iterator::operator\-\-](../Topic/move_iterator::operator--.md)|저장된 반복기를 감소시킵니다.  정확한 동작은 사전 감소인지 또는 사후 감소인지에 따라 다릅니다.|  
|[move\_iterator::operator\-\>](../Topic/move_iterator::operator-%3E.md)|`&**this`를 반환합니다.|  
|[move\_iterator::operator\-](../Topic/move_iterator::operator-.md)|현재 위치에서 오른쪽 값을 차감하여 `move_iterator(*this) -=` 를 반환합니다.|  
|[move\_iterator::operator](../Topic/move_iterator::operator.md)|`(reference)*(*this + off)`를 반환합니다.  현재 기준에서 해당 위치의 값을 얻기 위한 오프셋을 지정할 수 있습니다.|  
|[move\_iterator::operator\+](../Topic/move_iterator::operator+.md)|`move_iterator(*this) +=`  값을 반환합니다.  기준에 오프셋을 추가하여 해당 위치의 값을 얻을 수 있습니다.|  
|[move\_iterator::operator\+\=](../Topic/move_iterator::operator+=.md)|저장된 반복기에 오른쪽 값을 더하고 `*this`를 반환합니다.|  
|[move\_iterator::operator\-\=](../Topic/move_iterator::operator-=.md)|저장된 반복기에서 오른쪽 값을 빼고 `*this`를 반환합니다.|  
  
## 요구 사항  
 **헤더:** \<iterator\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<iterator\>](../standard-library/iterator.md)   
 [Lvalue 및 Rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md)   
 [이동 생성자 및 이동 할당 연산자\(C\+\+\)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)