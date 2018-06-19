---
title: file_status 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::file_status
- filesystem/std::experimental::filesystem::file_status::operator=
- filesystem/std::experimental::filesystem::file_status::type
- filesystem/std::experimental::filesystem::file_status::permissions
dev_langs:
- C++
ms.assetid: 9781840e-ad22-44dd-ad79-0fabaa94bac4
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::experimental::filesystem::file_status
- std::experimental::filesystem::file_status::operator=
- std::experimental::filesystem::file_status::type
- std::experimental::filesystem::file_status::permissions
ms.workload:
- cplusplus
ms.openlocfilehash: be8f85041099d76a4bbb492aa55c5fb73d870589
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842536"
---
# <a name="filestatus-class"></a>file_status 클래스

[file_type](../standard-library/filesystem-enumerations.md#file_type) 및 파일 [perms](../standard-library/filesystem-enumerations.md#perms)를 래핑합니다.

## <a name="syntax"></a>구문

```cpp
class file_status;
```

## <a name="filestatusfilestatus"></a>file_status::file_status

```cpp
explicit file_status(
   file_type ftype = file_type::none,
   perms mask = perms::unknown) noexcept;

file_status(const file_status&) noexcept = default;

file_status(file_status&&) noexcept = default;

~file_status() noexcept = default;
```

## <a name="filestatusoperator"></a>file_status::operator=

```cpp
file_status& operator=(const file_status&) noexcept = default;
file_status& operator=(file_status&&) nexcept = default;
```

기본 멤버 대입 연산자가 예상대로 작동합니다.

## <a name="type"></a>type

```cpp
file_type type() const noexcept
void type(file_type ftype) noexcept
```

file_type을 가져오거나 설정합니다.

## <a name="permissions"></a>permissions

```cpp
perms permissions() const noexcept
void permissions(perms mask) noexcept
```

파일 사용 권한을 가져오거나 설정합니다.

setter를 사용하여 파일을 읽기 전용으로 만들거나 읽기 전용 특성을 제거합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<파일 시스템 >

**Namespace:** std::experimental::filesystem, std::experimental::filesystem

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[path 클래스](../standard-library/path-class.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
