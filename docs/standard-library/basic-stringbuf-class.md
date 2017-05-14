---
title: "basic_stringbuf 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- basic_stringbuf
- sstream/std::basic_stringbuf
- sstream/std::basic_stringbuf::allocator_type
- sstream/std::basic_stringbuf::char_type
- sstream/std::basic_stringbuf::int_type
- sstream/std::basic_stringbuf::off_type
- sstream/std::basic_stringbuf::pos_type
- sstream/std::basic_stringbuf::traits_type
- sstream/std::basic_stringbuf::overflow
- sstream/std::basic_stringbuf::pbackfail
- sstream/std::basic_stringbuf::seekoff
- sstream/std::basic_stringbuf::seekpos
- sstream/std::basic_stringbuf::str
- sstream/std::basic_stringbuf::underflow
dev_langs:
- C++
helpviewer_keywords:
- basic_stringbuf class
ms.assetid: 40c85f9e-42a5-4a65-af5c-23c8e3bf8113
caps.latest.revision: 28
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: b8d19f4cd76690c52dd6a69df04240944c151f67
ms.contentlocale: ko-kr
ms.lasthandoff: 04/29/2017

---
# <a name="basicstringbuf-class"></a>basic_stringbuf 클래스
배열 개체에 저장된 요소의 시퀀스에서 문자 특성이 `Tr` 클래스에 의해 결정되는 `Elem` 형식 요소의 전송을 제어하는 스트림 버퍼에 대해 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Elem, class Tr = char_traits<Elem>,   
    class Alloc = allocator<Elem>>  
class basic_stringbuf : public basic_streambuf<Elem, Tr>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Alloc`  
 할당자 클래스입니다.  
  
 `Elem`  
 문자열 기본 요소의 형식입니다.  
  
 `Tr`  
 문자열의 기본 요소에서 특수화된 문자 특성입니다.  
  
## <a name="remarks"></a>설명  
 시퀀스의 변경 내용을 수용하도록 필요에 따라 개체가 할당, 확장 및 해제됩니다.  
  
 basic_stringbuf< `Elem`, `Tr`, `Alloc`> 클래스의 개체는 해당 생성자에서 `ios_base::`[openmode](../standard-library/ios-base-class.md#openmode) 인수의 복사본을 해당 `stringbuf` 모드 **mode**로 저장합니다.  
  
-   `mode & ios_base::in`이 0이 아닌 경우 입력 버퍼에 액세스할 수 있습니다. 자세한 내용은 [basic_streambuf 클래스](../standard-library/basic-streambuf-class.md)를 참조하세요.  
  
-   `mode & ios_base::out`이 0이 아닌 경우 출력 버퍼에 액세스할 수 있습니다.  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[basic_stringbuf](#basic_stringbuf)|`basic_stringbuf` 형식의 개체를 생성합니다.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[allocator_type](#allocator_type)|이 형식은 템플릿 매개 변수 `Alloc`의 동의어입니다.|  
|[char_type](#char_type)|형식 이름을 `Elem` 템플릿 매개 변수와 연결합니다.|  
|[int_type](#int_type)|`Tr` 범위에 있는 동일한 이름의 형식에 해당하는 `basic_filebuf`의 범위 내에 이 형식을 만듭니다.|  
|[off_type](#off_type)|`Tr` 범위에 있는 동일한 이름의 형식에 해당하는 `basic_filebuf`의 범위 내에 이 형식을 만듭니다.|  
|[pos_type](#pos_type)|`Tr` 범위에 있는 동일한 이름의 형식에 해당하는 `basic_filebuf`의 범위 내에 이 형식을 만듭니다.|  
|[traits_type](#traits_type)|형식 이름을 `Tr` 템플릿 매개 변수와 연결합니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[overflow](#overflow)|가득 찬 버퍼에 새 문자를 삽입할 때 호출할 수 있는 보호된 가상 함수입니다.|  
|[pbackfail](#pbackfail)|보호된 가상 멤버 함수는 요소를 입력 버퍼에 다시 넣은 후 다음 포인터에서 가리키는 현재 요소로 설정하려고 합니다.|  
|[seekoff](#seekoff)|보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 합니다.|  
|[seekpos](#seekpos)|보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 합니다.|  
|[str](#str)|쓰기 위치를 변경하지 않고 문자열 버퍼에서 텍스트를 설정하거나 가져옵니다.|  
|swap||  
|[underflow](#underflow)|입력 스트림에서 현재 요소를 추출하는 보호된 가상 멤버 함수입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<sstream>  
  
 **네임스페이스:** std  
  
##  <a name="allocator_type"></a>  basic_stringbuf::allocator_type  
 이 형식은 템플릿 매개 변수 `Alloc`의 동의어입니다.  
  
```  
typedef Alloc allocator_type;  
```  
  
##  <a name="basic_stringbuf"></a>  basic_stringbuf::basic_stringbuf  
 `basic_stringbuf` 형식의 개체를 생성합니다.  
  
```  
basic_stringbuf(
    ios_base::openmode _Mode = ios_base::in | ios_base::out);

basic_stringbuf(
    const basic_string<Elem, Tr, Alloc>& str,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Mode`  
 [ios_base::openmode](../standard-library/ios-base-class.md#openmode)의 열거형 중 하나입니다.  
  
 `str`  
 [basic_string](../standard-library/basic-string-class.md) 형식의 개체입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 생성자는 입력 버퍼와 출력 버퍼를 제어하는 모든 포인터에 null 포인터를 저장합니다. 자세한 내용은 [basic_streambuf 클래스](../standard-library/basic-streambuf-class.md)의 설명 섹션을 참조하세요. 또한 `_Mode`를 stringbuf 모드로서 저장합니다. 자세한 내용은 [basic_stringbuf 클래스](../standard-library/basic-stringbuf-class.md)의 설명 섹션을 참조하세요.  
  
 두 번째 생성자는 `str` 문자열 객체로 제어되는 시퀀스의 복사본을 할당합니다. `_Mode & ios_base::in`이 0이 아닌 경우 시퀀스 시작 시 읽기를 시작하도록 입력 버퍼를 설정합니다. `_Mode & ios_base::out`이 0이 아닌 경우 시퀀스 시작 시 쓰기를 시작하도록 출력 버퍼를 설정합니다. 또한 `_Mode`를 stringbuf 모드로서 저장합니다. 자세한 내용은 [basic_stringbuf 클래스](../standard-library/basic-stringbuf-class.md)의 설명 섹션을 참조하세요.  
  
##  <a name="char_type"></a>  basic_stringbuf::char_type  
 형식 이름을 **Elem** 템플릿 매개 변수와 연결합니다.  
  
```  
typedef Elem char_type;  
```  
  
##  <a name="int_type"></a>  basic_stringbuf::int_type  
 **Tr** 범위에 있는 동일한 이름의 형식에 해당하는 basic_filebuf의 범위 내에 이 형식을 만듭니다.  
  
```  
typedef typename traits_type::int_type int_type;  
```  
  
##  <a name="off_type"></a>  basic_stringbuf::off_type  
 **Tr** 범위에 있는 동일한 이름의 형식에 해당하는 basic_filebuf의 범위 내에 이 형식을 만듭니다.  
  
```  
typedef typename traits_type::off_type off_type;  
```  
  
##  <a name="overflow"></a>  basic_stringbuf::overflow  
 가득 찬 버퍼에 새 문자를 삽입할 때 호출할 수 있는 보호된 가상 함수입니다.  
  
```  
virtual int_type overflow(int_type _Meta = traits_type::eof());
```  
  
### <a name="parameters"></a>매개 변수  
 `_Meta`  
 버퍼 또는 **traits_type::eof**에 삽입할 문자입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공할 수 없는 경우 **traits_type::eof**를 반환합니다. 아닌 경우 **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*)를 반환합니다.  
  
### <a name="remarks"></a>설명  
 _ *Meta*가 **traits_type::**[eof](../standard-library/char-traits-struct.md#eof)와 비교하여 같지 않은 경우 보호되는 가상 멤버 함수는 **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(\_ *Meta*) 요소를 출력 버퍼에 삽입하려고 합니다. 수행할 수 있는 방법은 다양합니다.  
  
-   쓰기 위치가 사용 가능한 경우 요소를 쓰기 위치에 저장하고 출력 버퍼에 대해 다음 포인터를 증분할 수 있습니다.  
  
-   출력 버퍼에 대해 새 저장소 또는 추가 저장소를 할당하여 쓰기 위치를 사용 가능하게 만들 수 있습니다. 이러한 방식으로 출력 버퍼를 확장하면 연결된 입력 버퍼도 확장됩니다.  
  
##  <a name="pbackfail"></a>  basic_stringbuf::pbackfail  
 보호된 가상 멤버 함수는 요소를 입력 버퍼에 다시 넣은 후 다음 포인터에서 가리키는 현재 요소로 설정하려고 합니다.  
  
```  
virtual int_type pbackfail(int_type _Meta = traits_type::eof());
```  
  
### <a name="parameters"></a>매개 변수  
 `_Meta`  
 버퍼 또는 **traits_type::eof**에 삽입할 문자입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공할 수 없는 경우 **traits_type::eof**를 반환합니다. 아닌 경우 **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*)를 반환합니다.  
  
### <a name="remarks"></a>설명  
 `_Meta`가 **traits_type::**[eof](../standard-library/char-traits-struct.md#eof)와 비교하여 같은 경우 다시 푸시할 요소는 실제로 현재 요소 이전 스트림에 이미 있는 요소입니다. 같지 않은 경우 해당 요소는 **byte** = **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(_ *Meta*)로 바뀝니다. 함수는 여러 가지 방법으로 요소를 다시 넣을 수 있습니다.  
  
-   putback 위치를 사용할 수 있고 여기에 저장된 요소가 byte와 비교 시 같으면 입력 버퍼에 대한 다음 포인터를 감소시킬 수 있습니다.  
  
-   putback 위치를 사용할 수 있고 stringbuf 모드에서 시퀀스를 변경하도록 허용하면 (**mode & ios_base::out**이 0이 아님) 함수는 byte를 putback 위치에 저장하고 입력 버퍼에 대한 다음 포인터를 감소시킬 수 있습니다.  
  
##  <a name="pos_type"></a>  basic_stringbuf::pos_type  
 **Tr** 범위에 있는 동일한 이름의 형식에 해당하는 basic_filebuf의 범위 내에 이 형식을 만듭니다.  
  
```  
typedef typename traits_type::pos_type pos_type;  
```  
  
##  <a name="seekoff"></a>  basic_stringbuf::seekoff  
 보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 합니다.  
  
```  
virtual pos_type seekoff(
    off_type _Off,  
    ios_base::seekdir _Way,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Off`  
 `_Way`를 기준으로 찾을 위치입니다. 자세한 내용은 [basic_stringbuf::off_type](#off_type)을 참조하세요.  
  
 `_Way`  
 오프셋 작업의 시작 지점입니다. 가능한 값은 [ios_base::seekdir](../standard-library/ios-base-class.md#seekdir)을 참조하세요.  
  
 `_Mode`  
 포인터 위치에 대한 모드를 지정합니다. 기본적으로는 읽기 및 쓰기 위치를 수정할 수 있습니다. 자세한 내용은 [ios_base::openmode](../standard-library/ios-base-class.md#openmode)를 참조하세요.  
  
### <a name="return-value"></a>반환 값  
 새 위치 또는 잘못된 스트림 위치를 반환합니다.  
  
### <a name="remarks"></a>설명  
 `basic_stringbuf<Elem, Tr, Alloc>` 클래스 개체의 경우 스트림 위치는 스트림 오프셋으로만 구성됩니다. 오프셋 0은 제어되는 시퀀스의 첫 번째 요소를 지정합니다.  
  
 새 위치는 다음과 같이 결정됩니다.  
  
-   `_Way` == `ios_base::beg`인 경우 새 위치는 스트림 시작 부분에 `_Off`를 더한 위치입니다.  
  
-   `_Way` == `ios_base::cur`인 경우 새 위치는 현재 스트림 위치에 `_Off`를 더한 위치입니다.  
  
-   `_Way` == `ios_base::end`인 경우 새 위치는 스트림 끝에 `_Off`를 더한 위치입니다.  
  
 `_Mode & ios_base::in`이 0이 아닌 경우 함수는 입력 버퍼에서 읽을 다음 위치를 변경합니다. `_Mode & ios_base::out`이 0이 아닌 경우 함수는 출력 버퍼에서 읽을 다음 위치를 변경합니다. 스트림이 영향을 받으려면 버퍼가 존재해야 합니다. 위치 지정 작업을 정상적으로 수행하려면 결과 스트림 위치가 제어되는 시퀀스 내에 있어야 합니다. 함수가 두 스트림 위치에 모두 영향을 미치는 경우 `_Way`는 `ios_base::beg` 또는 `ios_base::end`여야 하며 두 스트림은 동일한 요소에 배치됩니다. 아닌 경우(또는 두 위치 모두 영향을 받지 않는 경우) 배치 작업이 실패합니다.  
  
 두 스트림 위치 중 하나 또는 모두를 정상적으로 변경하는 경우 함수는 결과 스트림 위치를 반환합니다. 아닌 경우 함수는 실패하며 잘못된 스트림 위치를 반환합니다.  
  
##  <a name="seekpos"></a>  basic_stringbuf::seekpos  
 보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 합니다.  
  
```  
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Sp`  
 찾을 위치입니다.  
  
 `_Mode`  
 포인터 위치에 대한 모드를 지정합니다. 기본적으로는 읽기 및 쓰기 위치를 수정할 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 두 스트림 위치 중 하나 또는 모두를 정상적으로 변경하는 경우 함수는 결과 스트림 위치를 반환합니다. 아닌 경우 함수는 실패하며 잘못된 스트림 위치를 반환합니다. 스트림 위치가 잘못되었는지를 확인하려면 반환 값을 `pos_type(off_type(-1))`과 비교합니다.  
  
### <a name="remarks"></a>설명  
 basic_stringbuf< **Elem**, **Tr**, `Alloc`> 클래스 개체의 경우 스트림 위치는 스트림 오프셋으로만 구성됩니다. 오프셋 0은 제어되는 시퀀스의 첫 번째 요소를 지정합니다. 새 위치는 _ *Sp*에 의해 결정됩니다.  
  
 **mode & ios_base::in**이 0이 아닌 경우 함수는 입력 버퍼에서 읽을 다음 위치를 변경합니다. **mode & ios_base::out**이 0이 아닌 경우 함수는 입력 버퍼에서 읽을 다음 위치를 변경합니다. 스트림이 영향을 받으려면 버퍼가 존재해야 합니다. 위치 지정 작업을 정상적으로 수행하려면 결과 스트림 위치가 제어되는 시퀀스 내에 있어야 합니다. 아닌 경우(또는 두 위치 모두 영향을 받지 않는 경우) 배치 작업이 실패합니다.  
  
##  <a name="str"></a>  basic_stringbuf::str  
 쓰기 위치를 변경하지 않고 문자열 버퍼에서 텍스트를 설정하거나 가져옵니다.  
  
```  
basic_string<Elem, Tr, Alloc> str() const;
void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Newstr`  
 새 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 [basic_string](../standard-library/basic-string-class.md)\< **Elem**, **Tr**, Alloc **>,** 클래스의 개체를 반환합니다. 이 개체의 제어된 시퀀스는 **\*this**에 의해 제어된 시퀀스의 복사본입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 멤버 함수는 basic_string< **Elem**, **Tr**, `Alloc`> 클래스의 개체를 반환합니다. 이 개체의 제어된 시퀀스는 **\*this**에 의해 제어된 시퀀스의 복사본입니다. 복사되는 시퀀스는 저장된 stringbuf 모드에 따라 달라집니다.  
  
-   **mode & ios_base::out**이 0이고 출력 버퍼가 존재하는 경우 시퀀스는 전체 출력 버퍼입니다(`pbase`로 시작되는 [epptr](../standard-library/basic-streambuf-class.md#epptr) - [pbase](../standard-library/basic-streambuf-class.md#pbase) 요소).  
  
-   **mode & ios_base::in**이 0이 아니고 입력 버퍼가 존재하는 경우 시퀀스는 전체 입력 버퍼입니다(`eback`으로 시작되는 [egptr](../standard-library/basic-streambuf-class.md#egptr) - [eback](../standard-library/basic-streambuf-class.md#eback) 요소).  
  
-   아닌 경우 복사된 시퀀스는 비어 있습니다.  
  
 두 번째 멤버 함수는 현재 **\*this**에 의해 제어되는 시퀀스의 할당을 취소합니다. 그런 다음 `_Newstr`에 의해 제어되는 시퀀스의 복사본을 할당합니다. **mode & ios_base::in**이 0이 아닌 경우 시퀀스 시작 시 읽기를 시작하도록 입력 버퍼를 설정합니다. **mode & ios_base::out**이 0이 아닌 경우 시퀀스 시작 시 쓰기를 시작하도록 출력 버퍼를 설정합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// basic_stringbuf_str.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <sstream>  
  
using namespace std;  
  
int main( )   
{  
   basic_string<char> i( "test" );  
   stringstream ss;  
  
   ss.rdbuf( )->str( i );  
   cout << ss.str( ) << endl;  
  
   ss << "z";  
   cout << ss.str( ) << endl;  
  
   ss.rdbuf( )->str( "be" );  
   cout << ss.str( ) << endl;  
}  
```  
  
```Output  
test  
zest  
be  
```  
  
##  <a name="traits_type"></a>  basic_stringbuf::traits_type  
 형식 이름을 **Tr** 템플릿 매개 변수와 연결합니다.  
  
```  
typedef Tr traits_type;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 템플릿 매개 변수 **Tr**의 동의어입니다.  
  
##  <a name="underflow"></a>  basic_stringbuf::underflow  
 입력 스트림에서 현재 요소를 추출하는 보호된 가상 함수입니다.  
  
```  
virtual int_type underflow();
```  
  
### <a name="return-value"></a>반환 값  
 성공하지 못할 경우 함수는 **traits_type::**[eof](../standard-library/char-traits-struct.md#eof)를 반환합니다. 성공할 경우, 변환된 입력 스트림의 현재 요소를 반환합니다.  
  
### <a name="remarks"></a>설명  
 보호된 가상 멤버 함수는 입력 버퍼에서 현재 요소 **byte** 추출을 시도한 다음 현재 스트림 위치로 이동하여 요소를 **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( **byte**)로서 반환합니다. 이 경우 한 가지 방법을 사용할 수 있습니다. 읽기 위치를 사용할 수 있으면 함수는 읽기 위치에 저장된 요소로 **byte**를 가져온 후 입력 버퍼의 다음 포인터로 이동합니다.  
  
##  <a name="swap"></a>  basic_streambuf::swap  
 이 문자열 버퍼의 내용을 다른 문자열 버퍼로 바꿉니다.  
  
```  
void basic_stringbuf<T>::swap(basic_stringbuf& other)  
```  
  
### <a name="parameters"></a>매개 변수  
 `other`  
 해당 내용이 이 basic_stringbuf로 바뀌는 basic_stringbuf입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="op_eq"></a>  basic_stringbuf::operator=  
 연산자 우변의 basic_stringbuf 내용을 좌변의 basic_stringbuf에 할당합니다.  
  
```  
basic_stringbuf& basic_stringbuf:: operator=(const basic_stringbuf& other)  
```  
  
### <a name="parameters"></a>매개 변수  
 `other`  
 로캘 특성을 포함하여 해당 내용이 연산자 좌변의 stringbuf에 할당되는 basic_stringbuf입니다.  
  
### <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)


