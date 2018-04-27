---
title: directory_entry 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- filesystem/std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- filesystem/std::experimental::filesystem::directory_entry::directory_entry
- filesystem/std::experimental::filesystem::directory_entry::operator=
- filesystem/std::experimental::filesystem::directory_entry::assign
- filesystem/std::experimental::filesystem::directory_entry::replace_filename
- filesystem/std::experimental::filesystem::directory_entry::path
- filesystem/std::experimental::filesystem::directory_entry::status
- filesystem/std::experimental::filesystem::directory_entry::symlink_status
- filesystem/std::experimental::filesystem::directory_entry::operator&lt;
- filesystem/std::experimental::filesystem::directory_entry::operator==
- filesystem/std::experimental::filesystem::directory_entry::operator!=
- filesystem/std::experimental::filesystem::directory_entry::operator&lt;=
- filesystem/std::experimental::filesystem::directory_entry::operator&gt;
- filesystem/std::experimental::filesystem::directory_entry::operator&gt;=
dev_langs:
- C++
ms.assetid: 1827c67b-4137-4548-adb0-f955f7acaf08
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::experimental::filesystem::directory_entry
- std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- std::experimental::filesystem::directory_entry::directory_entry
- std::experimental::filesystem::directory_entry::operator=
- std::experimental::filesystem::directory_entry::assign
- std::experimental::filesystem::directory_entry::replace_filename
- std::experimental::filesystem::directory_entry::path
- std::experimental::filesystem::directory_entry::status
- std::experimental::filesystem::directory_entry::symlink_status
- std::experimental::filesystem::directory_entry::operator&lt;
- std::experimental::filesystem::directory_entry::operator==
- std::experimental::filesystem::directory_entry::operator!=
- std::experimental::filesystem::directory_entry::operator&lt;=
- std::experimental::filesystem::directory_entry::operator&gt;
- std::experimental::filesystem::directory_entry::operator&gt;=
ms.workload:
- cplusplus
ms.openlocfilehash: ba3dc5588cb035cb754ba43a6eeccb37b7ec0b79
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="directoryentry-class"></a>directory_entry 클래스

`*X`에서 반환하는 개체에 대해 설명합니다. 여기서 *X* 는 [directory_iterator](../standard-library/directory-iterator-class.md) 또는 [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md)입니다.

## <a name="syntax"></a>구문

```cpp
class directory_entry;
```

## <a name="remarks"></a>설명

클래스는 [path](../standard-library/path-class.md) 형식의 개체를 저장합니다. 저장된 `path`는 [path 클래스](../standard-library/path-class.md)의 인스턴스이거나 `path`에서 파생된 형식의 인스턴스일 수 있습니다. 또한 두 개의 [file_type](../standard-library/filesystem-enumerations.md#file_type) 값도 저장합니다. 하나는 저장된 파일 이름의 상태에 대해 알려진 정보를 나타내고, 다른 하나는 파일 이름의 기호화된 링크 상태에 대해 알려진 정보를 나타냅니다.

자세한 내용 및 코드 예제를 보려면 [파일 시스템 탐색(C++)](../standard-library/file-system-navigation.md)을 참조하세요.

## <a name="assign"></a>assign

```cpp
void assign(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

멤버 함수는 mypath에 pval을, mystat에 stat를, mysymstat에 symstat를 할당합니다.

## <a name="directoryentry"></a>directory_entry

```cpp
directory_entry() = default;
directory_entry(const directory_entry&) = default;
directory_entry(directory_entry&&) noexcept = default;
explicit directory_entry(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

기본 생성자는 예상대로 작동합니다. 네 번째 생성자는 mypath를 pval로, mystat를 stat_arg로, mysymstat를 symstat_arg로 초기화합니다.

## <a name="operator"></a>operator!=

```cpp
bool operator!=(const directory_entry& right) const noexcept;
```

멤버 함수는 !(*this == right)를 반환합니다.

## <a name="operator"></a>operator=

```cpp
directory_entry& operator=(const directory_entry&) = default;
directory_entry& operator=(directory_entry&&) noexcept = default;
```

기본 멤버 대입 연산자가 예상대로 작동합니다.

## <a name="operator"></a>operator==

```cpp
bool operator==(const directory_entry& right) const noexcept;
```

멤버 함수는 mypath == right.mypath를 반환합니다.

## <a name="operatorlt"></a>연산자&lt;

```cpp
bool operator<(const directory_entry& right) const noexcept;
```

멤버 함수는 mypath를 반환 합니다. &lt; right.mypath 합니다.

## <a name="operatorlt"></a>operator&lt;=

```cpp
bool operator&lt;=(const directory_entry& right) const noexcept;
```

멤버 함수는 !(right \< *this)를 반환합니다.

## <a name="operatorgt"></a>연산자&gt;

```cpp
bool operator&gt;(const directory_entry& right) const noexcept;
```

멤버 함수는 right \< *this를 반환합니다.

## <a name="operatorgt"></a>operator&gt;=

```cpp
bool operator&gt;=(const directory_entry& right) const noexcept;
```

멤버 함수가 반환 하는! (*이 \< 오른쪽)입니다.

## <a name="operator-const-pathtype"></a>operator const path_type&

```cpp
operator const std::experimental::filesystem::path&() const;
```

멤버 연산자는 mypath를 반환합니다.

## <a name="path"></a>path

```cpp
const std::experimental::filesystem::path& path() const noexcept;
```

멤버 함수는 mypath를 반환합니다.

## <a name="replacefilename"></a>replace_filename

```cpp
void replace_filename(
    const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

멤버 함수는 mypath를 mypath.parent_path() / pval로, mystat를 stat_arg로, mysymstat를 symstat_arg로 바꿉니다.

## <a name="status"></a>status

```cpp
file_status status() const;
file_status status(error_code& ec) const noexcept;
```

두 멤버 함수는 다음과 같이 먼저 변경될 수 있는 mystat를 반환합니다.

1. status_known(mystat)이면 아무 작업도 수행하지 않습니다.

1. 그렇지 않고 !status_known(mysymstat) && !is_symlink(mysymstat)이면 mystat = mysymstat입니다.

## <a name="symlinkstatus"></a>symlink_status

```cpp
file_status symlink_status() const;
file_status symlink_status(error_code& ec) const noexcept;
```

두 멤버 함수는 다음과 같이 먼저 변경될 수 있는 mysymstat를 반환합니다. status_known(mysymstat)이면 아무 작업도 수행하지 않습니다. 그렇지 않으면  mysymstat = symlink_status(mypval)입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<실험적/파일 시스템&gt;

**네임스페이스:** std::experimental::filesystem

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<filesystem&gt;](../standard-library/filesystem.md)<br/>
