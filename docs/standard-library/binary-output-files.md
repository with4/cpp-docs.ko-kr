---
title: 이진 출력 파일 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- I/O [C++], binary output files
- files [C++], binary output files
- binary data, binary output files
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cdb101620b1a61f3a29057ee408cf9e89d38f9e8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842354"
---
# <a name="binary-output-files"></a>이진 출력 파일

스트림은 원래 텍스트용으로 설계되었으므로 기본 출력 모드는 텍스트입니다. 텍스트 모드에서 줄 바꿈 문자 (16 진수 10)는 캐리지 리턴-줄 바꿈 (16 비트에만 해당)를 확장합니다. 확장에는 다음과 같은 문제가 수반될 수 있습니다.

```cpp
// binary_output_files.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;
int iarray[2] = { 99, 10 };
int main( )
{
    ofstream os( "test.dat" );
    os.write( (char *) iarray, sizeof( iarray ) );
}
```

사용자는 이 프로그램이 바이트 시퀀스 {99, 0, 10, 0}을 출력할 것으로 예상할 수 있지만, 대신 {99, 0, 13, 10, 0}이 출력되므로 이진 입력을 예상하는 프로그램에 문제가 발생합니다. 문자가 번역되지 않은 상태로 작성되는 진정한 이진 출력이 필요한 경우 [ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) 생성자 openmode 인수를 사용하여 이진 출력을 지정할 수 있습니다.

```cpp
// binary_output_files2.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;
int iarray[2] = { 99, 10 };

int main()
{
   ofstream ofs ( "test.dat", ios_base::binary );

   // Exactly 8 bytes written
   ofs.write( (char*)&iarray[0], sizeof(int)*2 );
}
```

## <a name="see-also"></a>참고자료

[출력 스트림](../standard-library/output-streams.md)<br/>
