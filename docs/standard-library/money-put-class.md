---
title: "money_put 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::money_put"
  - "xlocmon/std::money_put"
  - "money_put"
  - "std.money_put"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "money_put 클래스"
ms.assetid: f439fd56-c9b1-414c-95e1-66c918c6eee6
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# money_put 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

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
 모든 로캘 패싯과 마찬가지로, 고정 개체 ID에는 초기값 0이 저장되어 있습니다. 에 고유한 양수 값을 저장 하는 저장된 된 값에 액세스 하려고 하는 첫 번째 **id입니다.**  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[money_put](#money_put__money_put)|`money_put` 형식의 개체에 대한 생성자입니다.|  
  
### <a name="typedefs"></a>형식 정의  
  
|||  
|-|-|  
|[char_type](#money_put__char_type)|로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.|  
|[iter_type](#money_put__iter_type)|출력 반복기에 대해 설명하는 형식입니다.|  
|[string_type](#money_put__string_type)|`CharType` 형식의 문자가 포함된 문자열을 설명하는 형식입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[do_put](#money_put__do_put)|숫자 또는 문자열을 통화 값을 나타내는 문자 시퀀스로 변환하기 위해 호출하는 가상 함수입니다.|  
|[배치](#money_put__put)|숫자 또는 문자열을 통화 값을 나타내는 문자 시퀀스로 변환합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \< 로캘>  
  
 **네임스페이스:** std  
  
##  <a name="a-namemoneyputchartypea-moneyputchartype"></a><a name="money_put__char_type"></a>  money_put:: char_type  
 로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>설명  
 형식은 템플릿 매개 변수는 동의어 **CharType**합니다.  
  
##  <a name="a-namemoneyputdoputa-moneyputdoput"></a><a name="money_put__do_put"></a>  money_put:: do_put  
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
 ` next`  
 삽입 된 문자열의 첫 번째 요소를 주소 지정 하는 반복기입니다.  
  
 `_Intl`  
 형식의 시퀀스에서 예상 되는 통화 기호를 나타내는 부울 값: **true** 경우 국제 **false** 국내 하는 경우.  
  
 `_Iosbase`  
 형식 플래그는 집합의 통화 기호는 선택적인 입력 항목으로 나타내는 경우 그렇지 않은 경우 필수  
  
 `_Fill`  
 간격에 사용 되는 문자입니다.  
  
 ` val`  
 변환할 문자열 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 출력 반복기 마지막 요소 하나 다음 위치에 생성 되는 주소입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 보호 된 가상 멤버 함수에서 시작 하는 순차 요소 생성 ` next` 통화 출력 필드를 생성 하는 [string_type](#money_put__string_type) 개체 ` val`합니다. 에 의해 제어 되는 시퀀스 ` val` 하나 이상의 10 진수 숫자, 필요에 따라 앞에 크기를 나타내는 빼기 기호 (-)로 시작 해야 합니다. 함수는 생성 된 통화 출력 필드의 첫 번째 요소를 지정 하는 반복기를 반환 합니다.  
  
 두 번째 보호 된 가상 멤버 함수는 첫 번째 동일 하 게 동작을 제외 하 고 효과적으로 첫 번째 변환 ` val` 필요에 따라 앞에 빼기 기호, 소수 자릿수 시퀀스에 위와 같은 해당 시퀀스를 변환 합니다.  
  
 통화 출력 필드의 형식은 따라 결정 됩니다는 [로캘 패싯](../standard-library/locale-class.md#facet_class) fac (유효) 호출에서 반환 된 [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [moneypunct](../standard-library/moneypunct-class.md)\< **CharType**, **intl**>> ( **iosbase**합니다. [getloc](../standard-library/ios-base-class.md#ios_base__getloc)).  
  
 구체적으로는 다음과 같습니다.  
  
- **fac**합니다. [pos_format](../standard-library/moneypunct-class.md#moneypunct__pos_format) 음수가 아닌 값에 대 한 필드의 구성 요소는 생성 하는 순서를 결정 합니다.  
  
- **fac**합니다. [neg_format](../standard-library/moneypunct-class.md#moneypunct__neg_format) 음수 값에 대 한 필드의 구성 요소는 생성 하는 순서를 결정 합니다.  
  
- **fac**합니다. [curr_symbol](../standard-library/moneypunct-class.md#moneypunct__curr_symbol) 통화 기호를 생성 하는 요소 시퀀스를 결정 합니다.  
  
- **fac**합니다. [positive_sign](../standard-library/moneypunct-class.md#moneypunct__positive_sign) 더하기 기호를 생성 하는 요소 시퀀스를 결정 합니다.  
  
- **fac**합니다. [negative_sign](../standard-library/moneypunct-class.md#moneypunct__negative_sign) 음수 기호를 생성 하는 요소 시퀀스를 결정 합니다.  
  
- **fac**합니다. [그룹화](../standard-library/moneypunct-class.md#moneypunct__grouping) 숫자를 소수점의 왼쪽에 그룹화 하는 방법을 결정 합니다.  
  
- **fac**합니다. [thousands_sep](../standard-library/moneypunct-class.md#moneypunct__thousands_sep) 소수점의 왼쪽에 있는 숫자 그룹을 구분 하는 요소를 결정 합니다.  
  
- **fac**합니다. [decimal_point](../standard-library/moneypunct-class.md#moneypunct__decimal_point) 모든 소수 자릿수의 정수 부분을 구분 하는 요소를 결정 합니다.  
  
- **fac**합니다. [frac_digits](../standard-library/moneypunct-class.md#moneypunct__frac_digits) 상당 부분이 소수점 오른쪽 자릿수의 수를 결정 합니다.  
  
 경우 서명 문자열 ( **fac**합니다. `negative_sign` 또는 **fac**합니다. `positive_sign`) 둘 이상의 요소를 첫 번째 요소에만 위치에 생성 됩니다와 동일한 요소가 **money_base::sign** 의 형식 패턴에 표시 ( **fac**합니다. `neg_format` 또는 **fac**합니다. `pos_format`). 남아 있는 요소는 통화 출력 필드의 끝에 생성 됩니다.  
  
 경우 **iosbase**합니다. [플래그](../standard-library/ios-base-class.md#ios_base__flags) & [showbase](../Topic/%3Cios%3E%20functions.md#showbase) 이 값은 0에서 문자열 **fac**합니다. `curr_symbol` 여기서 생성와 동일한 요소가 **money_base::symbol** 의 형식 패턴에 나타납니다. 그렇지 않은 경우에 통화 기호를 사용 하지 생성 됩니다.  
  
 그룹화 제한이에 의해 적용 되는 경우 **fac**합니다. **그룹화** (첫 번째 요소에 값이 있는 CHAR_MAX)의 인스턴스가 다음 **fac**합니다. `thousands_sep` 통화 출력 필드의 값 부분에 생성 됩니다 (여기서와 동일한 요소가 **money_base::value** 의 형식 패턴에 표시). 경우 **fac**합니다. `frac_digits` 인스턴스가 0 **fac**합니다. `decimal_point` 10 진수 뒤에 생성 됩니다. 그렇지 않으면 결과 통화 출력 필드 배치 순위가 낮은 **fac**합니다. `frac_digits` 소수 자릿수는 소수점 오른쪽입니다.  
  
 안쪽 여백 발생 되는 경우를 제외한 모든 숫자 출력 필드의 경우와 **iosbase**합니다. **플래그** & **iosbase**합니다. [내부](../Topic/%3Cios%3E%20functions.md#internal) 는 0이 아니고, 내부 안쪽 여백 위치에 생성 됩니다와 동일한 요소가 **money_base::space** 가 나타나지의 형식 패턴에 나타납니다. 그렇지 않으면 내부 안쪽 생성된 된 시퀀스 하기 전에 발생합니다. 안쪽 여백 문자는 **채우기**합니다.  
  
 함수 호출 **iosbase**합니다. **너비**(0)를 필드 너비를 0으로 다시 설정 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [배치](#money_put__put), 에서 가상 멤버 함수를 호출 하는 경우, **배치**합니다.  
  
##  <a name="a-namemoneyputitertypea-moneyputitertype"></a><a name="money_put__iter_type"></a>  money_put:: iter_type  
 출력 반복기에 대해 설명하는 형식입니다.  
  
```  
typedef OutputIterator iter_type;  
```  
  
### <a name="remarks"></a>설명  
 형식은 템플릿 매개 변수는 동의어 **OutputIterator 합니다.**  
  
##  <a name="a-namemoneyputmoneyputa-moneyputmoneyput"></a><a name="money_put__money_put"></a>  money_put:: money_put  
 `money_put` 형식의 개체에 대한 생성자입니다.  
  
```  
explicit money_put(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Refs`  
 개체에 대 한 메모리 관리의 유형을 지정 하는 데 사용 되는 정수 값입니다.  
  
### <a name="remarks"></a>설명  
 가능한 값은 `_Refs` 매개 변수 및 그 중요성은:  
  
-   0:를 포함 하는 로캘을에서 개체의 수명을 관리 합니다.  
  
-   1: 개체의 수명을 수동으로 관리 해야 합니다.  
  
-   \> 0:이 값이 정의 되지 않습니다.  
  
 소멸자는 보호 되므로 직접 예제가 없습니다는 가능 합니다.  
  
 생성자와 해당 기본 개체 **로캘::**[패싯](../standard-library/locale-class.md#facet_class)( `_Refs`).  
  
##  <a name="a-namemoneyputputa-moneyputput"></a><a name="money_put__put"></a>  money_put:: put  
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
 ` next`  
 삽입 된 문자열의 첫 번째 요소를 주소 지정 하는 반복기입니다.  
  
 `_Intl`  
 형식의 시퀀스에서 예상 되는 통화 기호를 나타내는 부울 값: **true** 경우 국제 **false** 국내 하는 경우.  
  
 `_Iosbase`  
 형식 플래그는 집합의 통화 기호는 선택적인 입력 항목으로 나타내는 경우 그렇지 않은 경우 필수  
  
 `_Fill`  
 간격에 사용 되는 문자입니다.  
  
 ` val`  
 변환할 문자열 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 출력 반복기 마지막 요소 하나 다음 위치에 생성 되는 주소입니다.  
  
### <a name="remarks"></a>설명  
 두 멤버 함수는 반환 [do_put](#money_put__do_put)( ` next`, `_Intl`, `_Iosbase`, `_Fill`, ` val`).  
  
### <a name="example"></a>예제  
  
```  
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
  
##  <a name="a-namemoneyputstringtypea-moneyputstringtype"></a><a name="money_put__string_type"></a>  money_put:: string_type  
 형식의 문자를 포함 하는 문자열을 설명 하는 형식 **CharType**합니다.  
  
```  
typedef basic_string<CharType, Traits, Allocator> string_type;  
```  
  
### <a name="remarks"></a>설명  
 템플릿 클래스의 특수화를 설명 하는 형식 [basic_string](../standard-library/basic-string-class.md) 해당 개체가 소스 시퀀스의 요소 시퀀스를 저장할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [\< 로캘>](../standard-library/locale.md)   
 [facet 클래스](../standard-library/locale-class.md#facet_class)   
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)

