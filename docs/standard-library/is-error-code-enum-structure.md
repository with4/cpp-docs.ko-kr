---
title: is_error_code_enum 구조체 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- future/std::is_error_code_enum
dev_langs:
- C++
ms.assetid: 84ae4b99-66d2-41ba-9b50-645fcbe14630
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7d28754bd005627fc6c14d5d8870941158bff937
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33843342"
---
# <a name="iserrorcodeenum-structure"></a>is_error_code_enum 구조체

[future_errc](../standard-library/future-enums.md#future_errc)가 [error_code](../standard-library/error-code-class.md)를 저장하는 데 적합함을 나타내는 특수화입니다.

## <a name="syntax"></a>구문

```cpp
template <>
struct is_error_code_enum<Future_errc> : public true_type;
```

## <a name="requirements"></a>요구 사항

**헤더:** \<이후 >

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<future>](../standard-library/future.md)<br/>
