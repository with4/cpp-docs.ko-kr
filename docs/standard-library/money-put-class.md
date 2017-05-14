---
title: "money_put 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocmon/std::money_put
- money_put
- locale/std::money_put::char_type
- locale/std::money_put::iter_type
- locale/std::money_put::string_type
- locale/std::money_put::do_put
- locale/std::money_put::put
dev_langs:
- C++
helpviewer_keywords:
- money_put class
ms.assetid: f439fd56-c9b1-414c-95e1-66c918c6eee6
caps.latest.revision: 19
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 825edc66a7b4b565222133ebb47a789efbdba52b
ms.contentlocale: ko-kr
ms.lasthandoff: 04/29/2017

---
# <a name="moneyput-class"></a>money_put 클래스
통화 값에서 `CharType` 형식의 시퀀스로 변환을 제어하는 로캘 패싯으로 사용 가능한 개체에 대해 설명하는 템플릿 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class CharType,  
    class OutputIterator = ostreambuf_iterator<CharType>>  
class money_put : public locale::facet;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `CharType`  
 로캘의 문자를 인코딩하기 위해 프로그램 내 사용하는 형식입니다.  
  
 `OutputIterator`  
 통화 put 함수가 출력을 쓰는 반복기의 형식입니다.  
  
## <a name="remarks"></a>설명  
 모든 로캘 패싯과 마찬가지로, 고정 개체 ID에는 초기값 0이 저장되어 있습니다. 저장된 값에 액세스를 처음 시도하면 **id**에 고유한 양수 값이 저장됩니다.  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[money_put](#money_put)|`money_put` 형식의 개체에 대한 생성자입니다.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#char_type)|로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.|  
|[iter_type](#iter_type)|출력 반복기에 대해 설명하는 형식입니다.|  
|[string_type](#string_type)|`CharType` 형식의 문자가 포함된 문자열을 설명하는 형식입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[do_put](#do_put)|숫자 또는 문자열을 통화 값을 나타내는 문자 시퀀스로 변환하기 위해 호출하는 가상 함수입니다.|  
|[put](#put)|숫자 또는 문자열을 통화 값을 나타내는 문자 시퀀스로 변환합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<locale>  
  
 **네임스페이스:** std  
  
##  <a name="char_type"></a>  money_put::char_type  
 로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 템플릿 매개 변수 **CharType**과 동일한 의미입니다.  
  
##  <a name="do_put"></a>  money_put::do_put  
 숫자 또는 문자열을 통화 값을 나타내는 문자 시퀀스로 변환하기 위해 호출하는 가상 함수입니다.  
  
```  
virtual iter_type do_put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,   
    const string_type& val) const;

 
virtual iter_type do_put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,  
    long double val) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `next`  
 삽입된 문자열의 첫 번째 요소 주소를 지정하는 반복기입니다.  
  
 `_Intl`  
 시퀀스에서 필요한 통화 기호 유형을 나타내는 부울 값입니다. 국제의 경우 **true**이고 국내의 경우 **false**입니다.  
  
 `_Iosbase`  
 집합이 통화 기호가 선택 사항임을 나타낼 때 사용하는 형식 플래그입니다. 그 외의 경우 통화 기호는 필수 항목입니다.  
  
 `_Fill`  
 간격에 사용되는 문자입니다.  
  
 `val`  
 변환할 문자열 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 생성된 마지막 요소에서 한 위치 다음의 위치 주소를 지정하는 출력 반복기입니다.  
  
### <a name="remarks"></a>설명  
 보호되는 첫 번째 가상 구성원 함수는 [string_type](#string_type) 개체 `val`에서 통화 출력 필드를 생성하기 위해 `next`부터 시작하여 순차 요소를 생성합니다. 에 의해 제어 되는 시퀀스 `val` 필요에 따라 앞에 빼기 기호 (-)을 나타내는 하나 이상의 10 진수 숫자로 시작 해야 합니다. 함수는 생성된 통화 출력 필드를 벗어난 범위에 있는 첫 번째 요소를 지정하는 반복기를 반환합니다.  
  
 두 번째 보호된 가상 구성원 함수는 실제로 `val`을 먼저 10진수 숫자 시퀀스(필요에 따라 앞에 빼기 기호가 붙음)로 변환한 다음 위의 설명과 같이 해당 시퀀스를 변환한다는 점을 제외하면 첫 번째 함수와 동일하게 동작합니다.  
  
 통화 출력 필드의 형식은 [locale facet](../standard-library/locale-class.md#facet_class) fac에 의해 결정됩니다. 이 항목은 유효 호출 [use_facet](../standard-library/locale-functions.md#use_facet) < [moneypunct](../standard-library/moneypunct-class.md)\< **CharType**, **intl**> >( **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc))에서 반환됩니다.  
  
 구체적으로는 다음과 같습니다.  
  
- **fac**. [pos_format](../standard-library/moneypunct-class.md#pos_format)은 음수가 아닌 값에 대해 필드 구성 요소가 생성되는 순서를 결정합니다.  
  
- **fac**. [neg_format](../standard-library/moneypunct-class.md#neg_format)은 음수 값에 대해 필드 구성 요소가 생성되는 순서를 결정합니다.  
  
- **fac**. [curr_symbol](../standard-library/moneypunct-class.md#curr_symbol)은 통화 기호에 대해 생성할 요소 시퀀스를 결정합니다.  
  
- **fac**. [positive_sign](../standard-library/moneypunct-class.md#positive_sign)은 양수 기호에 대해 생성할 요소 시퀀스를 결정합니다.  
  
- **fac**. [negative_sign](../standard-library/moneypunct-class.md#negative_sign)은 음수 기호에 대해 생성할 요소 시퀀스를 결정합니다.  
  
- **fac**. [grouping](../standard-library/moneypunct-class.md#grouping)은 숫자가 소수점 왼쪽으로 그룹화되는 방법을 결정합니다.  
  
- **fac**. [thousands_sep](../standard-library/moneypunct-class.md#thousands_sep)는 소수점 왼쪽의 숫자 그룹을 구분하는 요소를 결정합니다.  
  
- **fac**. [decimal_point](../standard-library/moneypunct-class.md#decimal_point)는 소수 자릿수와 정수 자릿수를 구분하는 요소를 결정합니다.  
  
- **fac**. [frac_digits](../standard-library/moneypunct-class.md#frac_digits)는 소수점 오른쪽에 있는 유효 소수 자릿수의 수를 결정합니다.  
  
 부호 문자열 ( **fac**. `negative_sign` 또는 **fac**. `positive_sign`)에 요소가 두 개 이상 있으면 첫 번째 요소만 생성되며, **money_base::sign**과 동일한 요소가 형식 패턴 ( **fac**. `neg_format` 또는 **fac**. `pos_format`). 나머지 요소는 통화 출력 필드의 끝에 생성됩니다.  
  
 **iosbase**. [flags](../standard-library/ios-base-class.md#flags) & [showbase](../standard-library/ios-functions.md#showbase)가 0이 아니면 문자열 **fac**. `curr_symbol`이 생성되며, **money_base::symbol**과 동일한 요소가 형식 패턴에 나타납니다. 그렇지 않은 경우에는 통화 기호가 생성되지 않습니다.  
  
 **fac**, **grouping**에 의해 그룹화 제약 조건이 적용되지 않는 경우(해당 첫 번째 요소값이 CHAR_MAX임) **fac**. `thousands_sep`의 인스턴스가 통화 출력 필드의 값 부분에 생성되지 않습니다. 이 필드에는 **money_base::value**와 동일한 요소가 형식 패턴에 나타납니다. **fac**. `frac_digits`가 0이면 소수 자릿수 뒤에 **fac**. `decimal_point`의 인스턴스가 생성되지 않습니다. 그렇지 않은 경우 결과 통화 출력 필드에서 하위 순서 **fac**. `frac_digits` 소수 자릿수가 소수점 오른쪽에 배치됩니다.  
  
 모든 숫자 출력 필드에 대해서는 채우기가 수행됩니다. 단, **iosbase**. **flags** & **iosbase**. [internal](../standard-library/ios-functions.md#internal)이 0이 아니면 내부 채우기가 생성되며 **money_base::space**와 동일한 요소가 형식 패턴에 나타납니다(나타나는 경우). 그렇지 않으면 생성된 시퀀스 앞에서 내부 채우기가 수행됩니다. 채우기 문자는 **fill**입니다.  
  
 함수는 **iosbase**. **width**(0)을 호출하여 필드 너비를 0으로 다시 설정합니다.  
  
### <a name="example"></a>예제  
  **put**에 의해 가상 구성원 함수가 호출되는 [put](#put)의 예제를 참조하세요.  
  
##  <a name="iter_type"></a>  money_put::iter_type  
 출력 반복기에 대해 설명하는 형식입니다.  
  
```  
typedef OutputIterator iter_type;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 템플릿 매개 변수 **OutputIterator**와 동일한 의미입니다.  
  
##  <a name="money_put"></a>  money_put::money_put  
 `money_put` 형식의 개체에 대한 생성자입니다.  
  
```  
explicit money_put(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Refs`  
 개체에 대한 메모리 관리 형식을 지정하는 데 사용하는 정수값입니다.  
  
### <a name="remarks"></a>설명  
 `_Refs` 매개 변수에 대해 사용 가능한 값과 해당 중요도는 다음과 같습니다.  
  
-   0: 개체가 포함된 로캘에서 개체의 수명을 관리합니다.  
  
-   1: 개체의 수명을 수동으로 관리해야 합니다.  
  
-   \>1: 이러한 값은 정의 되지 않습니다.  
  
 소멸자는 보호되므로 직접적인 예제는 확인할 수 없습니다.  
  
 생성자는 **locale::**[facet](../standard-library/locale-class.md#facet_class)( `_Refs`)를 통해 해당 기준 개체를 초기화합니다.  
  
##  <a name="put"></a>  money_put::put  
 숫자 또는 문자열을 통화 값을 나타내는 문자 시퀀스로 변환합니다.  
  
```  
iter_type put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,   
    const string_type& val) const;

 
iter_type put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,  
    long double val) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `next`  
 삽입된 문자열의 첫 번째 요소 주소를 지정하는 반복기입니다.  
  
 `_Intl`  
 시퀀스에서 필요한 통화 기호 유형을 나타내는 부울 값입니다. 국제의 경우 **true**이고 국내의 경우 **false**입니다.  
  
 `_Iosbase`  
 집합이 통화 기호가 선택 사항임을 나타낼 때 사용하는 형식 플래그입니다. 그 외의 경우 통화 기호는 필수 항목입니다.  
  
 `_Fill`  
 간격에 사용되는 문자입니다.  
  
 `val`  
 변환할 문자열 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 생성된 마지막 요소에서 한 위치 다음의 위치 주소를 지정하는 출력 반복기입니다.  
  
### <a name="remarks"></a>설명  
 두 구성원 함수는 모두 [do_put](#do_put)( `next`, `_Intl`, `_Iosbase`, `_Fill`, `val`)을 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// money_put_put.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
//   locale loc( "german_germany" );  
   locale loc( "english_canada" );  
   basic_stringstream<char> psz, psz2;  
   ios_base::iostate st = 0;  
  
   psz2.imbue( loc );  
   psz2.flags( psz2.flags( )|ios_base::showbase ); // force the printing of the currency symbol  
   use_facet < money_put < char > >(loc).put(basic_ostream<char>::_Iter( psz2.rdbuf( ) ), true, psz2, st, 100012);  
   if (st & ios_base::failbit)  
      cout << "money_put( ) FAILED" << endl;  
   else  
      cout << "money_put( ) = \"" << psz2.rdbuf( )->str( ) <<"\""<< endl;     
  
   st = 0;  
};  
```  
  
```Output  
money_put( ) = "CAD1,000.12"  
```  
  
##  <a name="string_type"></a>  money_put::string_type  
 **CharType** 형식의 문자가 포함된 문자열을 설명하는 형식입니다.  
  
```  
typedef basic_string<CharType, Traits, Allocator> string_type;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 개체가 소스 시퀀스의 요소 시퀀스를 저장할 수 있는 템플릿 클래스 [basic_string](../standard-library/basic-string-class.md)의 특수화를 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<locale>](../standard-library/locale.md)   
 [facet 클래스](../standard-library/locale-class.md#facet_class)   
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)


