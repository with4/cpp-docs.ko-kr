---
title: bad_function_call 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- functional/std::bad_function_call
dev_langs:
- C++
helpviewer_keywords:
- bad_function_call class
ms.assetid: b70a0268-43ff-4f3b-a283-faf1cb172d4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e00dd485478a5a6fb7ff029afdad7bf7212fd56
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33839948"
---
# <a name="badfunctioncall-class"></a>bad_function_call 클래스

잘못된 함수 호출을 보고합니다.

## <a name="syntax"></a>구문

```cpp
class bad_function_call
 : public std::exception {
 };
```

## <a name="remarks"></a>설명

이 클래스는 [function 클래스](../standard-library/function-class.md)에서 `operator()`에 대한 호출이 있었음을 나타내기 위해 throw된 예외를 설명합니다.
