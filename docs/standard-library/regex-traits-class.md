---
title: "regex_traits 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- regex/std::regex_traits
- regex/std::regex_traits::char_type
- regex/std::regex_traits::size_type
- regex/std::regex_traits::string_type
- regex/std::regex_traits::locale_type
- regex/std::regex_traits::char_class_type
- regex/std::regex_traits::length
- regex/std::regex_traits::translate
- regex/std::regex_traits::translate_nocase
- regex/std::regex_traits::transform
- regex/std::regex_traits::transform_primary
- regex/std::regex_traits::lookup_classname
- regex/std::regex_traits::lookup_collatename
- regex/std::regex_traits::isctype
- regex/std::regex_traits::value
- regex/std::regex_traits::imbue
- regex/std::regex_traits::getloc
dev_langs:
- C++
helpviewer_keywords:
- std::regex_traits [C++]
- std::regex_traits [C++], char_type
- std::regex_traits [C++], size_type
- std::regex_traits [C++], string_type
- std::regex_traits [C++], locale_type
- std::regex_traits [C++], char_class_type
- std::regex_traits [C++], length
- std::regex_traits [C++], translate
- std::regex_traits [C++], translate_nocase
- std::regex_traits [C++], transform
- std::regex_traits [C++], transform_primary
- std::regex_traits [C++], lookup_classname
- std::regex_traits [C++], lookup_collatename
- std::regex_traits [C++], isctype
- std::regex_traits [C++], value
- std::regex_traits [C++], imbue
- std::regex_traits [C++], getloc
ms.assetid: bc5a5eed-32fc-4eb7-913d-71c42e729e81
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 267461681ef3d70e1ac6d30867c86d8f33a58faa
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="regextraits-class"></a>regex_traits 클래스
일치를 위해 요소의 특징을 설명합니다.  
  
## <a name="syntax"></a>구문  
```  
template<class Elem>
class regex_traits {  
public:  
   typedef Elem char_type;  
   typedef size_t size_type;  
   typedef basic_string<Elem> string_type;  
   typedef locale locale_type;  
   typedef ctype_base::mask char_class_type;  

   regex_traits();
   static size_type length(const char_type *str);
   char_type translate(char_type ch) const;
   char_type translate_nocase(char_type ch) const;
   template <class FwdIt>  
   string_type transform(FwdIt first, FwdIt last) const;
   template <class FwdIt>  
   string_type transform_primary(FwdIt first, FwdIt last) const;
   template <class FwdIt>  
   char_class_type lookup_classname(FwdIt first, FwdIt last) const;
   template <class FwdIt>  
   string_type lookup_collatename(FwdIt first, FwdIt last) const;
   bool isctype(char_type ch, char_class_type cls) const;
   int value(char_type ch, int base) const;
   locale_type imbue(locale_type loc);
   locale_type getloc() const;
};  
 ``` 
#### <a name="parameters"></a>매개 변수  
 `Elem`  
 설명할 문자 요소 형식입니다.  
  
## <a name="remarks"></a>설명  
 템플릿 클래스는 `Elem`형식의 다양한 정규식 특성을 설명합니다. 템플릿 클래스 [basic_regex 클래스](../standard-library/basic-regex-class.md)는 이 정보를 사용하여 `Elem` 형식의 요소를 조작합니다.  
  
 각 `regex_traits` 개체는 일부 멤버 함수에서 사용되는 `regex_traits::locale` 형식의 개체를 보유합니다. 기본 로캘은 `regex_traits::locale()`의 복사본입니다. 멤버 함수 `imbue` 는 로캘 개체를 대체하고, 멤버 함수 `getloc` 는 로캘 개체의 복사본을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<regex>  
  
 **네임스페이스:** std  
  
##  <a name="char_class_type"></a>  regex_traits::char_class_type  
 문자 클래스 지정자의 형식입니다.  
  
```  
typedef T8 char_class_type;  
```  
  
### <a name="remarks"></a>설명  
 형식은 문자 클래스를 지정하는 지정되지 않은 형식의 동의어입니다. `|` 연산자를 사용하여 이 형식의 값을 결합하면 피연산자가 지정한 클래스의 합집합인 문자 클래스를 지정할 수 있습니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__regex__regex_traits_char_class_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="char_type"></a>  regex_traits::char_type  
 요소의 형식입니다.  
  
```  
typedef Elem char_type;  
```  
  
### <a name="remarks"></a>설명  
 typedef는 템플릿 인수 `Elem`의 동의어입니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__regex__regex_traits_char_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="getloc"></a>  regex_traits::getloc  
 저장된 로캘 개체를 반환합니다.  
  
```  
locale_type getloc() const;
```  
  
### <a name="remarks"></a>설명  
 멤버 함수는 저장된 `locale` 개체를 반환합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__regex__regex_traits_getloc.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="imbue"></a>  regex_traits::imbue  
 저장된 로캘 개체를 변경합니다.  
  
```  
locale_type imbue(locale_type loc);
```  
  
### <a name="parameters"></a>매개 변수  
 `loc`  
 저장할 로캘 개체입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 `loc` 를 저장된 `locale` 개체에 복사하고 저장된 `locale` 개체의 이전 값에 대한 복사본을 반환합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__regex__regex_traits_imbue.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="isctype"></a>  regex_traits::isctype  
 클래스 멤버 자격을 테스트합니다.  
  
```  
bool isctype(char_type ch, char_class_type cls) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `ch`  
 테스트할 요소입니다.  
  
 `cls`  
 테스트할 클래스입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 `ch` 문자가 `cls`로 지정된 문자 클래스에 있는 경우에만 true를 반환합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__regex__regex_traits_isctype.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="length"></a>  regex_traits::length  
 nul로 끝나는 시퀀스의 길이를 반환합니다.  
  
```  
static size_type length(const char_type *str);
```  
  
### <a name="parameters"></a>매개 변수  
 `str`  
 nul로 끝나는 시퀀스입니다.  
  
### <a name="remarks"></a>설명  
 정적 멤버 함수는 `std::char_traits<char_type>::length(str)`를 반환합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__regex__regex_traits_length.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="locale_type"></a>  regex_traits::locale_type  
 저장된 로캘 개체의 형식입니다.  
  
```  
typedef T7 locale_type;  
```  
  
### <a name="remarks"></a>설명  
 typedef는 로캘을 캡슐화하는 형식의 동의어입니다. 특수화 `regex_traits<char>` 및 `regex_traits<wchar_t>` 에서 `std::locale`의 동의어입니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__regex__regex_traits_locale_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="lookup_classname"></a>  regex_traits::lookup_classname  
 시퀀스를 문자 클래스에 매핑합니다.  
  
```  
template <class FwdIt>  
char_class_type lookup_classname(FwdIt first, FwdIt last) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `first`  
 조회할 시퀀스의 시작입니다.  
  
 `last`  
 조회할 시퀀스의 끝입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 해당 인수가 가리키는 문자 시퀀스로 이름이 지정된 문자 클래스를 지정하는 값을 반환합니다. 값은 시퀀스에 있는 문자의 대/소문자에 따라 달라지지 않습니다.  
  
 특수화 `regex_traits<char>`는 모두 대/소문자를 무시하고 `"d"`, `"s"`, `"w"`, `"alnum"`, `"alpha"`, `"blank"`, `"cntrl"`, `"digit"`, `"graph"`, `"lower"`, `"print"`, `"punct"`, `"space"`, `"upper"` 및 `"xdigit"` 이름을 인식합니다.  
  
 특수화 `regex_traits<wchar_t>`는 모두 대/소문자를 무시하고 `L"d"`, `L"s"`, `L"w"`, `L"alnum"`, `L"alpha"`, `L"blank"`, `L"cntrl"`, `L"digit"`, `L"graph"`, `L"lower"`, `L"print"`, `L"punct"`, `L"space"`, `L"upper"` 및 `L"xdigit"` 이름을 인식합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__regex__regex_traits_lookup_classname.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="lookup_collatename"></a>  regex_traits::lookup_collatename  
 데이터 정렬 요소에 시퀀스를 매핑합니다.  
  
```  
template <class FwdIt>  
string_type lookup_collatename(FwdIt first, FwdIt last) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `first`  
 조회할 시퀀스의 시작입니다.  
  
 `last`  
 조회할 시퀀스의 끝입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 `[first, last)`시퀀스에 해당하는 데이터 정렬 요소를 포함하는 문자열 개체를 반환하거나, 시퀀스가 유효한 데이터 정렬 요소가 아닌 경우 빈 문자열을 반환합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__regex__regex_traits_lookup_collatename.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="regex_traits"></a>  regex_traits::regex_traits  
 개체를 생성합니다.  
  
```  
regex_traits();
```  
  
### <a name="remarks"></a>설명  
 생성자는 저장된 `locale` 개체가 기본 로캘로 초기화되는 개체를 생성합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__regex__regex_traits_construct.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="size_type"></a>  regex_traits::size_type  
 시퀀스 길이의 형식입니다.  
  
```  
typedef T6 size_type;  
```  
  
### <a name="remarks"></a>설명  
 typedef는 부호 없는 정수 형식의 동의어입니다. 특수화 `regex_traits<char>` 및 `regex_traits<wchar_t>`에서 `std::size_t`의 동의어입니다.  
  
 typedef는 `std::size_t`의 동의어입니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__regex__regex_traits_size_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="string_type"></a>  regex_traits::string_type  
 요소 문자열의 형식입니다.  
  
```  
typedef basic_string<Elem> string_type;  
```  
  
### <a name="remarks"></a>설명  
 typedef는 `basic_string<Elem>`의 동의어입니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__regex__regex_traits_string_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="transform"></a>  regex_traits::transform  
 정렬된 해당 시퀀스로 변환합니다.  
  
```  
template <class FwdIt>  
string_type transform(FwdIt first, FwdIt last) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `first`  
 변환할 시퀀스의 시작입니다.  
  
 `last`  
 변환할 시퀀스의 끝입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 저장된 `locale` 개체에 따라 달라지는 변환 규칙을 사용하여 생성하는 문자열을 반환합니다. 반복기 범위 `[first1, last1)` 및 `[first2, last2)`로 지정된 두 문자 시퀀스에 대해, 반복기 범위 `transform(first1, last1) < transform(first2, last2)` 로 지정된 문자 시퀀스가 반복기 범위 `[first1, last1)` 로 지정된 문자 시퀀스보다 먼저 정렬되면 `[first2, last2)`입니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__regex__regex_traits_transform.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="transform_primary"></a>  regex_traits::transform_primary  
 정렬된 해당 caseless 시퀀스로 변환합니다.  
  
```  
template <class FwdIt>  
string_type transform_primary(FwdIt first, FwdIt last) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `first`  
 변환할 시퀀스의 시작입니다.  
  
 `last`  
 변환할 시퀀스의 끝입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 저장된 `locale` 개체에 따라 달라지는 변환 규칙을 사용하여 생성하는 문자열을 반환합니다. 반복기 범위 `[first1, last1)` 및 `[first2, last2)`로 지정된 두 문자 시퀀스에 대해, 반복기 범위 `transform_primary(first1, last1) < transform_primary(first2, last2)` 로 지정된 문자 시퀀스가 대/소문자 또는 악센트에 관계없이 반복기 범위 `[first1, last1)` 로 지정된 문자 시퀀스보다 먼저 정렬되면 `[first2, last2)` 입니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__regex__regex_traits_transform_primary.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="translate"></a>  regex_traits::translate  
 일치하는 해당 요소로 변환합니다.  
  
```  
char_type translate(char_type ch) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `ch`  
 변환할 요소입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 저장된 `locale` 개체에 따라 달라지는 변환 규칙을 사용하여 생성하는 문자를 반환합니다. 두 `char_type` 개체 `ch1` 및 `ch2`의 경우 하나는 정규식 정의에 나타나고 다른 하나는 대/소문자를 구분하는 일치에 대한 대상 시퀀스의 해당 위치에 나타날 때 `translate(ch1) == translate(ch2)` 및 `ch1` 가 일치해야 하는 경우에만 `ch2` 입니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__regex__regex_traits_translate.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="translate_nocase"></a>  regex_traits::translate_nocase  
 해당 caseless 일치하는 요소로 변환합니다.  
  
```  
char_type translate_nocase(char_type ch) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `ch`  
 변환할 요소입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 저장된 `locale` 개체에 따라 달라지는 변환 규칙을 사용하여 생성하는 문자를 반환합니다. 두 `char_type` 개체 `ch1` 및 `ch2`의 경우 하나는 정규식 정의에 나타나고 다른 하나는 대/소문자를 구분하지 않는 일치에 대한 대상 시퀀스의 해당 위치에 나타날 때 `translate_nocase(ch1) == translate_nocase(ch2)` 및 `ch1` 가 일치해야 하는 경우에만 `ch2` 입니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__regex__regex_traits_translate_nocase.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="value"></a>  regex_traits::value  
 요소를 숫자 값으로 변환합니다.  
  
```  
int value(Elem ch, int radix) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `ch`  
 변환할 요소입니다.  
  
 `radix`  
 사용할 기본 산술입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 기본 `ch` 에서 `radix`문자로 표시된 값 또는 `ch` 가 기본 `radix`에서 유효한 숫자가 아닌 경우 -1을 반환합니다. 함수는 8, 10 또는 16의 `radix` 인수로만 호출됩니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__regex__regex_traits_value.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
## <a name="see-also"></a>참고 항목  
[\<regex>](../standard-library/regex.md)  
[regex_constants 클래스](../standard-library/regex-constants-class.md)  
[regex_error 클래스](../standard-library/regex-error-class.md)  
[\<regex> 함수](../standard-library/regex-functions.md)  
[regex_iterator 클래스](../standard-library/regex-iterator-class.md)  
[\<regex> 연산자](../standard-library/regex-operators.md)  
[regex_token_iterator 클래스](../standard-library/regex-token-iterator-class.md)  
[\<regex> 형식 정의](../standard-library/regex-typedefs.md)  
 [regex_traits\<char> 클래스](../standard-library/regex-traits-char-class.md)   
 [regex_traits\<wchar_t> 클래스](../standard-library/regex-traits-wchar-t-class.md)

