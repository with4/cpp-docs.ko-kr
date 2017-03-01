---
title: "basic_ostream 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::basic_ostream
- std.basic_ostream
- ostream/std::basic_ostream
- basic_ostream
dev_langs:
- C++
helpviewer_keywords:
- basic_ostream class
ms.assetid: 5baadc65-b662-4fab-8c9f-94457c58cda1
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 73cde54e382bb04b82739239bd0f07142c5b3321
ms.lasthandoff: 02/24/2017

---
# <a name="basicostream-class"></a>basic_ostream 클래스
이 템플릿 클래스는 문자 특성이 **Tr**([traits_type](../standard-library/basic-ios-class.md#basic_ios__traits_type)이라고도 함)에 의해 결정되는 **Elem**([char_type](../standard-library/basic-ios-class.md#basic_ios__char_type)이라고도 함) 형식의 요소가 있는 스트림 버퍼에 요소 및 인코드된 개체의 삽입을 제어하는 개체를 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Elem, class Tr = char_traits<Elem>>  
class basic_ostream : virtual public basic_ios<Elem, Tr>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Elem`  
 `char_type`  
  
 `Tr`  
 문자 `traits_type`입니다.  
  
## <a name="remarks"></a>설명  
 [operator<<](#basic_ostream__operator_lt__lt_)를 오버로드하는 대부분의 멤버 함수는 형식이 지정된 출력 함수입니다. 다음 패턴을 따릅니다.  
  
```  
iostate state = goodbit;  
const sentry ok(*this);

if (ok)  
 {try  
 {<convert and insert elements  
    accumulate flags in state> }  
    catch (...)  
 {try  
 {setstate(badbit);

}  
    catch (...)  
 {}  
    if ((exceptions()& badbit) != 0)  
    throw; }}  
width(0);
// Except for operator<<(Elem)  
setstate(state);

return (*this);
```  
  
 다른 두 멤버 함수는 형식이 지정되지 않은 출력 함수입니다. 다음 패턴을 따릅니다.  
  
```  
iostate state = goodbit;  
const sentry ok(*this);

if (!ok)  
    state |= badbit;  
else  
 {try  
 {<obtain and insert elements  
    accumulate flags in state> }  
    catch (...)  
 {try  
 {setstate(badbit);

}  
    catch (...)  
 {}  
    if ((exceptions()& badbit) != 0)  
    throw; }}  
setstate(state);

return (*this);
```  
  
 두 함수 그룹은 요소를 삽입하는 동안 오류가 발생하는 경우 [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)**(badbit)**를 호출합니다.  
  
 basic_istream\< **Elem**, **Tr**> 클래스의 개체는 [basic_ios](../standard-library/basic-ios-class.md)**\<Elem**, **Tr>** 클래스의 가상 공용 기준 개체만 저장합니다.  
  
## <a name="example"></a>예제  
 출력 스트림에 대한 자세한 내용은 [basic_ofstream 클래스](../standard-library/basic-ofstream-class.md)에 대한 예제를 참조하세요.  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[basic_ostream](#basic_ostream__basic_ostream)|`basic_ostream` 개체를 생성합니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[flush](#basic_ostream__flush)|버퍼를 플러시합니다.|  
|[put](#basic_ostream__put)|스트림에 문자를 넣습니다.|  
|[seekp](#basic_ostream__seekp)|출력 스트림 내의 위치를 다시 설정합니다.|  
|[sentry](#basic_ostream__sentry)|중첩 클래스는 선언에서 형식이 지정된 출력 함수 및 형식이 지정되지 않은 출력 함수를 구성하는 개체를 설명합니다.|  
|[swap](#basic_ostream__operator_eq)|이 `basic_ostream` 개체의 값을 제공된 `basic_ostream` 개체의 값으로 교환합니다.|  
|[tellp](#basic_ostream__tellp)|출력 스트림 내의 위치를 보고합니다.|  
|[write](#basic_ostream__write)|스트림에 문자를 넣습니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[operator=](#basic_ostream_operator_eq)|제공된 `basic_ostream` 개체 매개 변수의 값을 이 개체에 할당합니다.|  
|[operator<<](#basic_ostream_operator_lt_lt_)|스트림에 씁니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** \<ostream>  
  
 **네임스페이스:** std  
  
##  <a name="a-namebasicostreambasicostreama--basicostreambasicostream"></a><a name="basic_ostream__basic_ostream"></a>  basic_ostream::basic_ostream  
 `basic_ostream` 개체를 생성합니다.  
  
```  
explicit basic_ostream(
    basic_streambuf<Elem, Tr>* strbuf,  
    bool _Isstd = false);

basic_ostream(basic_ostream&& right);
```  
  
### <a name="parameters"></a>매개 변수  
 ` strbuf`  
 [basic_streambuf](../standard-library/basic-streambuf-class.md) 형식의 개체입니다.  
  
 `_Isstd`  
표준 스트림인 경우  `true`, 아닌 경우 `false`입니다.  
  
 ` right`  
 `basic_ostream` 형식의 개체에 대한 rvalue 참조입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 생성자는 [init](../standard-library/basic-ios-class.md#basic_ios__init)(` strbuf`)를 호출하여 기본 개체를 초기화합니다. 두 번째 생성자는 [basic_ios::move](../standard-library/basic-ios-class.md#basic_ios__move)`(`` right``)`를 호출하여 기본 개체를 초기화합니다.  
  
### <a name="example"></a>예제  
  출력 스트림에 대한 자세한 내용은 [basic_ofstream::basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream__basic_ofstream)에 대한 예제를 참조하세요.  
  
##  <a name="a-namebasicostreamflusha--basicostreamflush"></a><a name="basic_ostream__flush"></a>  basic_ostream::flush  
 버퍼를 플러시합니다.  
  
```  
basic_ostream<Elem, Tr>& flush();
```  
  
### <a name="return-value"></a>반환 값  
 Basic_ostream 개체에 대한 참조입니다.  
  
### <a name="remarks"></a>설명  
 [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf)가 null 포인터가 아닌 경우 함수는 **rdbuf->**[pubsync](../standard-library/basic-streambuf-class.md#basic_streambuf__pubsync)를 호출합니다. -1이 반환되는 경우 함수는 [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)(**badbit**)를 호출합니다. 그런 다음 **\*this**를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// basic_ostream_flush.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout << "test";  
   cout.flush();  
}  
```  
  
```Output  
test  
```  
  
##  <a name="a-namebasicostreamoperatorltlta--basicostreamoperatorltlt"></a><a name="basic_ostream_operator_lt_lt_"></a>  basic_ostream::operator&lt;&lt;  
 스트림에 씁니다.  
  
```  
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& (* Pfn)(basic_ostream<Elem, Tr>&));

basic_ostream<Elem, Tr>& operator<<(
    ios_base& (* Pfn)(ios_base&));

basic_ostream<Elem, Tr>& operator<<(
    basic_ios<Elem, Tr>& (* Pfn)(basic_ios<Elem, Tr>&));

basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
basic_ostream<Elem, Tr>& operator<<(bool val);
basic_ostream<Elem, Tr>& operator<<(short val);
basic_ostream<Elem, Tr>& operator<<(unsigned short val);
basic_ostream<Elem, Tr>& operator<<(int __w64  val);
basic_ostream<Elem, Tr>& operator<<(unsigned int __w64  val);
basic_ostream<Elem, Tr>& operator<<(long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long __w64  val);
basic_ostream<Elem, Tr>& operator<<(long long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long long val);
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
basic_ostream<Elem, Tr>& operator<<(const void* val);
```  
  
### <a name="parameters"></a>매개 변수  
 `Pfn`  
 함수 포인터입니다.  
  
 ` strbuf`  
 **stream_buf** 개체에 대한 포인터입니다.  
  
 ` val`  
 스트림에 기록할 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 Basic_ostream 개체에 대한 참조입니다.  
  
### <a name="remarks"></a>설명  
 `<ostream>` 헤더는 또한 몇몇 전역 삽입 연산자를 정의합니다. 자세한 내용은 [operator<< (\<ostream>)](../standard-library/ostream-operators.md#operator_lt__lt_)을 참조하세요.  
  
 첫 번째 멤버 함수는 **ostr << endl** 형식의 식이 [endl](../standard-library/ostream-functions.md#endl)**(ostr)**을 호출한 다음 **\*this**를 반환하도록 합니다. 두 번째와 세 번째 함수는 [hex](../standard-library/ios-functions.md#hex)와 같은 기타 조작자가 비슷하게 동작하도록 합니다. 나머지 함수는 모두 형식이 지정된 출력 함수입니다.  
  
 다음 함수는  
  
```  
basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
```  
  
 ` strbuf`가 null 포인터가 아닌 경우 ` strbuf`에서 요소를 추출하여 삽입합니다. 추출은 파일의 끝에서 또는 추출이 예외를 throw하는 경우(다시 throw됨) 중지됩니다. 또한 삽입이 실패하면 문제의 요소를 추출하지 않은 채 중단됩니다. 함수가 요소를 삽입하지 않거나 추출이 예외를 throw하면 함수는 [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)(**failbit**)를 호출합니다. 어떤 경우든 함수는 **\*this**를 반환합니다.  
  
 다음 함수는  
  
```  
basic_ostream<Elem, Tr>& operator<<(bool val);
```  
  
 _ 변환`Val` 부울 필드를 호출 하 여 삽입 [use_facet](../standard-library/basic-filebuf-class.md#basic_filebuf__open)**<>\<Elem, OutIt >**`(`[getloc](../standard-library/ios-base-class.md#ios_base__getloc)). [put](#basic_ostream__put)(**OutIt**([rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf)), **\*this**, `getloc`, **val**). 여기서 **OutIt**는 [ostreambuf_iterator](../standard-library/ostreambuf-iterator-class.md)**\<Elem, Tr>**로 정의됩니다. 함수는 **\*this**를 반환합니다.  
  
 다음 함수는  
  
```  
basic_ostream<Elem, Tr>& operator<<(short val);
basic_ostream<Elem, Tr>& operator<<(unsigned short val);
basic_ostream<Elem, Tr>& operator<<(int val);
basic_ostream<Elem, Tr>& operator<<(unsigned int __w64  val);
basic_ostream<Elem, Tr>& operator<<(long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long val);
basic_ostream<Elem, Tr>& operator<<(long long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long long val);
basic_ostream<Elem, Tr>& operator<<(const void* val);
```  
  
 각 변환 ` val` 숫자 필드를 호출 하 여 삽입 **use_facet<>\<Elem, OutIt >**(`getloc`). **put**(**OutIt**(`rdbuf`), **\*this**, `getloc`, **val**). 여기서 **OutIt**는 **ostreambuf_iterator\<Elem, Tr>**로 정의됩니다. 함수는 **\*this**를 반환합니다.  
  
 다음 함수는  
  
```  
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
```  
  
 각각 `val`을 숫자 필드로 변환하고 **use_facet<num_put\<Elem, OutIt>**(`getloc`)**. put**(**OutIt**(`rdbuf`), **\*this**, `getloc`, **val**)을 호출하여 삽입합니다. 여기서 **OutIt**는 **ostreambuf_iterator\<Elem, Tr>**로 정의됩니다. 함수는 **\*this**를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// basic_ostream_op_write.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string.h>  
  
using namespace std;  
  
ios_base& hex2( ios_base& ib )  
{  
   ib.unsetf( ios_base::dec );  
   ib.setf( ios_base::hex );  
   return ib;  
}  
  
basic_ostream<char, char_traits<char> >& somefunc(basic_ostream<char, char_traits<char> > &i)
{
    if (i == cout)
    {
        i << "i is cout" << endl;
    }
    return i;
}

class CTxtStreambuf : public basic_streambuf< char, char_traits< char > >
{
public:
    CTxtStreambuf(char *_pszText)
    {
        pszText = _pszText;
        setg(pszText, pszText, pszText + strlen(pszText));
    };
    char *pszText;
};

int main()
{
    cout << somefunc;
    cout << 21 << endl;

    hex2(cout);
    cout << 21 << endl;

    CTxtStreambuf f("text in streambuf");
    cout << &f << endl;
}
```  
  
##  <a name="a-namebasicostreamoperatoreqa--basicostreamoperator"></a><a name="basic_ostream__operator_eq"></a>  basic_ostream::operator=  
 제공된 `basic_ostream` 개체 매개 변수의 값을 이 개체에 할당합니다.  
  
```  
basic_ostream& operator=(basic_ostream&& right);
```  
  
### <a name="parameters"></a>매개 변수  
 ` right`  
 `basic_ostream` 개체에 대한 `rvalue` 참조입니다.  
  
### <a name="remarks"></a>설명  
 멤버 연산자는 swap `(`` right``)`를 호출합니다.  
  
##  <a name="a-namebasicostreamputa--basicostreamput"></a><a name="basic_ostream__put"></a>  basic_ostream::put  
 스트림에 문자를 넣습니다.  
  
```  
basic_ostream<Elem, Tr>& put(char_type _Ch);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Ch`  
 단일 문자입니다.  
  
### <a name="return-value"></a>반환 값  
 Basic_ostream 개체에 대한 참조입니다.  
  
### <a name="remarks"></a>설명  
 형식이 지정되지 않은 출력 함수는 `_Ch` 요소를 삽입합니다. 그런 다음 **\*this**를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// basic_ostream_put.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout.put( 'v' );  
   cout << endl;  
   wcout.put( L'l' );  
}  
```  
  
```Output  
v  
l  
```  
  
##  <a name="a-namebasicostreamseekpa--basicostreamseekp"></a><a name="basic_ostream__seekp"></a>  basic_ostream::seekp  
 출력 스트림 내의 위치를 다시 설정합니다.  
  
```  
basic_ostream<Elem, Tr>& seekp(pos_type _Pos);

basic_ostream<Elem, Tr>& seekp(off_type _Off, ios_base::seekdir _Way);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Pos`  
 스트림 내의 위치입니다.  
  
 `_Off`  
 `_Way` 기준의 오프셋입니다.  
  
 `_Way`  
 [ios_base::seekdir](../standard-library/ios-base-class.md#ios_base__seekdir) 열거형 중 하나입니다.  
  
### <a name="return-value"></a>반환 값  
 Basic_ostream 개체에 대한 참조입니다.  
  
### <a name="remarks"></a>설명  
 [fail](../standard-library/basic-ios-class.md#basic_ios__fail)이 **false**인 경우, 첫 번째 멤버 함수는 일부 `pos_type` 임시 개체 **newpos**에 대해 **newpos =** [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf)**->** [pubseekpos](../standard-library/basic-streambuf-class.md#basic_streambuf__pubseekpos)(_*Pos*)를 호출합니다. **fail**이 false인 경우 두 번째 함수는 **newpos = rdbuf->** [pubseekoff](../standard-library/basic-streambuf-class.md#basic_streambuf__pubseekoff)(*_Off, _Way*)를 호출합니다. 어떤 경우든 (`off_type`)**newpos ==** (`off_type`)(-1)(배치 작업 실패)이면 함수는 **istr.**[setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)(**failbit**)를 호출합니다. 두 함수 모두 **\*this**를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// basic_ostream_seekp.cpp  
// compile with: /EHsc  
#include <fstream>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    ofstream x("basic_ostream_seekp.txt");  
    streamoff i = x.tellp();  
    cout << i << endl;  
    x << "testing";  
    i = x.tellp();  
    cout << i << endl;  
    x.seekp(2);   // Put char in third char position in file  
    x << " ";  
  
    x.seekp(2, ios::end);   // Put char two after end of file  
    x << "z";  
}  
```  
  
```Output  
0  
7  
```  
  
##  <a name="a-namebasicostreamsentrya--basicostreamsentry"></a><a name="basic_ostream__sentry"></a>  basic_ostream::sentry  
 중첩 클래스는 선언에서 형식이 지정된 출력 함수 및 형식이 지정되지 않은 출력 함수를 구성하는 개체를 설명합니다.  
  
class sentry {  
   public:  
   explicit sentry(basic_ostream\<Elem, Tr>& _Ostr); operator bool() const; ~sentry(); };  
  
### <a name="remarks"></a>설명  
 중첩 클래스는 선언에서 형식이 지정된 출력 함수 및 형식이 지정되지 않은 출력 함수를 구성하는 개체를 설명합니다. **ostr.**[good](../standard-library/basic-ios-class.md#basic_ios__good)이 **true**이고 **ostr.**[tie](../standard-library/basic-ios-class.md#basic_ios__tie)가 null 포인터가 아니면 생성자는 **ostr.tie->**[flush](#basic_ostream__flush)를 호출합니다. 그런 다음 생성자는 **ostr.good**에서 반환한 값을 **status**에 저장합니다. 나중에 **operator bool**을 호출하면 저장된 이 값이 전달됩니다.  
  
 `uncaught_exception`이 **false**를 반환하고 [flags](../standard-library/ios-base-class.md#ios_base__flags) **&** [unitbuf](../standard-library/ios-functions.md#unitbuf)가&0;이 아니면 소멸자는 [flush](#basic_ostream__flush)를 호출합니다.  
  
##  <a name="a-namebasicostreamswapa--basicostreamswap"></a><a name="basic_ostream__swap"></a>  basic_ostream::swap  
 이 `basic_ostream` 개체의 값을 제공된 `basic_ostream`의 값으로 교환합니다.  
  
```  
void swap(basic_ostream& right);
```  
  
### <a name="parameters"></a>매개 변수  
 ` right`  
 `basic_ostream` 개체에 대한 참조입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 [basic_ios::swap](../standard-library/basic-ios-class.md#basic_ios__swap)`(`` right``)`를 호출하여 이 개체의 내용을 ` right`의 내용으로 교환합니다.  
  
##  <a name="a-namebasicostreamtellpa--basicostreamtellp"></a><a name="basic_ostream__tellp"></a>  basic_ostream::tellp  
 출력 스트림 내의 위치를 보고합니다.  
  
```  
pos_type tellp();
```  
  
### <a name="return-value"></a>반환 값  
 출력 스트림 내의 위치입니다.  
  
### <a name="remarks"></a>설명  
 [fail](../standard-library/basic-ios-class.md#basic_ios__fail)이 **false**인 경우 멤버 함수는 [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf)**->** [pubseekoff](../standard-library/basic-streambuf-class.md#basic_streambuf__pubseekoff)(0, `cur`, **in**)을 반환합니다. 아닌 경우 `pos_type`(-1)를 반환합니다.  
  
### <a name="example"></a>예제  
  `tellp` 사용 예제는 [seekp](#basic_ostream__seekp)를 참조하세요.  
  
##  <a name="a-namebasicostreamwritea--basicostreamwrite"></a><a name="basic_ostream__write"></a>  basic_ostream::write  
 스트림에 문자를 넣습니다.  
  
```  
basic_ostream<Elem, Tr>& write(const char_type* str, streamsize count);
```  
  
### <a name="parameters"></a>매개 변수  
 ` count`  
 스트림에 넣을 문자의 수입니다.  
  
 ` str`  
 스트림에 넣을 문자입니다.  
  
### <a name="return-value"></a>반환 값  
 Basic_ostream 개체에 대한 참조입니다.  
  
### <a name="remarks"></a>설명  
 [형식이 지정되지 않은 출력 함수](../standard-library/basic-ostream-class.md)는 ` str`에서 시작하여 ` count`개 요소의 시퀀스를 삽입합니다.  
  
### <a name="example"></a>예제  
  `write` 사용 예제는 [streamsize](../standard-library/ios-typedefs.md#streamsize)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)


