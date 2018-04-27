---
title: '&lt;system_error&gt; 형식 정의 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- system_error/std::generic_errno
ms.assetid: 28cf9f7d-9c28-4baa-a297-67c8260b07fb
caps.latest.revision: 11
manager: ghogen
ms.openlocfilehash: 701df57adb0576160f5aade9fd26220c852150ac
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ltsystemerrorgt-typedefs"></a>&lt;system_error&gt; 형식 정의

||
|-|
|[generic_errno](#generic_errno)|

## <a name="generic_errno"></a>  generic_errno

`<errno.h>`에서 Posix에 의해 정의되는 모든 오류 코드 매크로의 심볼 이름을 제공하는 열거형을 나타내는 형식입니다.

```cpp
typedef errc generic_error;
```

### <a name="remarks"></a>설명

이 형식은 [errc](../standard-library/system-error-enums.md#errc)와 동일한 의미입니다.

## <a name="see-also"></a>참고자료

[<system_error>](../standard-library/system-error.md)<br/>
