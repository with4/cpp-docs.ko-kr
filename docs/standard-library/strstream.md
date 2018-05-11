---
title: '&lt;strstream&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <strstream>
dev_langs:
- C++
helpviewer_keywords:
- strstream header
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 882248ab4f9ed692aa36bac5873251867b2fff54
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="ltstrstreamgt"></a>&lt;strstream&gt;

`char` 개체의 할당된 배열에 저장된 시퀀스에 대한 Iostreams 작업을 지원하는 여러 클래스를 정의합니다. 이러한 시퀀스는 C 문자열로/에서 쉽게 변환됩니다.

## <a name="syntax"></a>구문

```cpp
#include <strstream>

```

## <a name="remarks"></a>설명

`strstream` 형식의 개체는 C 문자열인 `char` *로 작업합니다. [basic_string](../standard-library/basic-string-class.md) 형식의 개체로 작업하려면 [\<sstream>](../standard-library/sstream.md)을 사용합니다.

> [!NOTE]
> 클래스 \<a m >는 사용 되지 않습니다. 클래스를 사용 하는 것이 좋습니다. \<a m > 대신 합니다.

### <a name="classes"></a>클래스

|클래스|설명|
|-|-|
|[strstreambuf 클래스](../standard-library/strstreambuf-class.md)|이 클래스는 `char` 배열 개체에 저장된 요소의 시퀀스로/에서 요소의 전송을 제어하는 스트림 버퍼를 설명합니다.|
|[istrstream 클래스](../standard-library/istrstream-class.md)|이 클래스는 [strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 스트림 버퍼에서 요소 및 인코드된 개체 추출을 제어하는 개체를 설명합니다.|
|[ostrstream 클래스](../standard-library/ostrstream-class.md)|이 클래스는 [strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 스트림 버퍼로 요소 및 인코드된 개체 삽입을 제어하는 개체를 설명합니다.|
|[strstream 클래스](../standard-library/strstream-class.md)|이 클래스는 [strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 스트림 버퍼를 사용한 요소 및 인코드된 개체 삽입 및 추출을 제어하는 개체를 설명합니다.|

## <a name="see-also"></a>참고자료

[\<strstream>](../standard-library/strstream.md)<br/>
[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream 프로그래밍](../standard-library/iostream-programming.md)<br/>
[iostreams 규칙](../standard-library/iostreams-conventions.md)<br/>
