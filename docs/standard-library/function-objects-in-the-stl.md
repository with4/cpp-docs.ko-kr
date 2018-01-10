---
title: "C++ 표준 라이브러리의 함수 개체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- functors
- C++ Standard Library, functors
- C++ Standard Library, function objects
- function objects
ms.assetid: 85f8a735-2c7b-4f10-9c4d-95c666ec4192
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2ba5024590a0682f8d65c7d21ca2cb15d2f481b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="function-objects-in-the-c-standard-library"></a>C++ 표준 라이브러리의 함수 개체
*함수 개체*또는 *함수*는 operator()를 구현하는 형식입니다. 이 연산자는 *호출 연산자* 또는 경우에 따라 *응용 프로그램 연산자*라고 합니다. C++ 표준 라이브러리는 기본적으로 함수 개체를 컨테이너의 정렬 기준 및 알고리즘에서 사용합니다.  
  
 함수 개체는 직접적인 함수 호출에 비해 두 가지 주요 장점을 제공합니다. 첫 번째는 함수 개체에 상태를 포함할 수 있다는 점입니다. 두 번째는 함수 개체가 형식이므로 템플릿 매개 변수로 사용할 수 있다는 점입니다.  
  
## <a name="creating-a-function-object"></a>함수 개체 만들기  
 함수 개체를 만들려면 다음과 같이 형식을 만들고 operator()를 구현합니다.  
  
```
class Functor  
{  
public:  
    int operator()(int a, int b)  
    {  
        return a < b;  
    }  
};  
```

 `main` 함수의 마지막 줄은 함수 개체를 호출하는 방법을 보여 줍니다. 이 호출은 함수 호출처럼 보이지만 실제로 Functor 형식의 operator()를 호출하고 있습니다. 함수 개체 호출과 함수의 이러한 유사성은 함수 개체라는 용어가 나타난 방식입니다.  
  
## <a name="function-objects-and-containers"></a>함수 개체 및 컨테이너  
 C++ 표준 라이브러리는 [\<functional>](../standard-library/functional.md) 헤더 파일에 여러 가지 함수 개체를 포함합니다. 이러한 함수 개체의 용도 중 하나는 컨테이너의 정렬 기준입니다. 예를 들어 `set` 컨테이너는 다음과 같이 선언됩니다.  
  
```  
template <class Key,  
    class Traits=less<Key>,  
    class Allocator=allocator<Key>>  
class set  
```  
  
 두 번째 템플릿 인수는 함수 개체 `less`입니다. 이 함수 개체는 전달된 첫 번째 매개 변수가 전달된 두 번째 매개 변수보다 작은 경우 `true` 를 반환합니다. 일부 컨테이너는 해당 요소를 정렬하므로 두 요소를 비교하는 방법이 필요하며 함수 개체를 사용하여 이를 수행합니다. 함수 개체를 만들고 컨테이너에 대한 템플릿 목록에서 지정하여 컨테이너의 고유한 정렬 기준을 정의할 수 있습니다.  
  
## <a name="function-objects-and-algorithms"></a>함수 개체 및 알고리즘  
 함수 개체의 또 다른 용도는 알고리즘입니다. 예를 들어 `remove_if` 알고리즘은 다음과 같이 선언됩니다.  
  
```  
template <class ForwardIterator, class Predicate>  
ForwardIterator remove_if(
    ForwardIterator first,  
    ForwardIterator last,  
    Predicate pred);
```  
  
 `remove_if` 에 대한 마지막 인수는 부울 값을 반환하는 개체 함수( *predicate*)입니다. 함수 개체의 결과가 `true`인 경우 반복기 `first` 및 `last`가 액세스하고 있는 컨테이너에서 요소가 제거됩니다. 인수 `pred`에 대한 [\<functional>](../standard-library/functional.md) 헤더에 선언된 함수 개체를 사용하거나 직접 만들 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)

