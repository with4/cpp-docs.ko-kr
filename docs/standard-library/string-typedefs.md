---
title: "&lt;string&gt; 형식 정의 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- string/std::string
- string/std::u16string
- string/std::u32string
- string/std::wstring
ms.assetid: fdca01e9-f2f1-4b59-abda-0093d760b3cc
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 553310c3c25eb0565506c1ad837591967d6c5ee1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ltstringgt-typedefs"></a>&lt;string&gt; 형식 정의
||||  
|-|-|-|  
|[string](#string)|[u16string](#u16string)|[u32string](#u32string)|  
|[wstring](#wstring)|  
  
##  <a name="string"></a>  string  
 `char` 형식 요소가 포함된 템플릿 클래스 [basic_string](../standard-library/basic-string-class.md)의 특수화를 설명하는 형식입니다.  
  
 `basic_string`을 특수화하는 기타 형식 정의에는 [wstring](../standard-library/string-typedefs.md#wstring), [u16string](../standard-library/string-typedefs.md#u16string), [u32string](../standard-library/string-typedefs.md#u32string) 등이 있습니다.  
  
```cpp  
typedef basic_string<char, char_traits<char>, allocator<char>> string;
```  
  
### <a name="remarks"></a>설명  
 아래의 코드 두 줄은 동일한 선언입니다.  
  
```cpp  
string str("");

basic_string<char> str("");
```  
  
 문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.  
  
##  <a name="u16string"></a>  u16string  
 `char16_t` 형식 요소가 포함된 템플릿 클래스 [basic_string](../standard-library/basic-string-class.md)의 특수화를 설명하는 형식입니다.  
  
 `basic_string`을 특수화하는 기타 형식 정의에는 [wstring](../standard-library/string-typedefs.md#wstring), [string](../standard-library/string-typedefs.md#string), [u32string](../standard-library/string-typedefs.md#u32string) 등이 있습니다.  
  
```cpp  
typedef basic_string<char16_t, char_traits<char16_t>, allocator<char16_t>> u16string;
```  
  
### <a name="remarks"></a>설명  
 문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.  
  
##  <a name="u32string"></a>  u32string  
 `char32_t` 형식 요소가 포함된 템플릿 클래스 [basic_string](../standard-library/basic-string-class.md)의 특수화를 설명하는 형식입니다.  
  
 `basic_string`을 특수화하는 기타 형식 정의에는 [string](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string), [wstring](../standard-library/string-typedefs.md#wstring) 등이 있습니다.  
  
```cpp  
typedef basic_string<char32_t, char_traits<char32_t>, allocator<char32_t>> u32string;
```  
  
### <a name="remarks"></a>설명  
 문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.  
  
##  <a name="wstring"></a>  wstring  
 `wchar_t` 형식 요소가 포함된 템플릿 클래스 [basic_string](../standard-library/basic-string-class.md)의 특수화를 설명하는 형식입니다.  
  
 `basic_string`을 특수화하는 기타 형식 정의에는 [string](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string), [u32string](../standard-library/string-typedefs.md#u32string) 등이 있습니다.  
  
```cpp  
typedef basic_string<wchar_t, char_traits<wchar_t>, allocator<wchar_t>> wstring;
```  
  
### <a name="remarks"></a>설명  
 아래의 코드 두 줄은 동일한 선언입니다.  
  
```cpp  
wstring wstr(L"");

basic_string<wchar_t> wstr(L"");
```  
  
 문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.  
  
> [!NOTE]
>  `wchar_t`의 크기는 구현 시 정의됩니다. 코드에서 `wchar_t`가 특정 크기여야 하는 경우 `sizeof(wchar_t)` 등을 사용하여 플랫폼 구현을 확인하세요. 모든 플랫폼에서 너비가 동일하게 유지되도록 보장되는 문자열 문자 형식이 필요한 경우에는 [string](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string) 또는 [u32string](../standard-library/string-typedefs.md#u32string)을 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<string>](../standard-library/string.md)



