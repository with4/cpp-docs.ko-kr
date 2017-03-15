---
title: "&lt;istream&gt; 연산자 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 4c2a2f8c2c2b55e3c14db9e44a4b05041c0ecfc9
ms.lasthandoff: 02/24/2017

---
# <a name="ltistreamgt-operators"></a>&lt;istream&gt; 연산자
 
##  <a name="a-nameoperatorgtgta--operatorgtgt"></a><a name="operator_gt__gt_"></a>  operator&gt;&gt;  
 스트림에서 문자 및 문자열을 추출합니다.  
  
```  
template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,   
    Elem* str);

template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,   
    Elem& Ch);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    signed char* str);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    signed char& Ch);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    unsigned char* str);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    unsigned char& Ch);

template <class Elem, class Tr, class Type>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,  
    Type& val);
```  
  
### <a name="parameters"></a>매개 변수  
 `Ch`  
 단일 문자입니다.  
  
 `Istr`  
 스트림입니다.  
  
 ` str`  
 문자열  
  
 ` val`  
 형식입니다.  
  
### <a name="return-value"></a>반환 값  
 스트림  
  
### <a name="remarks"></a>설명  
 `basic_istream` 클래스도 여러 가지 추출 연산자를 정의합니다. 자세한 내용은 [basic_istream::operator>>](../standard-library/basic-istream-class.md#basic_istream__operator_gt__gt_)를 참조하세요.  
  
 템플릿 함수는 다음과 같습니다.  
  
```cpp  
template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```  
  
 이 함수는 최대 *N* - 1개 요소를 추출하여 _ *Str*에서 시작하는 배열에 저장합니다. `Istr`. [width](../standard-library/ios-base-class.md#ios_base__width)가&0;보다 큰 경우 *N*은 `Istr`. **width**이고, 그러지 않은 경우에는 선언할 수 있는 가장 큰 **Elem** 배열의 크기입니다. 이 함수는 항상 저장하는 추출된 요소 다음에 **Elem()** 값을 저장합니다. 추출은 파일의 끝, **Elem**(0) 값을 갖는 문자(추출되지 않음) 또는 [ws](../standard-library/istream-functions.md#ws)에 의해 삭제될 모든 요소(추출되지 않음)에서 미리 중지됩니다. 함수가 요소를 추출하지 않는 경우 `Istr`. [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**)를 호출합니다. 어떤 경우든 `Istr`. **width**(0)를 호출하고 `Istr`을 반환합니다.  
  
 **보안 정보** 입력 스트림에서 추출할 null로 끝나는 문자열은 대상 버퍼 ` str`의 크기를 초과해서는 안 됩니다. 자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하세요.  
  
 템플릿 함수는 다음과 같습니다.  
  
```cpp  
template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```  
  
 가능한 경우 요소를 추출하여 `Ch`에 저장합니다. 그렇지 않으면 **is**. [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**)를 호출합니다. 어떤 경우든 `Istr`을 반환합니다.  
  
 템플릿 함수는 다음과 같습니다.  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```  
  
 `Istr` >> ( `char`**\***) ` str`을 반환합니다.  
  
 템플릿 함수는 다음과 같습니다.  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```  
  
 `Istr` >> ( **char&**) `Ch`를 반환합니다.  
  
 템플릿 함수는 다음과 같습니다.  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```  
  
 `Istr` >> ( **char \***) ` str`을 반환합니다.  
  
 템플릿 함수는 다음과 같습니다.  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```  
  
 `Istr` >> ( **char&**) `Ch`를 반환합니다.  
  
 템플릿 함수는 다음과 같습니다.  
  
```cpp  
template <class Elem, class Tr, class Type>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,  
    Type& val);
```  
  
 `Istr` `>>` ` val`을 반환하고 프로세스에서 `Istr`에 대한 `rvalue reference`를 `lvalue`로 변환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// istream_op_extract.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   ws( cin );  
   char c[10];  
  
   cin.width( 9 );  
   cin >> c;  
   cout << c << endl;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [\<istream>](../standard-library/istream.md)


