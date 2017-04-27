---
title: "&lt;hash_map&gt; 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- hash_map/std::swap
- hash_map/std::swap (hash_map)
ms.assetid: 28748cd0-71f7-41b9-b068-579183645fba
caps.latest.revision: 9
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 85c900f2263ae1c1089478badc85388e3b5e8548
ms.openlocfilehash: 6c11e1f90ce05aa3a4dc22ce31bed104ef0fa795
ms.lasthandoff: 02/24/2017

---
# <a name="lthashmapgt-functions"></a>&lt;hash_map&gt; 함수
|||  
|-|-|  
|[swap](#swap)|[swap(hash_map)](#swap__hash_map_)|  
  
##  <a name="swap__hash_map_"></a>  swap(hash_map)  
  
> [!NOTE]
>  이 API는 더 이상 사용되지 않습니다. [unordered_map 클래스](../standard-library/unordered-map-class.md)를 대신 사용하는 것이 좋습니다.  
  
 두 hash_map의 요소를 교환합니다.  
  
```
void swap(
    hash_map <Key, Type, Traits, Alloctor>& left,
    hash_map <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `right`  
 map `left`와 요소를 교환할 hash_map입니다.  
  
 `left`  
 map `right`와 요소를 교환할 hash_map입니다.  
  
### <a name="remarks"></a>설명  
 템플릿 함수는 멤버 함수 `left.`[swap](../standard-library/basic-ios-class.md#basic_ios__swap)*(right*)을 실행하기 위해 컨테이너 클래스 hash_map에서 특수화된 알고리즘입니다. 이 함수는 컴파일러에서 지정하는 함수 템플릿의 부분 순서 인스턴스입니다. 함수를 호출할 때 템플릿이 고유하게 일치하지 않는 방식으로 템플릿 함수가 오버로드되면 컴파일러는 템플릿 함수의 가장 특수화된 버전을 선택합니다. 알고리즘 헤더 파일에 있는 템플릿 함수의 일반 버전인 **template \<class T> void swap(T&, T&)**은 할당을 기준으로 작동하는 속도가 느린 작업입니다. 각 컨테이너의 특수화된 버전은 컨테이너 클래스의 내부 표현을 사용할 수 있으므로 속도가 훨씬 빠릅니다.  
  
 Visual C++ .NET 2003에서 [<hash_map>](../standard-library/hash-map.md) 및 [<hash_set>](../standard-library/hash-set.md) 헤더 파일의 멤버는 더 이상 std 네임스페이스에 있지 않으며 대신 stdext 네임스페이스로 이동되었습니다. 자세한 내용은 [stdext 네임스페이스](../standard-library/stdext-namespace.md)를 참조하세요.  
  
##  <a name="swap"></a>  swap  
  
> [!NOTE]
>  이 API는 더 이상 사용되지 않습니다. [unordered_multimap 클래스](../standard-library/unordered-multimap-class.md)를 대신 사용하는 것이 좋습니다.  
  
 두 hash_multimap의 요소를 교환합니다.  
  
```
void swap(
    hash_multimap <Key, Type, Traits, Alloctor>& left,
    hash_multimap <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `right`  
 map `left`와 요소를 교환할 hash_multimap입니다.  
  
 `left`  
 map `right`와 요소를 교환할 hash_multimap입니다.  
  
### <a name="remarks"></a>설명  
 템플릿 함수는 멤버 함수 `left.`[swap](../standard-library/hash-multimap-class.md#hash_multimap__swap)*(right*`)`을 실행하기 위해 컨테이너 클래스 hash_multimap에서 특수화된 알고리즘입니다. 이 함수는 컴파일러에서 지정하는 함수 템플릿의 부분 순서 인스턴스입니다. 함수를 호출할 때 템플릿이 고유하게 일치하지 않는 방식으로 템플릿 함수가 오버로드되면 컴파일러는 템플릿 함수의 가장 특수화된 버전을 선택합니다. 알고리즘 헤더 파일에 있는 템플릿 함수의 일반 버전인 **template \<class T> void swap(T&, T&)**은 할당을 기준으로 작동하는 속도가 느린 작업입니다. 각 컨테이너의 특수화된 버전은 컨테이너 클래스의 내부 표현을 사용할 수 있으므로 속도가 훨씬 빠릅니다.  
  
 Visual C++ .NET 2003에서 [<hash_map>](../standard-library/hash-map.md) 및 [<hash_set>](../standard-library/hash-set.md) 헤더 파일의 멤버는 더 이상 std 네임스페이스에 있지 않으며 대신 stdext 네임스페이스로 이동되었습니다. 자세한 내용은 [stdext 네임스페이스](../standard-library/stdext-namespace.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [<hash_map>](../standard-library/hash-map.md)




