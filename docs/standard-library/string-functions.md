---
title: "&lt;string&gt; 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- string/std::getline
- string/std::stod
- string/std::stof
- string/std::stoi
- string/std::stol
- string/std::stold
- string/std::stoll
- string/std::stoul
- string/std::stoull
- string/std::swap
- string/std::to_string
- string/std::to_wstring
ms.assetid: 1a4ffd11-dce5-4cc6-a043-b95de034c7c4
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::getline [C++]
- std::stod [C++]
- std::stof [C++]
- std::stoi [C++]
- std::stol [C++]
- std::stold [C++]
- std::stoll [C++]
- std::stoul [C++]
- std::stoull [C++]
- std::swap [C++]
- std::to_string [C++]
- std::to_wstring [C++]
ms.workload: cplusplus
ms.openlocfilehash: 9b1d77b464ea9e9ab4ca6e9511836c490c1c622a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ltstringgt-functions"></a>&lt;string&gt; functions
||||  
|-|-|-|  
|[getline](#getline)|[stod](#stod)|[stof](#stof)|  
|[stoi](#stoi)|[stol](#stol)|[stold](#stold)|  
|[stoll](#stoll)|[stoul](#stoul)|[stoull](#stoull)|  
|[swap](#swap)|[to_string](#to_string)|[to_wstring](#to_wstring)|  
  
##  <a name="getline"></a>  getline  
 입력 스트림에서 문자열을 한 줄씩 추출합니다.  
  
```  
// (1) delimiter as parameter  
template <class CharType, class Traits, class Allocator>  
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& is,  
    basic_string<CharType, Traits, Allocator>& str, 
    CharType delim);

 
template <class CharType, class Traits, class Allocator>  
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>&& is,  
    basic_string<CharType, Traits, Allocator>& str, 
    const CharType delim);

 
// (2) default delimiter used  
template <class CharType, class Traits, class Allocator>  
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& is,  
    basic_string<CharType, Traits, Allocator>& str);

 
template <class Allocator, class Traits, class Allocator>  
basic_istream<Allocator, Traits>& getline(
    basic_istream<Allocator, Traits>&& is,  
    basic_string<Allocator, Traits, Allocator>& str);
```  
  
### <a name="parameters"></a>매개 변수  
 `is`  
 문자열을 추출할 입력 스트림입니다.  
  
 `str`  
 입력 스트림에서 문자를 읽어들일 문자열입니다.  
  
 `delim`  
 줄 구분 기호입니다.  
  
### <a name="return-value"></a>반환 값  
 입력 스트림 `is`입니다.  
  
### <a name="remarks"></a>설명  
 `(1)`로 표시된 함수 시그니처 쌍은 `is`이 발견될 때까지 `delim`에서 문자를 추출하여 `str`에 저장합니다.  
  
 `(2)`로 표시된 함수 시그니처 쌍은 줄 바꿈 문자를 기본 줄 구분 기호로 사용하며 **getline**( `is`, `str`, `is`. `widen`(' `\n`'))으로 동작합니다.  
  
 각 쌍의 두 번째 함수는 [value 참조](../cpp/lvalues-and-rvalues-visual-cpp.md)를 지원하기 위한 첫 번째 함수와 유사한 버전입니다.  
  
 다음 중 하나가 발생하면 추출이 중지됩니다.  
  
-   파일의 끝에 도달하는 경우. 그러면 `is`의 내부 상태 플래그가 `ios_base::eofbit`로 설정됩니다.  
  
-   함수가 요소를 추출해서 비교한 결과 **delim**과 같은 것으로 확인되는 경우. 해당 요소는 되돌려지지도 않고 제어되는 시퀀스에 추가되지도 않습니다.  
  
-   함수가 `str.`[max_size](../standard-library/basic-string-class.md#max_size) 요소를 추출한 후. 그러면 `is`의 내부 상태 플래그가 `ios_base::failbit`로 설정됩니다.  
  
-   위에 나와 있지 않은 기타 오류가 발생하는 경우. 그러면 `is`의 내부 상태 플래그가 `ios_base::badbit`로 설정됩니다.  
  
 내부 상태 플래그에 대한 자세한 내용은 [ios_base::iostate](../standard-library/ios-base-class.md#iostate)를 참조하세요.  
  
 함수가 요소를 추출하지 않으면 `is`의 내부 상태 플래그는 `ios_base::failbit`로 설정됩니다. 어떤 경우든 `getline`은 `is`를 반환합니다.  
  
 예외가 throw되어도 `is` 및 `str`은 유효한 상태로 유지됩니다.  
  
### <a name="example"></a>예  
  다음 코드에서는 `getline()`을 두 가지 모드에서 보여 줍니다. 첫 번째 모드에서는 기본 구분 기호(줄 바꿈 문자)를 사용하고 두 번째 모드에서는 공백을 구분 기호로 사용합니다. 파일의 끝 문자(키보드에서 CTRL+Z를 누름)를 사용하여 while 루프 종료를 제어합니다. 그러면 `cin`의 내부 상태 플래그가 `eofbit`로 설정되며, [basic_ios::clear()](../standard-library/basic-ios-class.md#clear)를 사용하여 이 상태를 해제해야 두 번째 while 루프가 정상적으로 작동합니다.  
  
```cpp  
// compile with: /EHsc /W4  
#include <string>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main()  
{  
    string str;  
    vector<string> v1;  
    cout << "Enter a sentence, press ENTER between sentences. (Ctrl-Z to stop): " << endl;  
    // Loop until end-of-file (Ctrl-Z) is input, store each sentence in a vector.  
    // Default delimiter is the newline character.  
    while (getline(cin, str)) {  
        v1.push_back(str);  
    }  
  
    cout << "The following input was stored with newline delimiter:" << endl;  
    for (const auto& p : v1) {  
        cout << p << endl;  
    }  
  
    cin.clear();  
  
    vector<string> v2;  
    // Now try it with a whitespace delimiter  
    while (getline(cin, str, ' ')) {  
        v2.push_back(str);  
    }  
  
    cout << "The following input was stored with whitespace as delimiter:" << endl;  
    for (const auto& p : v2) {  
        cout << p << endl;  
    }  
}  
  
```  
  
##  <a name="stod"></a>  stod  
 문자 시퀀스를 `double`으로 변환합니다.  
  
```  
double stod(
    const string& str,   
    size_t* idx = 0);

double stod(
    const wstring& str,   
    size_t* idx = 0  
;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`str`|변환할 문자 시퀀스입니다.|  
|`idx`|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|  
  
### <a name="return-value"></a>반환 값  
 `double` 값입니다.  
  
### <a name="remarks"></a>설명  
 함수는 `str`을 호출하는 것처럼 `val`의 요소 시퀀스를 `double` 형식의 `strtod( str.c_str(), _Eptr)` 값으로 변환합니다. 여기서 `_Eptr`은 함수 내부의 개체입니다. ` str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 반면 `idx`가 null 포인터가 아닌 경우 함수는 `*_Eptr -  str.c_str()`에 `*idx`을 저장하고 `val`을 반환합니다.  
  
##  <a name="stof"></a>  stof  
 문자 시퀀스를 float로 변환합니다.  
  
```  
float stof(
    const string& str,   
    size_t* idx = 0);

float stof(
    const wstring& str,   
    size_t* idx = 0);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`str`|변환할 문자 시퀀스입니다.|  
|`idx`|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|  
  
### <a name="return-value"></a>반환 값  
 float 값입니다.  
  
### <a name="remarks"></a>설명  
 함수는 `str`을 호출하는 것처럼 `val`의 요소 시퀀스를 `float` 형식의 `strtof( str.c_str(), _Eptr)` 값으로 변환합니다. 여기서 `_Eptr`은 함수 내부의 개체입니다. ` str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 반면 `idx`가 null 포인터가 아닌 경우 함수는 `*_Eptr -  str.c_str()`에 `*idx`을 저장하고 `val`을 반환합니다.  
  
##  <a name="stoi"></a>  stoi  
 문자 시퀀스를 정수로 변환합니다.  
  
```  
int stoi(
    const string& str,   
    size_t* idx = 0,  
    int base = 10);

int stoi(
    const wstring& str,   
    size_t* idx = 0,  
    int base = 10);
```  
  
### <a name="return-value"></a>반환 값  
 정수 값입니다.  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`str`|변환할 문자 시퀀스입니다.|  
|`idx`|반환 시 변환되지 않은 첫 번째 문자의 인덱스를 포함합니다.|  
|`base`|사용할 기수입니다.|  
  
### <a name="remarks"></a>설명  
 `stoi` 함수는 `str`의 문자 시퀀스를 `int` 형식 값으로 변환하고 값을 반환합니다. 예를 들어 문자 시퀀스 "10" 전달 시 `stoi`에서 반환하는 값은 정수 10입니다.  
  
 `stoi`는 `strtol` 방식으로 호출하는 경우 싱글바이트 문자에 대해 `strtol( str.c_str(), _Eptr, idx)` 함수와 비슷하게 동작하고, `_Eptr` 방식으로 호출하는 경우에는 와이드 문자에 대해 `wcstol` 함수와 비슷하게 동작합니다. 여기서 `wcstol(Str.c_str(), _Eptr, idx)`은 함수 내부의 개체입니다. 자세한 내용은 [strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)을 참조하세요.  
  
 경우 `str.c_str() == *_Eptr`, `stoi` 형식의 개체가 throw `invalid_argument`합니다. 이러한 호출에서는 `errno`를 설정하거나, 반환되는 값을`int` 형식의 개체로 나타낼 수 없는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 반면 `idx`가 null 포인터가 아닌 경우 함수는 `*_Eptr - str.c_str()`에 `*idx`을 저장합니다.  
  
##  <a name="stol"></a>  stol  
 문자 시퀀스를 `long`으로 변환합니다.  
  
```  
long stol(
    const string& str,  
    size_t* idx = 0,  
    int base = 10);

long stol(
    const wstring& str,   
    size_t* idx = 0,  
    int base = 10);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`str`|변환할 문자 시퀀스입니다.|  
|`idx`|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|  
|`base`|사용할 기수입니다.|  
  
### <a name="return-value"></a>반환 값  
 long 정수 값입니다.  
  
### <a name="remarks"></a>설명  
 함수는 `str`을 호출하는 것처럼 `val`의 요소 시퀀스를 `long` 형식의 `strtol( str.c_str(), _Eptr, idx)` 값으로 변환합니다. 여기서 `_Eptr`은 함수 내부의 개체입니다. ` str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 반면 `idx`가 null 포인터가 아닌 경우 함수는 `*_Eptr -  str.c_str()`에 `*idx`을 저장하고 `val`을 반환합니다.  
  
##  <a name="stold"></a>  stold  
 문자 시퀀스를 `long double`으로 변환합니다.  
  
```  
double stold(
    const string& str,   
    size_t* idx = 0);

double stold(
    const wstring& str,   
    size_t* idx = 0);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`str`|변환할 문자 시퀀스입니다.|  
|`idx`|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|  
  
### <a name="return-value"></a>반환 값  
 `long double` 값입니다.  
  
### <a name="remarks"></a>설명  
 함수는 `str`을 호출하는 것처럼 `val`의 요소 시퀀스를 `long double` 형식의 `strtold( str.c_str(), _Eptr)` 값으로 변환합니다. 여기서 `_Eptr`은 함수 내부의 개체입니다. ` str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 반면 `idx`가 null 포인터가 아닌 경우 함수는 `*_Eptr -  str.c_str()`에 `*idx`을 저장하고 `val`을 반환합니다.  
  
##  <a name="stoll"></a>  stoll  
 문자 시퀀스를 `long long`으로 변환합니다.  
  
```  
long long stoll(
    const string& str,   
    size_t* idx = 0,  
    int base = 10);

long long stoll(
    const wstring& str,   
    size_t* idx = 0,  
    int base = 10);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`str`|변환할 문자 시퀀스입니다.|  
|`idx`|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|  
|`base`|사용할 기수입니다.|  
  
### <a name="return-value"></a>반환 값  
 `long long` 값입니다.  
  
### <a name="remarks"></a>설명  
 함수는 `str`을 호출하는 것처럼 `val`의 요소 시퀀스를 `long long` 형식의 `strtoll( str.c_str(), _Eptr, idx)` 값으로 변환합니다. 여기서 `_Eptr`은 함수 내부의 개체입니다. ` str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 반면 `idx`가 null 포인터가 아닌 경우 함수는 `*_Eptr -  str.c_str()`에 `*idx`을 저장하고 `val`을 반환합니다.  
  
##  <a name="stoul"></a>  stoul  
 문자 시퀀스를 부호 없는 long으로 변환합니다.  
  
```  
unsigned long stoul(
    const string& str,   
    size_t* idx = 0,  
    int base = 10);

unsigned long stoul(
    const wstring& str,   
    size_t* idx = 0,  
    int base = 10);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`str`|변환할 문자 시퀀스입니다.|  
|`idx`|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|  
|`base`|사용할 기수입니다.|  
  
### <a name="return-value"></a>반환 값  
 부호 없는 long 정수 값입니다.  
  
### <a name="remarks"></a>설명  
 함수는 `str`을 호출하는 것처럼 `val`의 요소 시퀀스를 `unsigned long` 형식의 `strtoul( str.c_str(), _Eptr, idx)` 값으로 변환합니다. 여기서 `_Eptr`은 함수 내부의 개체입니다. ` str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 반면 `idx`가 null 포인터가 아닌 경우 함수는 `*_Eptr -  str.c_str()`에 `*idx`을 저장하고 `val`을 반환합니다.  
  
##  <a name="stoull"></a>  stoull  
 문자 시퀀스를 `unsigned long long`으로 변환합니다.  
  
```  
unsigned long long stoull(
    const string& str,   
    size_t* idx = 0,  
    int base = 10);

unsigned long long stoull(
    const wstring& str,   
    size_t* idx = 0,  
    int base = 10);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`str`|변환할 문자 시퀀스입니다.|  
|`idx`|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|  
|`base`|사용할 기수입니다.|  
  
### <a name="return-value"></a>반환 값  
 `unsigned long long` 값입니다.  
  
### <a name="remarks"></a>설명  
 함수는 `str`을 호출하는 것처럼 `val`의 요소 시퀀스를 `unsigned long long` 형식의 `strtoull( str.c_str(), _Eptr, idx)` 값으로 변환합니다. 여기서 `_Eptr`은 함수 내부의 개체입니다. ` str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 반면 `idx`가 null 포인터가 아닌 경우 함수는 `*_Eptr -  str.c_str()`에 `*idx`을 저장하고 `val`을 반환합니다.  
  
##  <a name="swap"></a>  swap  
 두 문자열의 문자 배열을 교환합니다.  
  
```  
template <class Traits, class Allocator>  
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 요소를 다른 문자열의 요소와 교환할 단일 문자열입니다.  
  
 `right`  
 요소가 첫 번째 문자열과 교환되는 다른 문자열입니다.  
  
### <a name="remarks"></a>설명  
 특수 멤버 함수를 실행 하는 템플릿 함수 *왼쪽*.[ 스왑](../standard-library/basic-string-class.md#swap)(*오른쪽*) 문자열에 대해 고정적 복잡성 보장 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// string_swap.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   // Declaring an object of type basic_string<char>  
   string s1 ( "Tweedledee" );  
   string s2 ( "Tweedledum" );  
   cout << "Before swapping string s1 and s2:" << endl;  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   swap ( s1 , s2 );  
   cout << "\nAfter swapping string s1 and s2:" << endl;  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
}  
```  
  
```Output  
Before swapping string s1 and s2:  
The basic_string s1 = Tweedledee.  
The basic_string s2 = Tweedledum.  
  
After swapping string s1 and s2:  
The basic_string s1 = Tweedledum.  
The basic_string s2 = Tweedledee.  
```  
  
##  <a name="to_string"></a>  to_string  
 값을 `string`로 변환합니다.  
  
```  
string to_string(int Val);
string to_string(unsigned int Val);
string to_string(long Val);
string to_string(unsigned long Val);
string to_string(long long Val);
string to_string(unsigned long long Val);
string to_string(float Val);
string to_string(double Val);
string to_string(long double Val);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`Val`|변환할 값입니다.|  
  
### <a name="return-value"></a>반환 값  
 값을 나타내는 `string`입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 `Val`가 있는 위치에서 `Buf`를 호출하는 것과 같이 `sprintf(Buf, Fmt, Val)`을 함수 내부의 배열 개체 `Fmt`에 저장된 요소 시퀀스로 변환합니다.  
  
- `"%d"`이 `Val` 형식일 경우 `int`  
  
- `"%u"`이 `Val` 형식일 경우 `unsigned int`  
  
- `"%ld"`이 `Val` 형식일 경우 `long`  
  
- `"%lu"`이 `Val` 형식일 경우 `unsigned long`  
  
- `"%lld"`이 `Val` 형식일 경우 `long long`  
  
- `"%llu"`이 `Val` 형식일 경우 `unsigned long long`  
  
- `"%f"`이 `Val` 또는 `float` 형식일 경우 `double`  
  
- `"%Lf"`이 `Val` 형식일 경우 `long double`  
  
 함수에서 `string(Buf)`을 반환합니다.  
  
##  <a name="to_wstring"></a>  to_wstring  
 값을 와이드 문자열로 변환합니다.  
  
```  
wstring to_wstring(int Val);
wstring to_wstring(unsigned int Val);
wstring to_wstring(long Val);
wstring to_wstring(unsigned long Val);
wstring to_wstring(long long Val);
wstring to_wstring(unsigned long long Val);
wstring to_wstring(float Val);
wstring to_wstring(double Val);
wstring to_wstring(long double Val);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`Val`|변환할 값입니다.|  
  
### <a name="return-value"></a>반환 값  
 값을 나타내는 와이드 문자열입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 `Val`가 있는 위치에서 `Buf`를 호출하는 것과 같이 `swprintf(Buf, Len, Fmt, Val)`을 함수 내부의 배열 개체 `Fmt`에 저장된 요소 시퀀스로 변환합니다.  
  
- `L"%d"`이 `Val` 형식일 경우 `int`  
  
- `L"%u"`이 `Val` 형식일 경우 `unsigned int`  
  
- `L"%ld"`이 `Val` 형식일 경우 `long`  
  
- `L"%lu"`이 `Val` 형식일 경우 `unsigned long`  
  
- `L"%lld"`이 `Val` 형식일 경우 `long long`  
  
- `L"%llu"`이 `Val` 형식일 경우 `unsigned long long`  
  
- `L"%f"`이 `Val` 또는 `float` 형식일 경우 `double`  
  
- `L"%Lf"`이 `Val` 형식일 경우 `long double`  
  
 함수에서 `wstring(Buf)`을 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<string>](../standard-library/string.md)

