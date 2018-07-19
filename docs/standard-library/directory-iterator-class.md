---
title: directory_iterator 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::directory_iterator
- filesystem/std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::increment
- filesystem/std::experimental::filesystem::directory_iterator::operator=
- filesystem/std::experimental::filesystem::directory_iterator::operator==
- filesystem/std::experimental::filesystem::directory_iterator::operator!=
- filesystem/std::experimental::filesystem::directory_iterator::operator*
- filesystem/std::experimental::filesystem::directory_iterator::operator-&gt;
- filesystem/std::experimental::filesystem::directory_iterator::operator++
dev_langs:
- C++
ms.assetid: dca2ecf8-3e69-4644-a83d-705061e10cc8
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::directory_iterator::directory_iterator
- std::experimental::filesystem::directory_iterator::increment
- std::experimental::filesystem::directory_iterator::operator=
- std::experimental::filesystem::directory_iterator::operator==
- std::experimental::filesystem::directory_iterator::operator!=
- std::experimental::filesystem::directory_iterator::operator*
- std::experimental::filesystem::directory_iterator::operator-&gt;
- std::experimental::filesystem::directory_iterator::operator++
ms.workload:
- cplusplus
ms.openlocfilehash: b46e4d8fc7b59f8b4919a7e36a85f29f626aa80b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845832"
---
# <a name="directoryiterator-class"></a>directory_iterator 클래스

디렉터리에서 파일 이름을 통해 시퀀스되는 입력 반복기에 대해 설명합니다. 반복기 X에 대해 식 *X는 파일 이름과 상태에 대해 알려진 모든 항목을 래핑하는 directory_entry 클래스의 개체로 계산됩니다.

이 클래스는 표시를 위해 mydir이라는 경로 형식의 개체를 저장하여 시퀀스할 디렉터리의 이름을 나타내고, myentry라는 directory_entry 형식의 개체를 저장하여 디렉터리 시퀀스의 현재 파일 이름을 나타냅니다. directory_entry 형식의 기본 생성 개체에는 빈 mydir 경로 이름이 있고 시퀀스의 끝 반복기를 나타냅니다.

예를 들어 def 및 ghi 항목과 함께 디렉터리 abc를 지정할 경우 코드는 다음과 같습니다.

`for (directory_iterator next(path("abc")), end; next != end; ++next)     visit(next->path());`

path("abc/def") 및 path("abc/ghi") 인수를 사용하여 visit를 호출합니다.

자세한 내용 및 코드 예제를 보려면 [파일 시스템 탐색(C++)](../standard-library/file-system-navigation.md)을 참조하세요.

## <a name="syntax"></a>구문

```cpp
class directory_iterator;
```

## <a name="directoryiteratordirectoryiterator"></a>directory_iterator::directory_iterator

```cpp
directory_iterator() noexcept;
explicit directory_iterator(const path& pval);

directory_iterator(const path& pval, error_code& ec) noexcept;
directory_iterator(const directory_iterator&) = default;
directory_iterator(directory_iterator&&) noexcept = default;
```

첫 번째 생성자는 시퀀스의 끝 반복기를 생성합니다. 두 번째 및 세 번째 생성자는 pval을 mydir에 저장한 다음 mydir을 디렉터리로 열어 읽으려고 시도합니다. 성공하면 첫 번째 파일 이름을 myentry의 디렉터리에 저장하고, 실패하면 시퀀스의 끝 반복기를 생성합니다.

기본 생성자는 예상대로 작동합니다.

## <a name="directoryiteratorincrement"></a>directory_iterator::increment

```cpp
directory_iterator& increment(error_code& ec) noexcept;
```

함수는 디렉터리의 다음 파일 이름으로 이동하려고 합니다. 성공하면 해당 파일 이름을 myentry에 저장하고, 실패하면 시퀀스의 끝 반복기를 생성합니다.

## <a name="directoryiteratoroperator"></a>directory_iterator::operator!=

```cpp
bool operator!=(const directory_iterator& right) const;
```

멤버 연산자는 !(*this == right)를 반환합니다.

## <a name="directoryiteratoroperator"></a>directory_iterator::operator=

```cpp
directory_iterator& operator=(const directory_iterator&) = default;
directory_iterator& operator=(directory_iterator&&) noexcept = default;
```

기본 멤버 대입 연산자가 예상대로 작동합니다.

## <a name="directoryiteratoroperator"></a>directory_iterator::operator==

```cpp
bool operator==(const directory_iterator& right) const;
```

멤버 연산자는 *this와 right가 둘 다 시퀀스의 끝 반복기이거나 둘 다 시퀀스의 끝 반복기가 아닌 경우에만 true를 반환합니다.

## <a name="directoryiteratoroperator"></a>directory_iterator::operator*

```cpp
const directory_entry& operator*() const;
```

멤버 연산자는 myentry를 반환합니다.

## <a name="directoryiteratoroperator-"></a>directory_iterator::operator->

```cpp
const directory_entry * operator->() const;
```

멤버 함수는 &**this를 반환합니다.

## <a name="directoryiteratoroperator"></a>directory_iterator::operator++

```cpp
directory_iterator& operator++();
directory_iterator& operator++(int);
```

첫 번째 멤버 함수는 increment()를 호출한 다음 *this를 반환합니다. 두 번째 멤버 함수는 개체의 복사본을 만들고 increment()를 호출한 다음 복사본을 반환합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<experimental/filesystem>

**네임스페이스:** std::experimental::filesystem

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[파일 시스템 탐색(C++)](../standard-library/file-system-navigation.md)<br/>
