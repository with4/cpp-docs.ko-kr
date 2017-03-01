---
title: "basic_ios 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.basic_ios
- ios/std::basic_ios
- basic_ios
- std::basic_ios
dev_langs:
- C++
helpviewer_keywords:
- basic_ios class
ms.assetid: 4fdcd8e1-62d2-4611-8a70-1e4f58434007
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 6987d9c75785ebb716324395e0ce295d4155e55f
ms.lasthandoff: 02/24/2017

---
# <a name="basicios-class"></a>basic_ios 클래스
이 템플릿 클래스는 템플릿 매개 변수에 따라 달라지는 입력 스트림(템플릿 클래스 [basic_istream](../standard-library/basic-istream-class.md)) 및 출력 스트림(템플릿 클래스 [basic_ostream](../standard-library/basic-ostream-class.md))에 공통된 저장소 및 멤버 함수를 설명합니다. [ios_base](../standard-library/ios-base-class.md) 클래스는 일반적이고 템플릿 매개 변수에 따라 달라지지 않는 사항을 설명합니다. **basic_ios\<class Elem, class Traits>** 클래스의 개체는 **Elem** 형식의 요소가 포함된 스트림을 제어하는 데 도움이 됩니다. 해당 문자 특성은 **Traits** 클래스에 의해 결정됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
 
template <class Elem, class Traits>  
class basic_ios : public ios_base  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Elem`  
 형식입니다.  
  
 `Traits`  
 `char_traits` 형식의 변수입니다.  
  
## <a name="remarks"></a>설명  
 **basic_ios\<class Elem, class Traits>** 클래스의 개체는 다음을 저장합니다.  
  
-   [basic_istream](../standard-library/basic-istream-class.md)**\<Elem, Traits>** 형식의 개체에 대한 연결(tie) 포인터  
  
-   [basic_streambuf](../standard-library/basic-streambuf-class.md)**\<Elem, Traits >** 형식의 개체에 대한 스트림 버퍼 포인터  
  
- [서식 정보](../standard-library/ios-base-class.md)  
  
- [ios_base](../standard-library/ios-base-class.md) 형식의 기준 개체에 있는 [스트림 상태 정보](../standard-library/ios-base-class.md)  
  
-   `char_type` 형식의 개체에 있는 채우기 문자  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[basic_ios](#basic_ios__basic_ios)|`basic_ios` 클래스를 생성합니다.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#basic_ios__char_type)|템플릿 매개 변수 `Elem`의 동의어.|  
|[int_type](#basic_ios__int_type)|`Traits::int_type`의 동의어입니다.|  
|[off_type](#basic_ios__off_type)|`Traits::off_type`의 동의어입니다.|  
|[pos_type](#basic_ios__pos_type)|`Traits::pos_type`의 동의어입니다.|  
|[traits_type](#basic_ios__traits_type)|템플릿 매개 변수 `Traits`의 동의어.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[bad](#basic_ios__bad)|스트림 버퍼의 무결성 손실을 나타냅니다.|  
|[clear](#basic_ios__clear)|오류 플래그를 모두 지웁니다.|  
|[copyfmt](#basic_ios__copyfmt)|스트림 간에 플래그를 복사합니다.|  
|[eof](#basic_ios__eof)|스트림의 끝에 도달했는지 여부를 나타냅니다.|  
|[exceptions](#basic_ios__exceptions)|스트림에서 발생하는 예외를 나타냅니다.|  
|[fail](#basic_ios__fail)|스트림에서 유효한 필드 추출 실패를 나타냅니다.|  
|[fill](#basic_ios__fill)|텍스트가 스트림만큼 넓지 않을 경우 사용할 문자를 지정하거나 반환합니다.|  
|[good](#basic_ios__good)|스트림 상태가 양호함을 나타냅니다.|  
|[imbue](#basic_ios__imbue)|로캘을 변경합니다.|  
|[init](#basic_ios__init)|`basic_ios` 생성자에 의해 호출됩니다.|  
|[move](#basic_ios__move)|스트림 버퍼에 대한 포인터를 제외하고 매개 변수의 모든 값을 현재 개체로 이동합니다.|  
|[narrow](#basic_ios__narrow)|지정된 `char_type`에 해당하는 char를 찾습니다.|  
|[rdbuf](#basic_ios__rdbuf)|스트림을 지정된 버퍼로 라우트합니다.|  
|[rdstate](#basic_ios__rdstate)|플래그에 대한 비트 상태를 읽습니다.|  
|[set_rdbuf](#basic_ios__set_rdbuf)|이 스트림 개체에 대한 읽기 버퍼로 사용할 스트림 버퍼를 할당합니다.|  
|[setstate](#basic_ios__setstate)|추가 플래그를 설정합니다.|  
|[swap](#basic_ios__swap)|이 `basic_ios` 개체의 값을 다른 `basic_ios` 개체의 값으로 교환합니다. 스트림 버퍼에 대한 포인터는 교환되지 않습니다.|  
|[tie](#basic_ios__tie)|한 스트림이 다른 스트림보다 먼저 처리되도록 합니다.|  
|[widen](#basic_ios__widen)|지정된 char에 해당하는 `char_type`을 찾습니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[explicit operator bool](#basic_ios__operator_bool)|`basic_ios` 개체를 `bool`로 사용할 수 있도록 합니다. 일반적이고 의도하지 않은 부작용을 방지하기 위해 자동 형식 변환이 사용되지 않습니다.|  
|[operator void *](#basic_ios__operator_void_star)|스트림 상태가 여전히 양호한지 여부를 나타냅니다.|  
|[operator!](#basic_ios__operator_not)|스트림 상태가 불량이 아닌지 여부를 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<ios>  
  
 **네임스페이스:** std  
  
##  <a name="a-namebasiciosbada--basiciosbad"></a><a name="basic_ios__bad"></a>  basic_ios::bad  
 스트림 버퍼의 무결성 손실을 나타냅니다.  
  
```  
bool bad() const;
```  
  
### <a name="return-value"></a>반환 값  
 `rdstate & badbit`가&0;이 아닌 경우 `true`,&0;인 경우 `false`입니다.  
  
 `badbit`에 대한 자세한 내용은 [ios_base::iostate](../standard-library/ios-base-class.md#ios_base__iostate)를 참조하세요.  
  
### <a name="example"></a>예제  
  
```cpp  
// basic_ios_bad.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( void )  
{  
  using namespace std;  
  bool b = cout.bad( );  
  cout << boolalpha;  
  cout << b << endl;  
    
  b = cout.good( );  
  cout << b << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosbasiciosa--basiciosbasicios"></a><a name="basic_ios__basic_ios"></a>  basic_ios::basic_ios  
 basic_ios 클래스를 생성합니다.  
  
```   
explicit basic_ios(basic_streambuf<Elem,  Traits>* sb);
basic_ios();
```  
  
### <a name="parameters"></a>매개 변수  
 `sb`  
 입력 또는 출력 요소를 저장할 표준 버퍼입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 생성자는 [init](#basic_ios__init)(_ *Sb*)를 호출하여 멤버 개체를 초기화합니다. 보호된 두 번째 생성자는 멤버 개체를 초기화하지 않은 채 유지합니다. 나중에 **init**를 호출할 경우 개체가 안전하게 삭제되기 전에 개체를 초기화해야 합니다.  
  
##  <a name="a-namebasicioschartypea--basicioschartype"></a><a name="basic_ios__char_type"></a>  basic_ios::char_type  
 **Elem** 템플릿 매개 변수의 동의어입니다.  
  
```   
typedef Elem char_type;  
```  
  
##  <a name="a-namebasicioscleara--basiciosclear"></a><a name="basic_ios__clear"></a>  basic_ios::clear  
 오류 플래그를 모두 지웁니다.  
  
```   
void clear(iostate state = goodbit, bool reraise = false); 
void clear(io_state state);
```  
  
### <a name="parameters"></a>매개 변수  
 `state`(선택 사항)  
 모든 플래그를 지운 후에 설정할 플래그입니다. 기본값은 `goodbit`입니다.  
  
 `reraise`(선택 사항)  
 예외를 다시 발생시킬지 여부를 지정합니다. 기본값은 `false`입니다(예외를 다시 발생시키지 않음).  
  
### <a name="remarks"></a>설명  
 플래그는 **goodbit**, **failbit**, **eofbit** 및 **badbit**입니다. [good](#basic_ios__good), [bad](#basic_ios__bad), [eof](#basic_ios__eof) 및 [fail](#basic_ios__fail)을 사용하여 이러한 플래그를 테스트합니다.  
  
 멤버 함수는 저장된 스트림 상태 정보를 다음 코드로 바꿉니다.  
  
 `state` &#124; `(`[rdbuf](#basic_ios__rdbuf) != 0 **goodbit** : **badbit**)  
  
 `state`**&**[exceptions](#basic_ios__exceptions)가&0;이 아니면 [failure](../standard-library/ios-base-class.md#ios_base__failure) 클래스 개체를 throw합니다.  
  
### <a name="example"></a>예제  
  **clear**를 사용하는 방법의 예는 [rdstate](#basic_ios__rdstate) 및 [getline](../standard-library/string-functions.md#getline)을 참조하세요.  
  
##  <a name="a-namebasicioscopyfmta--basicioscopyfmt"></a><a name="basic_ios__copyfmt"></a>  basic_ios::copyfmt  
 스트림 간에 플래그를 복사합니다.  
  
```   
basic_ios<Elem, Traits>& copyfmt(
const basic_ios<Elem, Traits>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 ` right`  
 플래그를 복사하려는 스트림입니다.  
  
### <a name="return-value"></a>반환 값  
 플래그를 복사 중인 스트림에 대한 **this** 개체입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 호출 이벤트 erase_event를 보고합니다. 그런 다음 채움 문자, 연결(tie) 포인터 및 서식 지정 정보를 ` right`에서 **\*this**로 복사합니다. 멤버 함수는 예외 마스크를 변경하기 전에 copyfmt_event 호출 이벤트를 보고합니다. 복사가 완료되고 **state &**[exceptions](#basic_ios__exceptions)가&0;이 아니면, 함수는 실제로 [rdstate](#basic_ios__rdstate) 인수와 함께 [clear](#basic_ios__clear)를 호출합니다. 그런 다음 **\*this**를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp    
// basic_ios_copyfmt.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main( )  
{  
  using namespace std;  
  ofstream x( "test.txt" );  
  int i = 10;  
    
  x << showpos;  
  cout << i << endl;  
  cout.copyfmt( x );  
  cout << i << endl;  
}  
  
```  
  
##  <a name="a-namebasicioseofa--basicioseof"></a><a name="basic_ios__eof"></a>  basic_ios::eof  
 스트림의 끝에 도달했는지 여부를 나타냅니다.  
  
```  
bool eof() const;
```  
  
### <a name="return-value"></a>반환 값  
 스트림의 끝에 도달한 경우 `true`, 아닌 경우 `false`입니다.  
  
### <a name="remarks"></a>설명  
 [rdstate](#basic_ios__rdstate) `& eofbit`가&0;이 아닌 경우 멤버 함수는 `true`를 반환합니다. `eofbit`에 대한 자세한 내용은 [ios_base::iostate](../standard-library/ios-base-class.md#ios_base__iostate)를 참조하세요.  
  
### <a name="example"></a>예제  
  
```cpp    
// basic_ios_eof.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
using namespace std;  
  
int main( int argc, char* argv[] )  
{  
  fstream   fs;  
  int n = 1;  
  fs.open( "basic_ios_eof.txt" );   // an empty file  
  cout << boolalpha  
  cout << fs.eof() << endl;  
  fs >> n;   // Read the char in the file  
  cout << fs.eof() << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosexceptionsa--basiciosexceptions"></a><a name="basic_ios__exceptions"></a>  basic_ios::exceptions  
 스트림에서 발생하는 예외를 나타냅니다.  
  
```   
iostate exceptions() const; 
void exceptions(iostate Newexcept);
void exceptions(io_state Newexcept);
```  
  
### <a name="parameters"></a>매개 변수  
 *Newexcept*  
 예외를 throw하려는 플래그입니다.  
  
### <a name="return-value"></a>반환 값  
 현재 스트림에 대한 예외를 throw하도록 지정된 플래그입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 멤버 함수는 저장된 예외 마스크를 반환합니다. 두 번째 멤버 함수는 예외 마스크에 *_Except*를 저장하고 전에 저장된 값을 반환합니다. 새 예외 마스크를 저장하면 [clear](#basic_ios__clear)( [rdstate](#basic_ios__rdstate) )와 같은 예외가 throw될 수 있습니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// basic_ios_exceptions.cpp  
// compile with: /EHsc /GR  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
    
  cout << cout.exceptions( ) << endl;  
  cout.exceptions( ios::eofbit );  
  cout << cout.exceptions( ) << endl;  
  try  
  {  
    cout.clear( ios::eofbit );   // Force eofbit on  
  }  
  catch ( exception &e )  
  {  
    cout.clear( );  
    cout << "Caught the exception." << endl;  
    cout << "Exception class: " << typeid(e).name()  << endl;  
    cout << "Exception description: " << e.what() << endl;  
  }  
}  
  
```  
  
```Output  
  
0  
1  
Caught the exception.  
Exception class: class std::ios_base::failure  
Exception description: ios_base::eofbit set   
```  
  
##  <a name="a-namebasiciosfaila--basiciosfail"></a><a name="basic_ios__fail"></a>  basic_ios::fail  
 스트림에서 유효한 필드 추출 실패를 나타냅니다.  
  
```  
bool fail() const;
```  
  
### <a name="return-value"></a>반환 값  
 [rdstate](#basic_ios__rdstate) `& (badbit|failbit)`가&0;이 아닌 경우 `true`,&0;인 경우 `false`입니다.  
  
 `failbit`에 대한 자세한 내용은 [ios_base::iostate](../standard-library/ios-base-class.md#ios_base__iostate)를 참조하세요.  
  
### <a name="example"></a>예제  
  
```cpp  
// basic_ios_fail.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( void )  
{  
  using namespace std;  
  bool b = cout.fail( );  
  cout << boolalpha;  
  cout << b << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosfilla--basiciosfill"></a><a name="basic_ios__fill"></a>  basic_ios::fill  
 텍스트가 스트림만큼 넓지 않을 경우 사용할 문자를 지정하거나 반환합니다.  
  
```   
char_type fill() const; 
char_type fill(char_type Char);
```  
  
### <a name="parameters"></a>매개 변수  
 `Char`  
 채우기 문자로 사용할 문자입니다.  
  
### <a name="return-value"></a>반환 값  
 현재 채우기 문자입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 멤버 함수는 저장된 채우기 문자를 반환합니다. 두 번째 멤버 함수는 채우기 문자에 `Char`을 저장하고 전에 저장된 값을 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// basic_ios_fill.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iomanip>  
  
int main( )  
{  
  using namespace std;  
    
  cout << setw( 5 ) << 'a' << endl;     
  cout.fill( 'x' );  
  cout << setw( 5 ) << 'a' << endl;      
  cout << cout.fill( ) << endl;  
}  
  
```  
  
```Output  
  
a  
xxxxa  
x   
```  
  
##  <a name="a-namebasiciosgooda--basiciosgood"></a><a name="basic_ios__good"></a>  basic_ios::good  
 스트림 상태가 양호함을 나타냅니다.  
  
```  
bool good() const;
```  
  
### <a name="return-value"></a>반환 값  
 [rdstate](#basic_ios__rdstate) `== goodbit`인 경우(state 플래그가 설정되지 않음) `true`, 아닌 경우 `false`입니다.  
  
 `goodbit`에 대한 자세한 내용은 [ios_base::iostate](../standard-library/ios-base-class.md#ios_base__iostate)를 참조하세요.  
  
### <a name="example"></a>예제  
  `good`을 사용하는 예는 [basic_ios::bad](#basic_ios__bad)를 참조하세요.  
  
##  <a name="a-namebasiciosimbuea--basiciosimbue"></a><a name="basic_ios__imbue"></a>  basic_ios::imbue  
 로캘을 변경합니다.  
  
```   
locale imbue(const locale& Loc);
```  
  
### <a name="parameters"></a>매개 변수  
 `Loc`  
 로캘 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 이전 로캘입니다.  
  
### <a name="remarks"></a>설명  
 [rdbuf](#basic_ios__rdbuf)가 null 포인터가 아닌 경우 멤버 함수는  
  
 `rdbuf`-> [pubimbue](../standard-library/basic-streambuf-class.md#basic_streambuf__pubimbue)(_ *Loc*)를 호출합니다.  
  
 어느 경우든 [ios_base::imbue](../standard-library/ios-base-class.md#ios_base__imbue)(_ *Loc*)를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// basic_ios_imbue.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <locale>  
  
int main( )  
{  
  using namespace std;  
    
  cout.imbue( locale( "french_france" ) );  
  double x = 1234567.123456;  
  cout << x << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosinita--basiciosinit"></a><a name="basic_ios__init"></a>  basic_ios::init  
 basic_ios 생성자에 의해 호출됩니다.  
  
```  
 
void init(basic_streambuf<Elem,Traits>* _Sb, bool _Isstd = false);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Sb`  
 입력 또는 출력 요소를 저장할 표준 버퍼입니다.  
  
 `_Isstd`  
 표준 스트림인지 여부를 지정합니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 모든 멤버 개체에 값을 저장하므로:  
  
- [rdbuf](#basic_ios__rdbuf)는 *_Sb*를 반환합니다.  
  
- [tie](#basic_ios__tie)는 null 포인터를 반환합니다.  
  
- `_Sb`가&0;이 아닌 경우 [rdstate](#basic_ios__rdstate)는 [goodbit](../standard-library/ios-base-class.md#ios_base__iostate)를 반환하고, 아닌 경우 [badbit](../standard-library/ios-base-class.md#ios_base__iostate)를 반환합니다.  
  
- [exceptions](#basic_ios__exceptions)는 **goodbit**를 반환합니다.  
  
- [flags](../standard-library/ios-base-class.md#ios_base__flags)는 [skipws](../standard-library/ios-base-class.md#ios_base__fmtflags) &#124; [dec](../standard-library/ios-base-class.md#ios_base__fmtflags)를 반환합니다.  
  
- [width](../standard-library/ios-base-class.md#ios_base__width)는 0을 반환합니다.  
  
- [precision](../standard-library/ios-base-class.md#ios_base__precision)은 6을 반환합니다.  
  
- [fill](#basic_ios__fill)은 공백 문자를 반환합니다.  
  
- [getloc](../standard-library/ios-base-class.md#ios_base__getloc)는 `locale::classic`을 반환합니다.  
  
- [iword](../standard-library/ios-base-class.md#ios_base__iword)는&0;을 반환하고, [pword](../standard-library/ios-base-class.md#ios_base__pword)는 모든 인수 값에 대해 null 포인터를 반환합니다.  
  
##  <a name="a-namebasiciosinttypea--basiciosinttype"></a><a name="basic_ios__int_type"></a>  basic_ios::int_type  
 **traits_type::int_type**의 동의어입니다.  
  
```  
typedef typename traits_type::int_type int_type;  
```  
  
##  <a name="a-namebasiciosmovea--basiciosmove"></a><a name="basic_ios__move"></a>  basic_ios::move  
 스트림 버퍼에 대한 포인터를 제외하고 매개 변수의 모든 값을 현재 개체로 이동합니다.  
  
```   
void move(basic_ios&& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `right`  
 값을 이동할 `ios_base` 개체입니다.  
  
### <a name="remarks"></a>설명  
 보호된 멤버 함수는 저장된 `stream buffer pointer`(` right`에서는 변경되지 않고 `*this`에서는 null 포인터로 설정됨)를 제외하고 ` right`에 저장된 모든 값을 `*this`로 이동합니다. 저장된 `tie pointer`는 ` right`에서 null 포인터로 설정됩니다.  
  
##  <a name="a-namebasiciosnarrowa--basiciosnarrow"></a><a name="basic_ios__narrow"></a>  basic_ios::narrow  
 지정된 `char_type`에 해당하는 char를 찾습니다.  
  
```  
 
char narrow(char_type Char, char Default = '\0') const;
```  
  
### <a name="parameters"></a>매개 변수  
 `Char`  
 변환할 `char`입니다.  
  
 `Default`  
 등가가 없는 경우 반환되도록 할 `char`입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 `char_type`에 대한 등가 `char`입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 [use_facet](../standard-library/basic-filebuf-class.md#basic_filebuf__open)**<**Â **ctype**\< **E**> >( [getloc](../standard-library/ios-base-class.md#ios_base__getloc)( ) ). `narrow`( `Char`, `Default`)를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// basic_ios_narrow.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <wchar.h>  
  
int main( )  
{  
  using namespace std;  
  wchar_t *x = L"test";  
  char y[10];  
  cout << x[0] << endl;  
  wcout << x << endl;  
  y[0] = wcout.narrow( x[0] );  
  cout << y[0] << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosofftypea--basiciosofftype"></a><a name="basic_ios__off_type"></a>  basic_ios::off_type  
 **traits_type::off_type**의 동의어입니다.  
  
```  
typedef typename traits_type::off_type off_type;  
```  
  
##  <a name="a-namebasiciosoperatorvoidstara--basiciosoperator-void-"></a><a name="basic_ios__operator_void_star"></a>  basic_ios::operator void *  
 스트림 상태가 여전히 양호한지 여부를 나타냅니다.  
  
```  
 operator void *() const;
```  
  
### <a name="return-value"></a>반환 값  
 연산자는 [fail](#basic_ios__fail)인 경우에만 null 포인터를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// basic_ios_opgood.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
  cout << (bool)(&cout != 0) << endl;   // Stream is still good  
}  
  
```  
  
```Output  
1  
```  
  
##  <a name="a-namebasiciosoperatornota--basiciosoperator"></a><a name="basic_ios__operator_not"></a>  basic_ios::operator!  
 스트림 상태가 불량이 아닌지 여부를 나타냅니다.  
  
```   
bool operator!() const;
```  
  
### <a name="return-value"></a>반환 값  
 [fail](#basic_ios__fail)을 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// basic_ios_opbad.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
  cout << !cout << endl;   // Stream is not bad  
}  
  
```  
  
```Output  
0  
```  
  
##  <a name="a-namebasiciosoperatorboola--basiciosoperator-bool"></a><a name="basic_ios__operator_bool"></a>  basic_ios::operator bool  
 `basic_ios` 개체를 `bool`로 사용할 수 있도록 합니다. 일반적이고 의도하지 않은 부작용을 방지하기 위해 자동 형식 변환이 사용되지 않습니다.  
  
```  
explicit operator bool() const;
```  
  
### <a name="remarks"></a>설명  
 연산자는 `fail``()`인 경우에만 `false`로 변환할 수 있는 값을 반환합니다. 반환 형식은 `bool`로만 변환할 수 있고, `void *` 또는 기타 알려진 스칼라 형식으로는 변환할 수 없습니다.  
  
##  <a name="a-namebasiciospostypea--basiciospostype"></a><a name="basic_ios__pos_type"></a>  basic_ios::pos_type  
 **traits_type::pos_type**의 동의어입니다.  
  
```  
typedef typename traits_type::pos_type pos_type;  
```  
  
##  <a name="a-namebasiciosrdbufa--basiciosrdbuf"></a><a name="basic_ios__rdbuf"></a>  basic_ios::rdbuf  
 스트림을 지정된 버퍼로 라우트합니다.  
  
```   
basic_streambuf<Elem, Traits> *rdbuf() const; 
basic_streambuf<Elem, Traits> *rdbuf(
basic_streambuf<Elem, Traits>* _Sb);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Sb`  
 스트림입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 멤버 함수는 저장된 스트림 버퍼 포인터를 반환합니다.  
  
 두 번째 멤버 함수는 저장된 스트림 버퍼 포인터에 `_Sb`를 저장하고 전에 저장된 값을 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// basic_ios_rdbuf.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <fstream>  
  
int main( )  
{  
  using namespace std;  
  ofstream file( "rdbuf.txt" );  
  streambuf *x = cout.rdbuf( file.rdbuf( ) );  
  cout << "test" << endl;   // Goes to file  
  cout.rdbuf(x);  
  cout << "test2" << endl;  
}  
  
```  
  
```Output  
test2  
```  
  
##  <a name="a-namebasiciosrdstatea--basiciosrdstate"></a><a name="basic_ios__rdstate"></a>  basic_ios::rdstate  
 플래그에 대한 비트 상태를 읽습니다.  
  
```  
 
iostate rdstate() const;
```  
  
### <a name="return-value"></a>반환 값  
 저장된 스트림 상태 정보입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// basic_ios_rdstate.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
using namespace std;  
  
void TestFlags( ios& x )  
{  
  cout << ( x.rdstate( ) & ios::badbit ) << endl;  
  cout << ( x.rdstate( ) & ios::failbit ) << endl;  
  cout << ( x.rdstate( ) & ios::eofbit ) << endl;  
  cout << endl;  
}  
  
int main( )  
{  
  fstream x( "c:\test.txt", ios::out );  
  x.clear( );  
  TestFlags( x );  
  x.clear( ios::badbit | ios::failbit | ios::eofbit );  
  TestFlags( x );  
}  
  
```  
  
```Output  
  
0  
0  
0  
  
4  
2  
1   
```  
  
##  <a name="a-namebasiciossetstatea--basiciossetstate"></a><a name="basic_ios__setstate"></a>  basic_ios::setstate  
 추가 플래그를 설정합니다.  
  
```   
void setstate(iostate _State);
```  
  
### <a name="parameters"></a>매개 변수  
 `_State`  
 설정할 추가 플래그입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 실제로 [clear](#basic_ios__clear)(_ *State* &#124; [rdstate](#basic_ios__rdstate))를 호출합니다.  
  
### <a name="example"></a>예제  
  
```cpp    
// basic_ios_setstate.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
  bool b = cout.bad( );  
  cout << b << endl;   // Good  
  cout.clear( ios::badbit );  
  b = cout.bad( );  
  // cout.clear( );  
  cout << b << endl;   // Is bad, good  
  b = cout.fail( );  
  cout << b << endl;   // Not failed  
  cout.setstate( ios::failbit );  
  b = cout.fail( );  
  cout.clear( );  
  cout << b << endl;   // Is failed, good  
  return 0;  
}  
  
```  
  
```Output  
  
0  
1   
```  
  
##  <a name="a-namebasiciossetrdbufa--basiciossetrdbuf"></a><a name="basic_ios__set_rdbuf"></a>  basic_ios::set_rdbuf  
 이 스트림 개체에 대한 읽기 버퍼로 사용할 스트림 버퍼를 할당합니다.  
  
```   
void set_rdbuf(
basic_streambuf<Elem, Tr>* strbuf)  
```  
  
### <a name="parameters"></a>매개 변수  
 ` strbuf`  
 읽기 버퍼가 될 스트림 버퍼입니다.  
  
### <a name="remarks"></a>설명  
 보호된 멤버 함수는 `stream buffer pointer`에 ` strbuf`를 저장합니다. `clear`를 호출하지 않습니다.  
  
##  <a name="a-namebasiciostiea--basiciostie"></a><a name="basic_ios__tie"></a>  basic_ios::tie  
 한 스트림이 다른 스트림보다 먼저 처리되도록 합니다.  
  
```  
 
basic_ostream<Elem, Traits> *tie() const; 
basic_ostream<Elem, Traits> *tie(
basic_ostream<Elem, Traits>* str);
```  
  
### <a name="parameters"></a>매개 변수  
 ` str`  
 스트림입니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 멤버 함수는 저장된 연결(tie) 포인터를 반환합니다. 두 번째 멤버 함수는 연결(tie) 포인터에 ` str`을 저장하고 전에 저장된 값을 반환합니다.  
  
### <a name="remarks"></a>설명  
 `tie`는 한 스트림의 작업이 완료된 후 다른 스트림의 작업이 발생하도록 두 스트림을 동기화합니다.  
  
### <a name="example"></a>예제  
  이 예에서 cin을 cout과 연결하면 숫자 자체가 cin에서 추출되기 전에 "Enter a number:" 문자열이 콘솔로 이동합니다. 이렇게 하면 숫자를 읽을 때 "Enter a number:" 문자열이 아직 버퍼에 남아 있으므로, 실제로 응답해야 할 메시지가 사용자에게 표시되도록 할 수 있습니다. 기본적으로 cin과 cout은 연결됩니다.  
  
```  
  
#include <ios>  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
  int i;  
  cin.tie( &cout );  
  cout << "Enter a number:";  
  cin >> i;  
}  
  
```  
  
##  <a name="a-namebasiciostraitstypea--basiciostraitstype"></a><a name="basic_ios__traits_type"></a>  basic_ios::traits_type  
 **Traits** 템플릿 매개 변수의 동의어입니다.  
  
```   
typedef Traits traits_type;  
```  
  
##  <a name="a-namebasicioswidena--basicioswiden"></a><a name="basic_ios__widen"></a>  basic_ios::widen  
 지정된 `char`에 해당하는 `char_type`을 찾습니다.  
  
```   
char_type widen(char Char) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `Char`  
 변환할 문자입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 `char`에 해당하는 `char_type`을 찾습니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 [use_facet](../standard-library/basic-filebuf-class.md#basic_filebuf__open)< **ctype**\< **E**> >( [getloc](../standard-library/ios-base-class.md#ios_base__getloc)). `widen`( `Char`)를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp    
// basic_ios_widen.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <wchar.h>  
  
int main( )  
{  
  using namespace std;  
  char *z = "Hello";  
  wchar_t y[2] = {0,0};  
  cout << z[0] << endl;  
  y[0] = wcout.widen( z[0] );  
  wcout << &y[0] << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosswapa--basiciosswap"></a><a name="basic_ios__swap"></a>  basic_ios::swap  
 이 `basic_ios` 개체의 값을 다른 `basic_ios` 개체의 값으로 교환합니다. 그러나 스트림 버퍼에 대한 포인터는 교환되지 않습니다.  
  
```   
void swap(basic_ios&& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `right`  
 값을 교환하는 데 사용되는 `basic_ios` 개체입니다.  
  
### <a name="remarks"></a>설명  
 보호된 멤버 함수는 저장된 `stream buffer pointer`를 제외하고 ` right`에 저장된 모든 값을 `*this`와 교환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)


