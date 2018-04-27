---
title: time_get_byname 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xloctime/std::time_get_byname
dev_langs:
- C++
helpviewer_keywords:
- time_get_byname class
ms.assetid: 6e54153e-da40-4bb9-a942-1a6ce57b30c9
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 004c35e3c09f8acc55980024e4752ab26a26afa1
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="timegetbyname-class"></a>time_get_byname 클래스

`time_get`\<CharType, InputIterator> 형식의 로캘 패싯으로 사용할 수 있는 개체에 대해 설명하는 파생된 템플릿 클래스입니다.

## <a name="syntax"></a>구문

```cpp
template <class Elem, class InputIterator =
    istreambuf_iterator<CharType, char_traits<CharType>>>
class time_get_byname : public time_get<CharType, InputIterator>
{
public:
    explicit time_get_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit time_get_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~time_get_byname()
};
```

### <a name="parameters"></a>매개 변수

`_Locname` 명명 된 로캘입니다.

`_Refs` 초기 참조 수입니다.

## <a name="requirements"></a>요구 사항

해당 동작은 명명된 로캘 `_Locname`에 따라 결정됩니다. 각 생성자는 [time_get](../standard-library/time-get-class.md#time_get)\<CharType, InputIterator>( `_Refs`)를 통해 해당 기준 개체를 초기화합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
