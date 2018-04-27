---
title: 출력 파일 스트림 구성원 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- output streams [C++], member functions
ms.assetid: 38aaf710-8035-4a34-a0c4-123a5327f28a
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b7f845c4d35f638a096bad3bab6897ed3bd7f790
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="output-file-stream-member-functions"></a>Output File Stream Member 함수

출력 스트림 구성원 함수에는 조작자와 동일한 형식, 서식 없는 쓰기 작업을 수행하는 형식 및 그 외의 스트림 상태를 수정하며 동일한 조작자 또는 삽입 연산자를 포함하지 않는 형식의 세 가지 형식이 있습니다. 서식 있는 순차적 출력을 생성하려는 경우 삽입 연산자 및 조작자만 사용할 수 있습니다. 임의 액세스 이진 디스크 출력의 경우에는 필요에 따라 삽입 연산자를 포함하여 다른 구성원 함수를 사용합니다.

## <a name="the-open-function-for-output-streams"></a>출력 스트림에 대한 open 함수

출력 파일 스트림([ofstream](../standard-library/basic-ofstream-class.md))을 사용하려면 생성자 또는 **open** 함수에서 특정 디스크 파일과 해당 스트림을 연결해야 합니다. **open** 함수를 사용하는 경우 일련의 파일에 대해 같은 스트림 개체를 다시 사용할 수 있습니다. 어떤 경우든 파일을 설명하는 인수는 동일합니다.

출력 스트림과 연결된 파일을 열 때는 대개 **open_mode** 플래그를 지정합니다. `ios` 클래스에서 열거자로 정의되는 이러한 플래그는 비트 OR(&#124;) 연산자를 사용하여 결합할 수 있습니다. 열거자 목록은 [ios_base::openmode](../standard-library/ios-base-class.md#openmode)를 참조하세요.

흔히 볼 수 있는 세 가지 출력 스트림에서는 모드 옵션이 사용됩니다.

- 파일 만들기. 파일이 이미 있는 경우에는 이전 버전이 삭제됩니다.

   ```cpp
   ostream ofile("FILENAME");
   // Default is ios::out

   ofstream ofile("FILENAME", ios::out);
   // Equivalent to above
   ```

- 기존 파일에 레코드를 추가하거나 파일이 없으면 만듭니다.

   ```cpp
   ofstream ofile("FILENAME", ios::app);
   ```

- 두 파일을 같은 스트림에서 한 번에 하나씩 엽니다.

   ```cpp
   ofstream ofile();
   ofile.open("FILE1", ios::in);
   // Do some output
   ofile.close();    // FILE1 closed
   ofile.open("FILE2", ios::in);
   // Do some more output
   ofile.close();    // FILE2 closed
   // When ofile goes out of scope it is destroyed.
   ```

## <a name="the-put"></a>put

**put** 함수는 출력 스트림에 문자 하나를 씁니다. 다음의 두 문은 기본적으로 동일하지만 두 번째 문에는 스트림의 형식 인수가 적용됩니다.

```cpp
cout.put('A');

// Exactly one character written
cout <<'A'; // Format arguments 'width' and 'fill' apply
```

## <a name="the-write"></a>쓰기

**write** 함수는 출력 파일 스트림에 메모리 블록을 씁니다. 길이 인수가 기록되는 바이트 수를 지정합니다. 이 예에서는 출력 파일 스트림을 만들고 `Date` 구조체의 이진 값을 해당 스트림에 씁니다.

```cpp
// write_function.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;

struct Date
{
   int mo, da, yr;
};

int main( )
{
   Date dt = { 6, 10, 92 };
   ofstream tfile( "date.dat" , ios::binary );
   tfile.write( (char *) &dt, sizeof dt );
}
```

**write** 함수는 null 문자에 도달할 때까지 중지되지 않으므로 전체 클래스 구조체가 기록됩니다. 이 함수는 두 개의 인수, 즉 `char` 포인터와 쓸 문자 수를 사용합니다. 구조체 개체의 주소 앞에는 **char\*** 로의 캐스팅이 필요합니다.

## <a name="the-seekp-and-tellp-functions"></a>seekp 및 tellp 함수

출력 파일 스트림은 다음에 데이터를 쓸 위치를 가리키는 내부 포인터를 유지합니다. `seekp` 구성원 함수는 이 포인터를 설정하므로 임의 액세스 디스크 파일 출력을 제공합니다. `tellp` 구성원 함수는 파일 위치를 반환합니다. `seekp` 및 `tellp`와 동일한 입력 스트림용 함수를 사용하는 예제는 [seekg 및 tellg 함수](../standard-library/input-stream-member-functions.md)를 참조하세요.

## <a name="the-close-function-for-output-streams"></a>출력 스트림에 대한 close 함수

**close** 구성원 함수는 출력 파일 스트림과 연결된 디스크 파일을 닫습니다. 모든 디스크 출력을 완료하려면 파일을 닫아야 합니다. 필요한 경우 `ofstream` 소멸자가 파일을 자동으로 닫지만, 같은 스트림 개체에 대해 다른 파일을 열어야 하는 경우에는 **close** 함수를 사용할 수 있습니다.

출력 스트림 소멸자는 생성자 또는 **open** 구성원 함수가 스트림의 파일을 연 경우에만 해당 파일을 닫습니다. 이미 열린 파일에 대해 생성자에 파일 설명자를 전달하거나 **attach** 구성원 함수를 사용하는 경우에는 파일을 명시적으로 닫아야 합니다.

## <a name="vclrferrorprocessingfunctionsanchor10"></a> 오류 처리 함수

스트림에 쓰는 중에 오류를 테스트하려면 다음 구성원 함수를 사용합니다.

|함수|반환 값|
|--------------|------------------|
|[bad](http://msdn.microsoft.com/Library/4038d331-e9c9-48b0-bf49-c6505744469c)|복구할 수 없는 오류가 발생하는 경우 **true**를 반환합니다.|
|[fail](http://msdn.microsoft.com/Library/619f1b36-1e72-4551-8b48-888ae4e370d2)|복구할 수 없는 오류 또는 "정상" 상황(예: 변환 오류)이 발생하거나 파일을 찾을 수 없는 경우 **true**를 반환합니다. 인수로 0을 사용하여 **clear**를 호출하고 나면 처리가 다시 시작되는 경우가 많습니다.|
|[good](http://msdn.microsoft.com/Library/77f0aa17-2ae1-48ae-8040-592d301e3972)|복구 가능 여부와 관계없이 오류 조건이 없으며 파일 끝 플래그가 설정되어 있지 않은 경우 **true**를 반환합니다.|
|[eof](http://msdn.microsoft.com/Library/3087f631-1268-49cd-86cf-ff4108862329)|파일 끝 조건에서 **true**를 반환합니다.|
|[clear](http://msdn.microsoft.com/Library/dc172694-1267-45f8-8f5c-e822e16fc271)|내부 오류 상태를 설정합니다. 기본 인수를 사용하여 호출된 경우에는 모든 오류 비트를 지웁니다.|
|[rdstate](http://msdn.microsoft.com/Library/e235e4e2-7e95-4777-a160-3938d263dd9c)|현재 오류 상태를 반환합니다.|

**!** 연산자는 **fail** 함수와 같은 기능을 수행하도록 오버로드됩니다. 따라서 다음 식은

```cpp
if(!cout)...
```

다음과 동일합니다.

```cpp
if(cout.fail())...
```

**void\*()** 연산자는 **!** 연산자와 반대가 되도록 오버로드되므로 다음 식은

```cpp
if(cout)...
```

다음과 동일합니다.

```cpp
if(!cout.fail())...
```

**void\*()** 연산자를 파일 끝을 테스트하지 않으므로 **good**과 동일하지 않습니다.

## <a name="see-also"></a>참고자료

[출력 스트림](../standard-library/output-streams.md)<br/>
