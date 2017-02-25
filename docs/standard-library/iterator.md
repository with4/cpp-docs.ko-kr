---
title: "&lt;iterator&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::<iterator>"
  - "std.<iterator>"
  - "<iterator>"
  - "iterator/std::<iterator>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iterator 헤더"
ms.assetid: c61a3962-f3ed-411a-b5a3-e8b3c2b500bd
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# &lt;iterator&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

반복기 기본형, 미리 정의된 반복기, 스트림 반복기뿐만 아니라 여러 가지 지원 템플릿을 정의합니다.  미리 정의된 반복기는 삽입 및 반전 어댑터를 포함합니다.  삽입 반복기 어댑터: 앞, 뒤 및 일반의 세 가지 클래스가 있습니다.  컨테이너 멤버 함수 반복기가 제공하는 덮어쓰기 의미 체계보다 삽입 의미 체계를 제공합니다.  
  
## 구문  
  
```  
  
#include <iterator>  
  
```  
  
## 설명  
 반복기는 C\+\+ 프로그램에서 다른 데이터 구조가 동일한 방식으로 작동하도록 하여 포인터의 일반화, 요구 사항의 추상화를 구현합니다.  반복기는 컨테이너와 일반 알고리즘 사이에서 중개자 역할을 합니다.  알고리즘은 특정 데이터 형식에서 작동하는 대신, 반복기의 형식으로 지정된 범위에서 작동하도록 정의됩니다.  그런 다음 반복기의 요구 사항을 충족하는 모든 데이터 구조는 알고리즘에 의해 운영될 수 있습니다.  반복기의 범주는 5가지이며, 각각 고유한 요구 사항과 결과적 기능이 있습니다.  
  
-   출력: 앞으로 나아가는 것. ostream 및 inserter가 제공한 가치를 보관할 수 있지만 검색할 수는 없습니다.  
  
-   입력: 앞으로 나아가는 것. istream에서 제공한 가치를 검색할 수 있지만 보관할 수는 없습니다.  
  
-   정방향: 앞으로 나아가는 것. 가치를 보관하고 검색할 수 있습니다.  
  
-   양방향: 앞으로 나아가고 뒤로 이동하는 것. list, set, multiset, map, multimap에서 제공한 가치를 보관하고 검색할 수 있습니다.  
  
-   임의 액세스: 임의 순서로 액세스하는 요소. vector, deque, string, array에서 제공한 가치를 보관하고 검색할 수 있습니다.  
  
 요구 사항이 더 적은 반복기 대신 요구 사항이 더 많고 요소에 더 강력하게 액세스할 수 있는 반복기를 사용할 수 있습니다.  예를 들어, 정방향 반복기가 호출되면, 대신 임의 액세스 반복기를 사용할 수 있습니다.  
  
 Visual Studio는 확인 및 확인되지 않은 반복기에 대한 다양한 디버그 모드 상황을 지원하기 위해 C\+\+ 표준 라이브러리 반복기에 대한 확장을 추가했습니다.  자세한 내용은 [안전한 라이브러리: C\+\+ 표준 라이브러리](../standard-library/safe-libraries-cpp-standard-library.md)을 참조하십시오.  
  
### 함수  
  
|||  
|-|-|  
|[advance](../Topic/advance.md)|지정된 위치 수만큼 반복기를 증가시킵니다.|  
|[back\_inserter](../Topic/back_inserter.md)|지정된 컨테이너 뒤에 요소를 삽입할 수 있는 반복기를 만듭니다.|  
|[begin](../Topic/begin.md)|지정된 컨테이너의 첫 번째 요소에 대한 반복기를 검색합니다.|  
|[cbegin](../Topic/cbegin.md)|지정된 컨테이너의 첫 번째 요소에 대한 상수 반복기를 검색합니다.|  
|[cend](../Topic/cend.md)|지정된 컨테이너에서 마지막 요소 다음에 있는 요소에 대한 상수 반복기를 검색합니다.|  
|[distance](../Topic/distance.md)|두 반복기에 의해 주소가 지정된 위치 사이의 간격의 수를 결정합니다.|  
|[end](../Topic/end.md)|지정된 컨테이너에서 마지막 요소 다음의 요소에 대한 반복기를 검색합니다.|  
|[front\_inserter](../Topic/front_inserter.md)|지정된 컨테이너 앞에 요소를 삽입할 수 있는 반복기를 만듭니다.|  
|[inserter](../Topic/inserter.md)|지정된 삽입 지점에서 컨테이너에 새 요소를 추가하는 반복기 어댑터입니다.|  
|[make\_checked\_array\_iterator](../Topic/make_checked_array_iterator.md)|알고리즘에서 사용할 수 있는 [checked\_array\_iterator](../standard-library/checked-array-iterator-class.md)를 만듭니다. **Note:**  이 함수는 표준 C\+\+ 라이브러리의 Microsoft 확장입니다.  이 함수를 사용하여 구현한 코드는 이 Microsoft 확장을 지원하지 않는 C\+\+ 표준 빌드 환경으로 이식할 수 없습니다.|  
|[make\_move\_iterator](../Topic/make_move_iterator.md)|제공된 반복기를 포함하는 이동 반복기를 저장된 기준 반복기로 반환합니다.|  
|[make\_unchecked\_array\_iterator](../Topic/make_unchecked_array_iterator.md)|알고리즘에서 사용할 수 있는 [unchecked\_array\_iterator](../standard-library/unchecked-array-iterator-class.md)를 만듭니다. **Note:**  이 함수는 표준 C\+\+ 라이브러리의 Microsoft 확장입니다.  이 함수를 사용하여 구현한 코드는 이 Microsoft 확장을 지원하지 않는 C\+\+ 표준 빌드 환경으로 이식할 수 없습니다.|  
|[next](../Topic/next.md)|지정된 횟수만큼 반복하고 새 반복기 위치를 반환합니다.|  
|[prev](../Topic/prev.md)|역순으로 지정된 횟수만큼 반복하고 새 반복기 위치를 반환합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[연산자\!\=](../Topic/operator!=%20\(%3Citerator%3E\).md)|연산자의 좌변에 있는 반복기 개체가 우변에 있는 반복기 개체와 다른지를 테스트합니다.|  
|[연산자\=\=](../Topic/operator==%20\(%3Citerator%3E\).md)|연산자의 좌변에 있는 반복기 개체가 우변에 있는 반복기 개체와 같은지를 테스트합니다.|  
|[연산자 \<](../Topic/operator%3C%20\(%3Citerator%3E\).md)|연산자의 좌변에 있는 반복기 개체가 우변에 있는 반복기 개체보다 작은지를 테스트합니다.|  
|[연산자\<\=](../Topic/operator%3C=%20\(%3Citerator%3E\).md)|연산자의 좌변에 있는 반복기 개체가 우변에 있는 반복기 개체보다 작거나 같은지를 테스트합니다.|  
|[연산자 \>](../Topic/operator%3E%20\(%3Citerator%3E\).md)|연산자의 좌변에 있는 반복기 개체가 우변에 있는 반복기 개체보다 큰지를 테스트합니다.|  
|[연산자\>\=](../Topic/operator%3E=%20\(%3Citerator%3E\).md)|연산자의 좌변에 있는 반복기 개체가 우변에 있는 반복기 개체보다 크거나 같은지를 테스트합니다.|  
|[연산자\+](../Topic/operator+%20\(%3Citerator%3E\).md)|반복기에 오프셋을 추가하고 새 오프셋 위치에서 삽입된 요소를 주소 지정하는 새 `reverse_iterator`를 반환합니다.|  
|[연산자\-](../Topic/operator-%20\(%3Citerator%3E\).md)|다른 반복기에서 하나의 반복기를 빼고 차이를 반환합니다.|  
  
### 클래스  
  
|||  
|-|-|  
|[back\_insert\_iterator](../standard-library/back-insert-iterator-class.md)|출력 반복기 개체를 설명하는 템플릿 클래스입니다.  여기에 저장하는 컨테이너이기도 한, 보호된 **pointer** 개체를 통해 액세스하는 **Container** 형식의 컨테이너에 요소를 삽입합니다.|  
|[bidirectional\_iterator\_tag](../standard-library/bidirectional-iterator-tag-struct.md)|양방향 반복기를 나타내는 **iterator category** 함수에 반환 형식을 제공하는 클래스입니다.|  
|[checked\_array\_iterator](../standard-library/checked-array-iterator-class.md)|확인된 반복기인 임의 액세스를 사용하는 배열에 액세스하는 클래스입니다. **Note:**  이 클래스는 표준 C\+\+ 라이브러리의 Microsoft 확장입니다.  이 함수를 사용하여 구현한 코드는 이 Microsoft 확장을 지원하지 않는 C\+\+ 표준 빌드 환경으로 이식할 수 없습니다.|  
|[forward\_iterator\_tag](../standard-library/forward-iterator-tag-struct.md)|정방향 반복기를 나타내는 **iterator category** 함수에 반환 형식을 제공하는 클래스입니다.|  
|[front\_insert\_iterator](../standard-library/front-insert-iterator-class.md)|출력 반복기 개체를 설명하는 템플릿 클래스입니다.  여기에 저장하는 컨테이너이기도 한, 보호된 **pointer** 개체를 통해 액세스하는 **Container** 형식의 컨테이너에 요소를 삽입합니다.|  
|[input\_iterator\_tag](../standard-library/input-iterator-tag-struct.md)|입력 반복기를 나타내는 **iterator category** 함수에 반환 형식을 제공하는 클래스입니다.|  
|[insert\_iterator](../standard-library/insert-iterator-class.md)|출력 반복기 개체를 설명하는 템플릿 클래스입니다.  여기에 저장하는 컨테이너이기도 한, 보호된 **pointer** 개체를 통해 액세스하는 **Container** 형식의 컨테이너에 요소를 삽입합니다.  다음 **iter**라고 하는 **Container::iterator**클래스의 보호된 **iterator**를 저장합니다.|  
|[istream\_iterator](../standard-library/istream-iterator-class.md)|입력 반복기 개체를 설명하는 템플릿 클래스입니다.  여기에 저장하는 `basic_istream`\<**Elem**, **Tr**\>의 포인터 형식이기도 한, 개체를 통해 액세스하는 입력 스트림에서 **Ty**의 개체를 추출합니다.|  
|[istreambuf\_iterator](../standard-library/istreambuf-iterator-class.md)|입력 반복기 개체를 설명하는 템플릿 클래스입니다.  형식 **pointer**를 `basic_streambuf`\<**Elem**, **Tr**\>에 저장하는 개체를 통해 액세스하는 출력 스트림 버퍼에 **Elem** 클래스의 요소를 삽입합니다.|  
|[iterator](../standard-library/iterator-struct.md)|템플릿 클래스는 모든 반복기에 대해 기본 형식으로 사용됩니다.|  
|[iterator\_traits](../standard-library/iterator-traits-struct.md)|다른 반복기 형식과 관련이 되어 같은 방식으로 참조되는 중요한 형식을 제공하는 템플릿 도우미 클래스입니다.|  
|[move\_iterator](../standard-library/move-iterator-class.md)|다음 `move_iterator` 개체는 `RandomIterator` 형식의 임의 액세스 반복기를 저장합니다.  역참조 되는 경우를 제외하고 임의 액세스 반복기처럼 동작합니다.  다음 `operator*` 결과는 `rvalue reference`을 만들기 위해 암시적으로 `value_type&&:`로 캐스팅됩니다.|  
|[ostream\_iterator](../standard-library/ostream-iterator-class.md)|출력 반복기 개체를 설명하는 템플릿 클래스입니다.  형식 **포인터**를 `basic_ostream`\<**Elem**, **Tr**\>에 저장하는 개체를 통해 액세스하는 출력 스트림에 **형식** 클래스의 개체를 삽입합니다.|  
|[ostreambuf\_iterator 클래스](../standard-library/ostreambuf-iterator-class.md)|출력 반복기 개체를 설명하는 템플릿 클래스입니다.  형식 포인터를 `basic_streambuf`\<**Elem**, **Tr**\>에 저장하는 개체를 통해 액세스하는 출력 스트림 버퍼에 **Elem** 클래스의 요소를 삽입합니다.|  
|[output\_iterator\_tag](../standard-library/output-iterator-tag-struct.md)|출력 반복기를 나타내는 **iterator category** 함수에 반환 형식을 제공하는 클래스입니다.|  
|[random\_access\_iterator\_tag](../standard-library/random-access-iterator-tag-struct.md)|임의 액세스 반복기를 나타내는 **iterator category** 함수에 반환 형식을 제공하는 클래스입니다.|  
|[reverse\_iterator](../standard-library/reverse-iterator-class.md)|반대 방향에서만 임의 액세스 반복기처럼 동작하는 개체를 설명하는 템플릿 클래스입니다.|  
|[unchecked\_array\_iterator](../standard-library/unchecked-array-iterator-class.md)|확인되지 않은 반복기인 임의 액세스를 사용하는 배열에 액세스하는 클래스입니다. **Note:**  이 클래스는 표준 C\+\+ 라이브러리의 Microsoft 확장입니다.  이 함수를 사용하여 구현한 코드는 이 Microsoft 확장을 지원하지 않는 C\+\+ 표준 빌드 환경으로 이식할 수 없습니다.|  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)