---
title: "&lt;regex&gt; 형식 정의 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cmatch
- std::cmatch
- regex/std::cmatch
- cregex_iterator
- std::cregex_iterator
- regex/std::cregex_iterator
- cregex_token_iterator
- std::cregex_token_iterator
- regex/std::cregex_token_iterator
- csub_match
- std::csub_match
- regex/std::csub_match
- regex
- std::regex
- regex/std::regex
- smatch
- std::smatch
- regex/std::smatch
- sregex_iterator
- std::sregex_iterator
- regex/std::sregex_iterator
- sregex_token_iterator
- std::sregex_token_iterator
- regex/std::sregex_token_iterator
- ssub_match
- std::ssub_match
- regex/std::ssub_match
- wcmatch
- std::wcmatch
- regex/std::wcmatch
- wcregex_iterator
- std::wcregex_iterator
- regex/std::wcregex_iterator
- wcregex_token_iterator
- std::wcregex_token_iterator
- regex/std::wcregex_token_iterator
- wcsub_match
- std::wcsub_match
- regex/std::wcsub_match
- wregex
- std::wregex
- regex/std::wregex
- wsmatch
- std::wsmatch
- regex/std::wsmatch
- wsregex_iterator
- std::wsregex_iterator
- regex/std::wsregex_iterator
- wsregex_token_iterator
- std::wsregex_token_iterator
- regex/std::wsregex_token_iterator
- wssub_match
- std::wssub_match
- regex/std::wssub_match
ms.assetid: e6a69067-106c-4a24-9e08-7c867a3a2260
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 41b445ceeeb1f37ee9873cb55f62d30d480d8718
ms.openlocfilehash: 60822dd232399b27ccda3db829b636d817091a2d
ms.lasthandoff: 02/24/2017

---
# <a name="ltregexgt-typedefs"></a>&lt;regex&gt; 형식 정의
||||  
|-|-|-|  
|[cmatch 형식 정의](#cmatch_typedef)|[cregex_iterator 형식 정의](#cregex_iterator_typedef)|[cregex_token_iterator 형식 정의](#cregex_token_iterator_typedef)|  
|[csub_match 형식 정의](#csub_match_typedef)|[regex 형식 정의](#regex_typedef)|[smatch 형식 정의](#smatch_typedef)|  
|[sregex_iterator 형식 정의](#sregex_iterator_typedef)|[sregex_token_iterator 형식 정의](#sregex_token_iterator_typedef)|[ssub_match 형식 정의](#ssub_match_typedef)|  
|[wcmatch 형식 정의](#wcmatch_typedef)|[wcregex_iterator 형식 정의](#wcregex_iterator_typedef)|[wcregex_token_iterator 형식 정의](#wcregex_token_iterator_typedef)|  
|[wcsub_match 형식 정의](#wcsub_match_typedef)|[wregex 형식 정의](#wregex_typedef)|[wsmatch 형식 정의](#wsmatch_typedef)|  
|[wsregex_iterator 형식 정의](#wsregex_iterator_typedef)|[wsregex_token_iterator 형식 정의](#wsregex_token_iterator_typedef)|[wssub_match 형식 정의](#wssub_match_typedef)|  
  
##  <a name="a-namecmatchtypedefa--cmatch-typedef"></a><a name="cmatch_typedef"></a>  cmatch 형식 정의  
 char match_results에 대한 형식 정의입니다.  
  
```  
typedef match_results<const char*> cmatch;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `const char*` 형식의 반복기에 대한 템플릿 클래스 [match_results 클래스](../standard-library/match-results-class.md)의 특수화를 설명합니다.  
  
##  <a name="a-namecregexiteratortypedefa--cregexiterator-typedef"></a><a name="cregex_iterator_typedef"></a>  cregex_iterator 형식 정의  
 char regex_iterator에 대한 형식 정의입니다.  
  
```  
typedef regex_iterator<const char*> cregex_iterator;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `const char*` 형식의 반복기에 대한 템플릿 클래스 [regex_iterator 클래스](../standard-library/regex-iterator-class.md)의 특수화를 설명합니다.  
  
##  <a name="a-namecregextokeniteratortypedefa--cregextokeniterator-typedef"></a><a name="cregex_token_iterator_typedef"></a>  cregex_token_iterator 형식 정의  
 char regex_token_iterator에 대한 형식 정의  
  
```  
typedef regex_token_iterator<const char*> cregex_token_iterator;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `const char*` 형식의 반복기에 대한 템플릿 클래스 [regex_token_iterator 클래스](../standard-library/regex-token-iterator-class.md)의 특수화를 설명합니다.  
  
##  <a name="a-namecsubmatchtypedefa--csubmatch-typedef"></a><a name="csub_match_typedef"></a>  csub_match 형식 정의  
 char sub_match에 대한 형식 정의입니다.  
  
```  
typedef sub_match<const char*> csub_match;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `const char*` 형식의 반복기에 대한 템플릿 클래스 [sub_match 클래스](../standard-library/sub-match-class.md)의 특수화를 설명합니다.  
  
##  <a name="a-nameregextypedefa--regex-typedef"></a><a name="regex_typedef"></a>  regex 형식 정의  
 char basic_regex에 대한 형식 정의입ㄴ니다.  
  
```  
typedef basic_regex<char> regex;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `char` 형식의 반복기에 대한 템플릿 클래스 [basic_regex 클래스](../standard-library/basic-regex-class.md)의 특수화를 설명합니다.  
  
> [!NOTE]
>  높은 비트 문자의 경우 `regex`에서 예기치 않은 결과가 반환됩니다. 0~127 범위를 벗어나는 값을 사용하는 경우 정의되지 않은 동작이 발생할 수 있습니다.  
  
##  <a name="a-namesmatchtypedefa--smatch-typedef"></a><a name="smatch_typedef"></a>  smatch 형식 정의  
 string match_results에 대한 형식 정의입니다.  
  
```  
typedef match_results<string::const_iterator> smatch;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `string::const_iterator` 형식의 반복기에 대한 템플릿 클래스 [match_results 클래스](../standard-library/match-results-class.md)의 특수화를 설명합니다.  
  
##  <a name="a-namesregexiteratortypedefa--sregexiterator-typedef"></a><a name="sregex_iterator_typedef"></a>  sregex_iterator 형식 정의  
 regex_iterator 문자열에 대한 형식 정의입니다.  
  
```  
typedef regex_iterator<string::const_iterator> sregex_iterator;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `string::const_iterator` 형식의 반복기에 대한 템플릿 클래스 [regex_iterator 클래스](../standard-library/regex-iterator-class.md)의 특수화를 설명합니다.  
  
##  <a name="a-namesregextokeniteratortypedefa--sregextokeniterator-typedef"></a><a name="sregex_token_iterator_typedef"></a>  sregex_token_iterator 형식 정의  
 string regex_token_iterator에 대한 형식 정의입니다.  
  
```  
typedef regex_token_iterator<string::const_iterator> sregex_token_iterator;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `string::const_iterator` 형식의 반복기에 대한 템플릿 클래스 [regex_token_iterator 클래스](../standard-library/regex-token-iterator-class.md)의 특수화를 설명합니다.  
  
##  <a name="a-namessubmatchtypedefa--ssubmatch-typedef"></a><a name="ssub_match_typedef"></a>  ssub_match 형식 정의  
 string sub_match에 대한 형식 정의입니다.  
  
```  
typedef sub_match<string::const_iterator> ssub_match;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `string::const_iterator` 형식의 반복기에 대한 템플릿 클래스 [sub_match 클래스](../standard-library/sub-match-class.md)의 특수화를 설명합니다.  
  
##  <a name="a-namewcmatchtypedefa--wcmatch-typedef"></a><a name="wcmatch_typedef"></a>  wcmatch 형식 정의  
 wchar_t match_results에 대한 형식 정의입니다.  
  
```  
typedef match_results<const wchar_t *> wcmatch;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `const wchar_t*` 형식의 반복기에 대한 템플릿 클래스 [match_results 클래스](../standard-library/match-results-class.md)의 특수화를 설명합니다.  
  
##  <a name="a-namewcregexiteratortypedefa--wcregexiterator-typedef"></a><a name="wcregex_iterator_typedef"></a>  wcregex_iterator 형식 정의  
 wchar_t regex_iterator에 대한 형식 정의입니다.  
  
```  
typedef regex_iterator<const wchar_t*> wcregex_iterator;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `const wchar_t*` 형식의 반복기에 대한 템플릿 클래스 [regex_iterator 클래스](../standard-library/regex-iterator-class.md)의 특수화를 설명합니다.  
  
##  <a name="a-namewcregextokeniteratortypedefa--wcregextokeniterator-typedef"></a><a name="wcregex_token_iterator_typedef"></a>  wcregex_token_iterator 형식 정의  
 wchar_t regex_token_iterator에 대한 형식 정의입니다.  
  
```  
typedef regex_token_iterator<const wchar_t*> wcregex_token_iterator;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `const wchar_t*` 형식의 반복기에 대한 템플릿 클래스 [regex_token_iterator 클래스](../standard-library/regex-token-iterator-class.md)의 특수화를 설명합니다.  
  
##  <a name="a-namewcsubmatchtypedefa--wcsubmatch-typedef"></a><a name="wcsub_match_typedef"></a>  wcsub_match 형식 정의  
 wchar_t sub_match에 대한 형식 정의입니다.  
  
```  
typedef sub_match<const wchar_t*> wcsub_match;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `const wchar_t*` 형식의 반복기에 대한 템플릿 클래스 [sub_match 클래스](../standard-library/sub-match-class.md)의 특수화를 설명합니다.  
  
##  <a name="a-namewregextypedefa--wregex-typedef"></a><a name="wregex_typedef"></a>  wregex 형식 정의  
 wchar_t basic_regex에 대한 형식 정의입니다.  
  
```  
typedef basic_regex<wchar_t> wregex;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `wchar_t` 형식의 반복기에 대한 템플릿 클래스 [basic_regex 클래스](../standard-library/basic-regex-class.md)의 특수화를 설명합니다.  
  
##  <a name="a-namewsmatchtypedefa--wsmatch-typedef"></a><a name="wsmatch_typedef"></a>  wsmatch 형식 정의  
 wstring match_results에 대한 형식 정의입니다.  
  
```  
typedef match_results<wstring::const_iterator> wsmatch;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `wstring::const_iterator` 형식의 반복기에 대한 템플릿 클래스 [match_results 클래스](../standard-library/match-results-class.md)의 특수화를 설명합니다.  
  
##  <a name="a-namewsregexiteratortypedefa--wsregexiterator-typedef"></a><a name="wsregex_iterator_typedef"></a>  wsregex_iterator 형식 정의  
 regex_iterator에 대한 형식 정의입니다.  
  
```  
typedef regex_iterator<wstring::const_iterator> wsregex_iterator;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `wstring::const_iterator` 형식의 반복기에 대한 템플릿 클래스 [regex_iterator 클래스](../standard-library/regex-iterator-class.md)의 특수화를 설명합니다.  
  
##  <a name="a-namewsregextokeniteratortypedefa--wsregextokeniterator-typedef"></a><a name="wsregex_token_iterator_typedef"></a>  wsregex_token_iterator 형식 정의  
 regex_token_iterator에 대한 형식 정의입니다.  
  
```  
typedef regex_token_iterator<wstring::const_iterator> wsregex_token_iterator;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `wstring::const_iterator` 형식의 반복기에 대한 템플릿 클래스 [regex_token_iterator 클래스](../standard-library/regex-token-iterator-class.md)의 특수화를 설명합니다.  
  
##  <a name="a-namewssubmatchtypedefa--wssubmatch-typedef"></a><a name="wssub_match_typedef"></a>  wssub_match 형식 정의  
 wstring sub_match에 대한 형식 정의입니다.  
  
```  
typedef sub_match<wstring::const_iterator> wssub_match;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `wstring::const_iterator` 형식의 반복기에 대한 템플릿 클래스 [sub_match 클래스](../standard-library/sub-match-class.md)의 특수화를 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
[\<regex>](../standard-library/regex.md)  
[regex_constants 클래스](../standard-library/regex-constants-class.md)  
[regex_error 클래스](../standard-library/regex-error-class.md)  
[\<regex> 함수](../standard-library/regex-functions.md)  
[regex_iterator 클래스](../standard-library/regex-iterator-class.md)  
[\<regex> 연산자](../standard-library/regex-operators.md)  
[regex_token_iterator 클래스](../standard-library/regex-token-iterator-class.md)  
[regex_traits 클래스](../standard-library/regex-traits-class.md)  

