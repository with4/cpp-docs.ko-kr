---
title: '&lt;forward_list&gt; 함수 | Microsoft 문서'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
ms.openlocfilehash: 097dca5d26014696e218ff6439b81e1d0349b2c5
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966321"
---
# <a name="ltforwardlistgt-functions"></a>&lt;forward_list&gt; 함수

||
|-|
|[swap](#swap)|

## <a name="swap"></a>  swap

두 정방향 목록의 요소를 교환합니다.

```cpp
void swap(
    forward_list <Type, Allocator>& left,
    forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*left*|`forward_list` 형식의 개체입니다.|
|*right*|`forward_list` 형식의 개체입니다.|

### <a name="remarks"></a>설명

이 템플릿 함수는 `left.swap(right)`를 실행합니다.

## <a name="see-also"></a>참고자료

[<forward_list>](../standard-library/forward-list.md)<br/>
