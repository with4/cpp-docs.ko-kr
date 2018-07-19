---
title: indirect_array 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- valarray/std::indirect_array
dev_langs:
- C++
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 676cc8ea493d113e9ef8a6f85108fdf3bad6ce5f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38959509"
---
# <a name="indirectarray-class"></a>indirect_array 클래스

부모 valarray의 인덱스 하위 집합을 지정하여 정의된 하위 집합 배열 간의 작업을 제공하여 valarray의 하위 집합인 개체를 지원하는 내부 보조 템플릿 클래스입니다.

## <a name="syntax"></a>구문

## <a name="remarks"></a>설명

개체에 대 한 참조를 저장 하는 개체를 설명 하는 클래스 `va` 클래스의 [valarray](../standard-library/valarray-class.md)**\<유형 >**, 개체와 함께 `xa` 클래스의 `valarray<size_t>`, 선택할 요소의 시퀀스를 설명 하는 `valarray<Type>` 개체입니다.

생성 하는 `indirect_array<Type>` 개체 형식의 식을 작성 해야만 `va[xa]`합니다. Indirect_array 클래스의 멤버 함수에 대해 정의 된 해당 함수 시그니처 처럼 동작 `valarray<Type>`에 선택한 요소의 시퀀스에만 영향을 제외 하 고, 합니다.

시퀀스 이루어져 **xa.** [크기](../standard-library/valarray-class.md#size) 요소에 있는 요소 `I` 인덱스가 됩니다 **xa**[ `I`] 내에서 `va`합니다.

## <a name="example"></a>예제:

```cpp
// indirect_array.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      va [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 2 )
      va [ i ] =  -1;

   cout << "The initial operand valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   // Select 2nd, 4th & 6th elements
   // and assign a value of 10 to them
   valarray<size_t> indx ( 3 );
   indx [0] = 2;
   indx [1] = 4;
   indx [2] = 6;
   va[indx] = 10;

   cout << "The modified operand valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;
}
```

### <a name="output"></a>출력

```cpp
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 10 -1 10 -1 10 -1 8 -1).
```

## <a name="requirements"></a>요구 사항

**헤더:** \<valarray>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
