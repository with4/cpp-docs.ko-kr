---
title: '&lt;streambuf&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <streambuf>
dev_langs:
- C++
helpviewer_keywords:
- streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 138ec5bb28e108751a7d4b03651826db38c098fa
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39026934"
---
# <a name="ltstreambufgt"></a>&lt;streambuf&gt;

iostreams 클래스 작동의 기본 요소인 템플릿 클래스 [basic_streambuf](../standard-library/basic-streambuf-class.md)를 정의하는 iostreams 표준 헤더 \<streambuf>를 포함합니다. 이 헤더는 일반적으로 다른 iostreams 헤더에 의해 포함되며, 직접 포함해야 하는 경우는 거의 없습니다.

## <a name="syntax"></a>구문

```cpp
#include <streambuf>

```

### <a name="typedefs"></a>형식 정의

|형식 이름|설명|
|-|-|
|[streambuf](../standard-library/streambuf-typedefs.md#streambuf)|특수화 `basic_streambuf` 를 사용 하는 **char** 템플릿 매개 변수로 합니다.|
|[wstreambuf](../standard-library/streambuf-typedefs.md#wstreambuf)|특수화 `basic_streambuf` 를 사용 하는 **wchar_t** 템플릿 매개 변수로 합니다.|

### <a name="classes"></a>클래스

|클래스|설명|
|-|-|
|[basic_streambuf 클래스](http://msdn.microsoft.com/d9c706ba-ce01-43e0-b0b2-a558fc53ea8d)|템플릿 클래스는 스트림의 특정 표현과 요소 간의 전송을 제어하는 스트림 버퍼 파생을 위한 추상 기본 클래스에 대해 설명합니다.|

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream 프로그래밍](../standard-library/iostream-programming.md)<br/>
[iostreams 규칙](../standard-library/iostreams-conventions.md)<br/>
