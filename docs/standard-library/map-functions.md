---
title: '&lt;map&gt; 함수 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- map/std::swap (map)
- map/std::swap (multimap)
ms.assetid: 7cb3d1a5-7add-4726-a73f-61927eafd466
ms.openlocfilehash: 3c6cb7d0308e4bafc531fe0baf0c5d666228c3ec
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966370"
---
# <a name="ltmapgt-functions"></a>&lt;map&gt; 함수

|||
|-|-|
|[swap(map)](#swap)|[swap (multimap)](#swap_multimap)|

## <a name="swap_multimap"></a>  swap  (map)

두 map의 요소를 교환합니다.

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    map<Key, Traits, Compare, Alloctor>& left,
    map<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽* 교환할 요소를 제공 하는 지도 또는 지도와 교환할 요소가 들어 있는 맵을 *왼쪽*합니다.

*왼쪽* 맵의 교환할 요소가 들어 있는 맵을 *오른쪽*합니다.

### <a name="remarks"></a>설명

템플릿 함수는 멤버 함수를 실행 하는 컨테이너 클래스 map에서 특수화 된 알고리즘 `left`.[ 스왑](../standard-library/map-class.md#swap)( `right`). 이 함수는 컴파일러에서 지정하는 함수 템플릿의 부분 순서 인스턴스입니다. 함수를 호출할 때 템플릿이 고유하게 일치하지 않는 방식으로 템플릿 함수가 오버로드되면 컴파일러는 템플릿 함수의 가장 특수화된 버전을 선택합니다. 알고리즘 클래스에서 템플릿 함수의 일반 버전인 **template** \< **class T**> **void swap**( **T&**, **T&**)는 할당을 기준으로 작동하며 속도가 느린 작업입니다. 각 컨테이너의 특수화된 버전은 컨테이너 클래스의 내부 표현을 사용할 수 있으므로 속도가 훨씬 빠릅니다.

### <a name="example"></a>예

`swap`의 템플릿 버전을 사용하는 예제는 멤버 함수 [map::swap](../standard-library/map-class.md#swap)에 대한 코드 예제를 참조하세요.

## <a name="swap"></a>  swap  (multimap)

두 multimap의 요소를 교환합니다.

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    multimap<Key, Traits, Compare, Alloctor>& left,
    multimap<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽* 교환할 요소를 제공 하는 multimap 또는 교환할 multimap의 요소입니다 multimap *왼쪽*합니다.

*왼쪽* 교환할 multimap의 요소입니다 multimap *오른쪽*합니다.

### <a name="remarks"></a>설명

템플릿 함수는 멤버 함수를 실행 하는 컨테이너 클래스 multimap에서를 실행 하는 컨테이너 클래스 map에서 특수화 된 알고리즘 `left`.[ 스왑](../standard-library/multimap-class.md#swap) (`right`). 이 함수는 컴파일러에서 지정하는 함수 템플릿의 부분 순서 인스턴스입니다. 함수를 호출할 때 템플릿이 고유하게 일치하지 않는 방식으로 템플릿 함수가 오버로드되면 컴파일러는 템플릿 함수의 가장 특수화된 버전을 선택합니다. 알고리즘 클래스에서 템플릿 함수의 일반 버전인 **template** \< **class T**> **void swap**( **T&**, **T&**)는 할당을 기준으로 작동하며 속도가 느린 작업입니다. 각 컨테이너의 특수화된 버전은 컨테이너 클래스의 내부 표현을 사용할 수 있으므로 속도가 훨씬 빠릅니다.

### <a name="example"></a>예

`swap`의 템플릿 버전을 사용하는 예제는 멤버 함수 [multimap::swap](../standard-library/multimap-class.md#swap)에 대한 코드 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[\<map>](../standard-library/map.md)<br/>
