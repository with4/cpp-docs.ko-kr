---
title: overflow_error 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- stdexcept/std::overflow_error
dev_langs:
- C++
helpviewer_keywords:
- overflow_error class
ms.assetid: bae7128d-e36b-4a45-84f1-2f89da441d20
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f76aab04fcd7a6458625925ca7c7edbf78fc45b4
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="overflowerror-class"></a>overflow_error 클래스

이 클래스는 산술 오버플로를 보고하기 위해 발생하는 모든 예외에 대한 기본 클래스로 사용됩니다.

## <a name="syntax"></a>구문

```cpp
class overflow_error : public runtime_error {
public:
    explicit overflow_error(const string& message);

    explicit overflow_error(const char *message);

};
```

## <a name="remarks"></a>설명

[what](../standard-library/exception-class.md)에서 반환된 값은 **message**`.`[data](../standard-library/basic-string-class.md#data)의 복사본입니다.

## <a name="example"></a>예제

```cpp
// overflow_error.cpp
// compile with: /EHsc /GR
#include <bitset>
#include <iostream>

using namespace std;

int main( )
{
   try
   {
      bitset< 33 > bitset;
      bitset[32] = 1;
      bitset[0] = 1;
      unsigned long x = bitset.to_ulong( );
   }
   catch ( exception &e )
   {
      cerr << "Caught " << e.what( ) << endl;
      cerr << "Type " << typeid( e ).name( ) << endl;
   };
}
\* Output:
Caught bitset<N> overflow
Type class std::overflow_error
*\
```

## <a name="requirements"></a>요구 사항

**헤더:** \<stdexcept>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[runtime_error 클래스](../standard-library/runtime-error-class.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
