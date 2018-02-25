---
title: "&lt;hash_map&gt; | Microsoft 문서"
ms.custom: 
ms.date: 01/18/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <hash_map>
- std::<hash_map>
dev_langs:
- C++
helpviewer_keywords:
- hash_map header
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c50716912b42aace87b1132672331c86d9eae162
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="lthashmapgt"></a>&lt;hash_map&gt;

> [!NOTE]
> 이 헤더는 사용되지 않습니다. 대신 사용 하는 [ \<unordered_map >](unordered-map.md)합니다.

컨테이너 템플릿 클래스 hash_map 및 hash_multimap과 지원 템플릿을 정의합니다.

## <a name="syntax"></a>구문

> #<a name="include-hashmap"></a>include <hash_map>

### <a name="operators"></a>연산자

|Hash_map 버전|Hash_multimap 버전|설명|
|-----------------------|----------------------------|-----------------|
|[operator!=(hash_map)](hash-map-operators.md#op_neq)|[operator!=(hash_multimap)](hash-map-operators.md#op_neq_mm)|연산자의 좌변에 있는 hash_map 또는 hash_multimap 개체가 우변에 있는 hash_map 또는 hash_multimap 개체와 같지 않은지 테스트합니다.|
|[operator==(hash_map)](hash-map-operators.md#op_eq_eq)|[operator==(hash_multimap)](hash-map-operators.md#op_eq_eq_mm)|연산자의 좌변에 있는 hash_map 또는 hash_multimap 개체가 우변에 있는 hash_map 또는 hash_multimap 개체와 같은지 테스트합니다.|

### <a name="specialized-template-functions"></a>특별 템플릿 함수

|Hash_map 버전|Hash_multimap 버전|설명|
|-----------------------|----------------------------|-----------------|
|[swap(hash_map)](hash-map-class.md#swap)|[swap(hash_multimap)](hash-multimap-class.md#swap)|두 hash_map 또는 hash_multimap의 요소를 교환합니다.|

### <a name="classes"></a>클래스

|||
|-|-|
|[hash_compare 클래스](hash-compare-class.md)|해시 연관 컨테이너(hash_map, hash_multimap, hash_set 또는 hash_multiset) 중 하나에서 기본 **Traits** 매개 변수 개체로 사용하여 포함된 요소의 순서를 지정하고 해시할 수 있는 개체를 설명합니다.|
|[value_compare 클래스](value-compare-class.md)|키 값 비교를 통해 hash_map의 요소를 비교하여 hash_map 내의 상대 순서를 확인할 수 있는 함수 개체를 제공합니다.|
|[hash_map 클래스](hash-map-class.md)|각 요소가 값이 고유하고 연결된 데이터 값인 정렬 키가 있는 쌍인 컬렉션에서 데이터를 신속하게 저장하고 검색하는 데 사용됩니다.|
|[hash_multimap 클래스](hash-multimap-class.md)|각 요소가 값이 고유하고 연결된 데이터 값이 아니어도 되는 정렬 키가 있는 쌍인 컬렉션에서 데이터를 신속하게 저장하고 검색합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<hash_map>

**네임스페이스:** stdext

## <a name="see-also"></a>참고 항목

[헤더 파일 참조](cpp-standard-library-header-files.md)  
[C++ 표준 라이브러리의 스레드 보안](thread-safety-in-the-cpp-standard-library.md)  
[C++ 표준 라이브러리 참조](cpp-standard-library-reference.md)  
