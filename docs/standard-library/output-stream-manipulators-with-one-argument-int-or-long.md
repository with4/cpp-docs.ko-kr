---
title: 하나의 인수를 포함하는 출력 스트림 조작자(int 또는 long) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- output streams, int or long argument manipulators
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f3238ffcbd03f40c6eac0423d0212a65719fb33d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853075"
---
# <a name="output-stream-manipulators-with-one-argument-int-or-long"></a>하나의 인수를 포함하는 출력 스트림 조작자(int 또는 long)

iostream 클래스 라이브러리는 매개 변수가 있는 조작자를 만들기 위한 매크로 집합을 제공합니다. 단일 `int` 또는 `long` 인수가 포함된 조작자는 특수한 경우입니다. `setw`와 같이 단일 `int` 또는 `long` 인수를 허용하는 출력 스트림 조작자를 만들려면 \<iomanip>에서 정의되는 _Smanip 매크로를 사용해야 합니다. 이 예제에서는 지정된 수의 공백을 스트림에 삽입하는 `fillblank` 조작자를 정의합니다.

## <a name="example"></a>예제

```cpp
// output_stream_manip.cpp
// compile with: /GR /EHsc
#include <iostream>
#include <iomanip>
using namespace std;

void fb( ios_base& os, int l )
{
   ostream *pos = dynamic_cast<ostream*>(&os);
   if (pos)
   {
      for( int i=0; i < l; i++ )
      (*pos) << ' ';
   };
}

_Smanip<int>
   __cdecl fillblank(int no)
   {
   return (_Smanip<int>(&fb, no));
   }

int main( )
{
   cout << "10 blanks follow" << fillblank( 10 ) << ".\n";
}
```

## <a name="see-also"></a>참고자료

[인수 포함 사용자 지정 조작자](../standard-library/custom-manipulators-with-arguments.md)<br/>
