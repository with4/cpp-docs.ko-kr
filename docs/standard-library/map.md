---
title: '&lt;map&gt; | Microsoft 문서'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <map>
dev_langs:
- C++
helpviewer_keywords:
- map header
ms.assetid: bbf76680-7362-456e-88fa-ecda93561b6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac523342cc175721b9c1ef33a3d8ac4cad83033b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="ltmapgt"></a>&lt;map&gt;

컨테이너 템플릿 클래스 map 및 multimap과 지원 템플릿을 정의합니다.

## <a name="syntax"></a>구문

```cpp
#include <map>

```

## <a name="members"></a>멤버

### <a name="operators"></a>연산자

|map 버전|multimap 버전|설명|
|-----------------|----------------------|-----------------|
|[operator!= (map)](../standard-library/map-operators.md#op_neq)|[operator!= (multimap)](../standard-library/map-operators.md#op_neq)|연산자의 좌변에 있는 map 또는 multimap 개체가 우변에 있는 map 또는 multimap 개체와 같지 않은지 테스트합니다.|
|[operator< (map)](../standard-library/map-operators.md#op_eq_eq)|[operator< (multimap)](../standard-library/map-operators.md#op_eq_eq)|연산자의 좌변에 있는 map 또는 multimap 개체가 우변에 있는 map 또는 multimap 개체보다 작은지 테스트합니다.|
|[operator<= (map)](../standard-library/map-operators.md#op_lt)|[operator\<= (multimap)](../standard-library/map-operators.md#op_lt)|연산자의 좌변에 있는 map 또는 multimap 개체가 우변에 있는 map 또는 multimap 개체보다 작거나 같은지 테스트합니다.|
|[operator== (map)](../standard-library/map-operators.md#op_eq_eq)|[operator== (multimap)](../standard-library/map-operators.md#op_eq_eq_multimap)|연산자의 좌변에 있는 map 또는 multimap 개체가 우변에 있는 map 또는 multimap 개체와 같은지 테스트합니다.|
|[operator> (map)](../standard-library/map-operators.md#op_gt)|[operator> (multimap)](../standard-library/map-operators.md#op_gt_multimap)|연산자의 좌변에 있는 map 또는 multimap 개체가 우변에 있는 map 또는 multimap 개체보다 큰지 테스트합니다.|
|[operator>= (map)](../standard-library/map-operators.md#op_gt_eq)|[operator>= (multimap)](../standard-library/map-operators.md#op_gt_eq_multimap)|연산자의 좌변에 있는 map 또는 multimap 개체가 우변에 있는 map 또는 multimap 개체보다 크거나 같은지 테스트합니다.|

### <a name="specialized-template-functions"></a>특별 템플릿 함수

|map 버전|multimap 버전|설명|
|-----------------|----------------------|-----------------|
|[swap (map)](../standard-library/map-functions.md#swap)|[swap (multimap)](../standard-library/map-functions.md#swap_multimap)|두 map 또는 multimap의 요소를 교환합니다.|

### <a name="classes"></a>클래스

|클래스|설명|
|-|-|
|[value_compare 클래스](../standard-library/value-compare-class-map.md)|키 값 비교를 통해 맵의 요소를 비교하여 map 내의 상대 순서를 확인할 수 있는 함수 개체를 제공합니다.|
|[map 클래스](../standard-library/map-class.md)|각 요소에 데이터가 자동 정렬되는 기준인 고유한 키가 있는 컬렉션에서 데이터를 저장 및 검색하는 데 사용됩니다.|
|[multimap 클래스](../standard-library/multimap-class.md)|각 요소에 데이터가 자동 정렬되는 기준인 키가 있고 키 값이 고유하지 않아도 되는 컬렉션에서 데이터를 저장 및 검색하는 데 사용됩니다.|

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
