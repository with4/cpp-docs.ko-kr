---
title: steady_clock 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 05/22/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::steady_clock
dev_langs:
- C++
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5445379597c4fefcd657303a05c33b6509d54d2e
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34569900"
---
# <a name="steadyclock-struct"></a>steady_clock 구조체

나타냅니다는 *시에도 계속* 클록입니다.

## <a name="syntax"></a>구문

```cpp
struct steady_clock;
```

## <a name="remarks"></a>설명

Windows에서는 `steady_clock` 래핑하는 `QueryPerformanceCounter` 함수입니다.

`now`에 대한 첫 번째 호출에서 반환되는 값이 항상 `now`에 대한 순차적 호출에서 반환되는 값보다 작거나 같을 경우 클록은 *단조*입니다. 클록이 *단조*이고 클록 틱 간 시간이 지속적이면 해당 클록은 *지속*입니다.

`high_resolution_clock` 에 대 한 typedef `steady_clock`합니다.

### <a name="public-typedefs"></a>공용 typedefs

|name|설명|
|----------|-----------------|
|`steady_clock::duration`|에 대 한 동의어 `nanoseconds`에 정의 된 \<h r o n >.|
|`steady_clock::period`|에 대 한 동의어 `nano`에 정의 된 \<비율 > 합니다.|
|`steady_clock::rep`|에 대 한 동의어 **긴** **긴**의 포함 된 인스턴스화에서 클록 틱 수를 나타내는 데 사용 되는 형식 `duration`합니다.|
|`steady_clock::time_point`|`chrono::time_point<steady_clock>`의 동의어입니다.|

## <a name="public-functions"></a>공용 함수

|기능|설명|
|--------------|-----------------|
|`now`|현재 시간으로 반환 된 `time_point` 값입니다.|

## <a name="public-constants"></a>공용 상수

|name|설명|
|----------|-----------------|
|`steady_clock::is_steady`|`true`입니다. `steady_clock`은 *지속*입니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<c h >

**네임스페이스:** std::chrono

## <a name="see-also"></a>참고자료

- [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)
- [\<chrono>](../standard-library/chrono.md)
- [system_clock 구조체](../standard-library/system-clock-structure.md)
