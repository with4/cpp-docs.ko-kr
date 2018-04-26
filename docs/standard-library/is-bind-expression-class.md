---
title: is_bind_expression 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- functional/std::is_bind_expression
dev_langs:
- C++
helpviewer_keywords:
- is_bind_expression class
ms.assetid: 0715f9e9-2239-4778-a1cf-2c21f49dfd47
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 40cdf414d70243064975738e9db133c15396e511
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="isbindexpression-class"></a>is_bind_expression 클래스

형식이 `bind`를 호출하여 생성되었는지 테스트합니다.

## <a name="syntax"></a>구문

템플릿<class Ty> 구조체 is_bind_expression {정적 const bool 값;을 (를);

## <a name="remarks"></a>설명

`Ty` 형식이 `bind`를 호출하여 반환된 형식인 경우에는 상수 멤버 `value`가 true이고, 그렇지 않으면 false입니다.

## <a name="example"></a>예제

```cpp
// std__functional__is_bind_expression.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

void square(double x)
{
    std::cout << x << "^2 == " << x * x << std::endl;
}

template<class Expr>
void test_for_bind(const Expr&)
{
    std::cout << std::is_bind_expression<Expr>::value << std::endl;
}

int main()
{
    test_for_bind(3.0 * 3.0);
    test_for_bind(std::bind(square, 3));

    return (0);
}
```

```Output
0
1
```

## <a name="requirements"></a>요구 사항

**헤더:** \<functional>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[bind](../standard-library/functional-functions.md#bind)<br/>
