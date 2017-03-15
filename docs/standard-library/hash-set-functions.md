---
title: "&lt;hash_set&gt; 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
caps.latest.revision: 7
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 1238f4a4e75f13ccd660554de8c49646549bc2cc
ms.lasthandoff: 02/24/2017

---
# <a name="lthashsetgt-functions"></a>&lt;hash_set&gt; 함수
|||  
|-|-|  
|[swap](#swap)|[swap(hash_multiset)](#swap__hash_multiset_)|  
  
##  <a name="a-nameswapa--swap"></a><a name="swap"></a>  swap  
  
> [!NOTE]
>  이 API는 더 이상 사용되지 않습니다. [unordered_set 클래스](../standard-library/unordered-set-class.md)를 대신 사용하는 것이 좋습니다.  
  
 두 hash_set의 요소를 교환합니다.  
  
```
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `right`  
 교환할 요소를 제공하는 hash_set 또는 hash_set `left`와 요소를 교환할 hash_set입니다.  
  
 `left`  
 hash_set `right`와 요소를 교환할 hash_set입니다.  
  
### <a name="remarks"></a>설명  
 `swap` 템플릿 함수는 멤버 함수 `left``.`[swap](../standard-library/hash-set-class.md#hash_set__swap)(`right`)을 실행하기 위해 컨테이너 클래스 hash_set에서 특수화된 알고리즘입니다. 이 함수는 컴파일러에서 지정하는 함수 템플릿의 부분 순서 인스턴스입니다. 함수를 호출할 때 템플릿이 고유하게 일치하지 않는 방식으로 템플릿 함수가 오버로드되면 컴파일러는 템플릿 함수의 가장 특수화된 버전을 선택합니다. 알고리즘 클래스 내 템플릿 함수의 일반 버전  
  
 **template \<class T> void swap(T&, T&),**  
  
 는 할당을 통해 작동하며 속도가 느린 작업입니다. 각 컨테이너의 특수화된 버전은 컨테이너 클래스의 내부 표현을 사용할 수 있으므로 속도가 훨씬 빠릅니다.  
  
 Visual C++ .NET 2003에서 [<hash_map>](../standard-library/hash-map.md) 및 [<hash_set>](../standard-library/hash-set.md) 헤더 파일의 멤버는 더 이상 std 네임스페이스에 있지 않으며 대신 stdext 네임스페이스로 이동되었습니다. 자세한 내용은 [stdext 네임스페이스](../standard-library/stdext-namespace.md)를 참조하세요.  
  
### <a name="example"></a>예제  
  `swap`의 템플릿 버전 사용 예제를 보려면 멤버 클래스 [hash_set::swap](../standard-library/hash-set-class.md#hash_set__swap)에 대한 코드 예제를 참조하세요.  
  
##  <a name="a-nameswaphashmultiseta--swap-hashmultiset"></a><a name="swap__hash_multiset_"></a>  swap(hash_multiset)  
  
> [!NOTE]
>  이 API는 더 이상 사용되지 않습니다. [unordered_set 클래스](../standard-library/unordered-set-class.md)를 대신 사용하는 것이 좋습니다.  
  
 두 hash_multiset의 요소를 교환합니다.  
  
```
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `right`  
 교환할 요소를 제공하는 hash_multiset 또는 hash_multiset과 요소를 교환할 hash_multiset `left`입니다.  
  
 `left`  
 hash_multiset `right`와 요소를 교환할 hash_multiset입니다.  
  
### <a name="remarks"></a>설명  
 `swap` 템플릿 함수는 멤버 함수 `left``.`[swap](../standard-library/hash-multiset-class.md#hash_multiset__swap)(`right`)을 실행하기 위해 컨테이너 클래스 hash_multiset에서 특수화된 알고리즘입니다. 이 함수는 컴파일러에서 지정하는 함수 템플릿의 부분 순서 인스턴스입니다. 함수를 호출할 때 템플릿이 고유하게 일치하지 않는 방식으로 템플릿 함수가 오버로드되면 컴파일러는 템플릿 함수의 가장 특수화된 버전을 선택합니다. 알고리즘 클래스 내 템플릿 함수의 일반 버전  
  
 **template \<class T> void swap(T&, T&),**  
  
 는 할당을 통해 작동하며 속도가 느린 작업입니다. 각 컨테이너의 특수화된 버전은 컨테이너 클래스의 내부 표현을 사용할 수 있으므로 속도가 훨씬 빠릅니다.  
  
 Visual C++ .NET 2003에서 [<hash_map>](../standard-library/hash-map.md) 및 [<hash_set>](../standard-library/hash-set.md) 헤더 파일의 멤버는 더 이상 std 네임스페이스에 있지 않으며 대신 stdext 네임스페이스로 이동되었습니다. 자세한 내용은 [stdext 네임스페이스](../standard-library/stdext-namespace.md)를 참조하세요.  
  
### <a name="example"></a>예제  
  `swap`의 템플릿 버전 사용 예제를 보려면 멤버 클래스 [hash_multiset::swap](../standard-library/hash-multiset-class.md#hash_multiset__swap)에 대한 코드 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [<hash_set>](../standard-library/hash-set.md)




