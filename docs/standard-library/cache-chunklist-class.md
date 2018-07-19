---
title: cache_chunklist 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::cache_chunklist
- allocators/stdext::cache_chunklist::allocate
- allocators/stdext::cache_chunklist::deallocate
dev_langs:
- C++
helpviewer_keywords:
- stdext::cache_chunklist
- stdext::cache_chunklist [C++], allocate
- stdext::cache_chunklist [C++], deallocate
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 808340df89bb548fee57604f25409c117933cc4e
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953262"
---
# <a name="cachechunklist-class"></a>cache_chunklist 클래스

단일 크기의 메모리 블록을 할당하고 할당 취소하는 [블록 할당자](../standard-library/allocators-header.md)를 정의합니다.

## <a name="syntax"></a>구문

```cpp
template <std::size_t Sz, std::size_t Nelts = 20>
class cache_chunklist
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*sz*|할당할 배열의 요소 수입니다.|

## <a name="remarks"></a>설명

이 템플릿 클래스를 사용 하 여 **new 연산자** 원시 메모리의 청크를 할당 하려면 필요한 경우 메모리 블록에 대 한 저장소를 할당할 블록 고; 각 청크에 대 한 별도 사용 가능한 목록에서 할당 취소 된 메모리 블록을 저장 하 고 를사용하여**delete 연산자** 사용 중인 메모리 블록이 없는 경우 청크를 할당 취소 합니다.

각 메모리 블록 보유 *Sz* 바이트의 사용 가능한 메모리 및 속해 있는 청크에 대 한 포인터입니다. 각 청크를 보유 `Nelts` 메모리 블록, 세 가지 포인터, int 및 데이터는 **new 연산자** 하 고 **delete 연산자** 필요 합니다.

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[cache_chunklist](#cache_chunklist)|`cache_chunklist` 형식의 개체를 생성합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[allocate](#allocate)|메모리 블록을 할당합니다.|
|[deallocate](#deallocate)|지정된 위치부터 시작하여 저장소에서 지정된 개수의 개체를 해제합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="allocate"></a>  cache_chunklist::allocate

메모리 블록을 할당합니다.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*count*|할당할 배열의 요소 수입니다.|

### <a name="return-value"></a>반환 값

할당된 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="cache_chunklist"></a>  cache_chunklist::cache_chunklist

`cache_chunklist` 형식의 개체를 생성합니다.

```cpp
cache_chunklist();
```

### <a name="remarks"></a>설명

## <a name="deallocate"></a>  cache_chunklist::deallocate

지정된 위치부터 시작하여 저장소에서 지정된 개수의 개체를 해제합니다.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*ptr*|저장소에서 할당을 취소할 첫 번째 개체에 대한 포인터입니다.|
|*count*|저장소에서 할당을 취소할 개체의 수입니다.|

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[\<allocators>](../standard-library/allocators-header.md)<br/>
