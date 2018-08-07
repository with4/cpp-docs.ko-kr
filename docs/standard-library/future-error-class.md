---
title: future_error 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- future/std::future_error
dev_langs:
- C++
ms.assetid: 6071c545-ac2a-49ef-9967-07b0125da861
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e5d5c24a658f53dbef4075d68f5aead5454356b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845013"
---
# <a name="futureerror-class"></a>future_error 클래스

[future](../standard-library/future-class.md) 개체를 관리하는 형식의 메서드에서 throw될 수 있는 예외 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
class future_error : public logic_error {
public:
    future_error(error_code code);

const error_code& code() const throw();

const char *what() const throw();

};
```

## <a name="requirements"></a>요구 사항

**헤더:** \<이후 >

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[logic_error 클래스](../standard-library/logic-error-class.md)<br/>
[error_code 클래스](../standard-library/error-code-class.md)<br/>
