---
title: steady_clock 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- chrono/std::chrono::steady_clock
dev_langs:
- C++
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ba4ebbe6db12fef05bfabd9970d354a7726fcd7d
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="steadyclock-struct"></a>steady_clock 구조체

`steady` 클록을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
struct steady_clock;
```

## <a name="remarks"></a>설명

Windows에서 steady_clock은 QueryPerformanceCounter 함수를 래핑합니다.

`now()`에 대한 첫 번째 호출에서 반환되는 값이 항상 `now()`에 대한 순차적 호출에서 반환되는 값보다 작거나 같을 경우 클록은 *단조*입니다.

클록이 *단조*이고 클록 틱 간 시간이 지속적이면 해당 클록은 *지속*입니다.

High_resolution_clock은 steady_clock에 대한 typedef입니다.

## <a name="public-functions"></a>공용 함수

|함수|설명|
|--------------|-----------------|
|now|현재 시간을 time_point 값으로 반환합니다.|

## <a name="public-constants"></a>공용 상수

|이름|설명|
|----------|-----------------|
|`system_clock::is_steady`|`true`입니다. `steady_clock`은 *지속*입니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<c h >

**네임스페이스:** std::chrono

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono>](../standard-library/chrono.md)<br/>
[system_clock 구조체](../standard-library/system-clock-structure.md)<br/>
