---
title: 입력 스트림 개체 생성 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7066ffe50dc76c26528e7bfcd3dc9e9778e1473a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="constructing-input-stream-objects"></a>입력 스트림 개체 생성

`cin` 개체만 사용하는 경우 입력 스트림을 생성할 필요가 없습니다. 다음을 사용하는 경우 입력 스트림을 생성해야 합니다.

- [입력 파일 스트림 생성자](#vclrfinputfilestreamconstructorsanchor8)

- [입력 문자열 스트림 생성자](#vclrfinputstringstreamconstructorsanchor9)

## <a name="vclrfinputfilestreamconstructorsanchor8"></a>입력 파일 스트림 생성자

입력 파일 스트림을 만드는 방법에는 두 가지가 있습니다.

- `void` 인수 생성자를 사용한 다음 `open` 멤버 함수를 호출합니다.

   ```cpp
   ifstream myFile; // On the stack
   myFile.open("filename");

   ifstream* pmyFile = new ifstream; // On the heap
   pmyFile->open("filename");
   ```

- 생성자 호출에서 파일 이름 및 모드 플래그를 지정합니다. 그렇게 하면 생성 프로세스 중 파일이 열립니다.

   ```cpp
   ifstream myFile("filename");
   ```

## <a name="vclrfinputstringstreamconstructorsanchor9"></a>입력 문자열 스트림 생성자

입력 문자열 스트림 생성자를 사용하려면 미리 할당되고 미리 초기화된 저장소의 주소가 필요합니다.

```cpp
string s("123.45");

double amt;
istringstream myString(s);

//istringstream myString("123.45") also works
myString>> amt; // amt contains 123.45
```

## <a name="see-also"></a>참고자료

[입력 스트림](../standard-library/input-streams.md)<br/>
