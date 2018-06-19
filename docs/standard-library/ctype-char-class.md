---
title: ctype&lt;char&gt; 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- ctype<char>
- locale/std::ctype<char>
dev_langs:
- C++
helpviewer_keywords:
- ctype<char> class
ms.assetid: ee30acb4-a743-405e-b3d4-13602092da84
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: edbc96419e68cf584222e4008f58fd96169b2fb9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33846001"
---
# <a name="ctypeltchargt-class"></a>ctype&lt;char&gt; 클래스

이 클래스는 `char` 형식에 대한 템플릿 클래스 **ctype\<CharType**>의 명시적 특수화입니다. `char` 형식 문자의 다양한 속성에 대해 특징을 지정하기 위한 로캘 패싯으로 사용할 수 있는 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <>
class ctype<char>
: public ctype_base
{
public:
    typedef char _Elem;
    typedef _Elem char_type;
    bool is(
    mask _Maskval,
    _Elem _Ch) const;


    const _Elem* is(
    const _Elem* first,
    const _Elem* last,
    mask* dest) const;


    const _Elem* scan_is(
    mask _Maskval,
    const _Elem* first,
    const _Elem* last) const;


    const _Elem* scan_not(
    mask _Maskval,
    const _Elem* first,
    const _Elem* last) const;


    _Elem tolower(
    _Elem _Ch) const;


    const _Elem* tolower(
    _Elem* first,
    const _Elem* last) const;


    _Elem toupper(
    _Elem _Ch) const;


    const _Elem* toupper(
    _Elem* first,
    const _Elem* last) const;


    _Elem widen(
    char _Byte) const;


    const _Elem* widen(
    const char* first,
    const char* last,
    _Elem* dest) const;


    const _Elem* _Widen_s(
    const char* first,
    const char* last,
    _Elem* dest,
    size_t dest_size) const;


    _Elem narrow(
    _Elem _Ch,
    char _Dflt = '\0') const;


    const _Elem* narrow(
    const _Elem* first,
    const _Elem* last,
    char _Dflt,
    char* dest) const;


    const _Elem* _Narrow_s(
    const _Elem* first,
    const _Elem* last,
    char _Dflt,
    char* dest,
    size_t dest_size) const;


    static locale::id& id;
    explicit ctype(
    const mask* _Table = 0,
    bool _Deletetable = false,
    size_t _Refs = 0);

protected:
    virtual ~ctype();
//other protected members
};
```

## <a name="remarks"></a>설명

명시적 특수화는 다음과 같은 여러 가지 면에서 템플릿 클래스와 다릅니다.

- ctype<`char`> 클래스의 개체는 **ctype_base::mask** 형식의 UCHAR_MAX + 1 요소로 구성된 배열인, ctype 마스크 테이블의 첫 번째 요소에 대한 포인터를 저장합니다. 또한 ctype\< **Elem**> 개체가 삭제된 경우 배열을 삭제해야 할지(`operator delete[]`를 사용하여) 여부를 나타내는 부울 개체도 저장합니다.

- 유일한 공용 생성자를 사용하여 ctype 마스크 테이블, **tab**을 지정하고 ctype<`char`> 개체가 삭제되었을 때 배열을 삭제해야 하는 경우 true인 부울 개체, **del**을 지정하고 참조 횟수 매개 변수 refs도 지정할 수 있습니다.

- 보호된 멤버 함수 **table**은 저장된 ctype 마스크 테이블을 반환합니다.

- 정적 멤버 개체 **table_size**는 ctype 마스크 테이블의 최소 요소 수를 지정합니다.

- 보호된 정적 멤버 함수 **classic_table**은 "C" 로캘에 적합한 ctype 마스크 테이블을 반환합니다.

- 보호된 가상 멤버 함수 [do_is](../standard-library/ctype-class.md#do_is), [do_scan_is](../standard-library/ctype-class.md#do_scan_is) 또는 [do_scan_not](../standard-library/ctype-class.md#do_scan_not)이 없습니다. 해당 공용 멤버 함수는 동일한 작업을 자체적으로 수행합니다.

멤버 함수 [do_narrow](../standard-library/ctype-class.md#do_narrow) 및 [do_widen](../standard-library/ctype-class.md#do_widen)은 변경되지 않은 요소를 복사합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[facet 클래스](http://msdn.microsoft.com/Library/dd4f12f5-cb1b-457f-af56-2fb204216ec1)<br/>
[ctype_base 클래스](../standard-library/ctype-base-class.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
