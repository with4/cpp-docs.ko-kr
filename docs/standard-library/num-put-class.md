---
title: "num_put 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::num_put"
  - "xlocnum/std::num_put"
  - "num_put"
  - "std.num_put"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "num_put 클래스"
ms.assetid: 36c5bffc-8283-4201-8ed4-78c4d81f8a17
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# num_put 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

숫자 값에서 `CharType` 형식의 시퀀스로 변환을 제어하는 로캘 패싯으로 사용 가능한 개체에 대해 설명하는 템플릿 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class CharType,  
    class OutputIterator = ostreambuf_iterator<CharType>>  
class num_put : public locale::facet;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `CharType`  
 로캘의 문자를 인코딩하기 위해 프로그램 내 사용하는 형식입니다.  
  
 `OutputIterator`  
 숫자 put 함수가 출력을 쓰는 반복기의 형식입니다.  
  
## <a name="remarks"></a>설명  
 모든 로캘 패싯과 마찬가지로, 고정 개체 ID에는 초기값 0이 저장되어 있습니다. 에 고유한 양수 값을 저장 하는 저장된 된 값에 액세스 하려고 하는 첫 번째 **id입니다.**  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[num_put](#num_put__num_put)|`num_put` 형식의 개체에 대한 생성자입니다.|  
  
### <a name="typedefs"></a>형식 정의  
  
|||  
|-|-|  
|[char_type](#num_put__char_type)|로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.|  
|[iter_type](#num_put__iter_type)|출력 반복기에 대해 설명하는 형식입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[do_put](#num_put__do_put)|숫자를 지정된 로캘에 대해 서식이 지정된 숫자를 나타내는 `CharType`의 시퀀스로 변환하기 위해 호출하는 가상 함수입니다.|  
|[배치](#num_put__put)|숫자를 지정된 로캘에 대해 서식이 지정된 숫자를 나타내는 `CharType`의 시퀀스로 변환합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \< 로캘>  
  
 **네임스페이스:** std  
  
##  <a name="a-namenumputchartypea-numputchartype"></a><a name="num_put__char_type"></a>  num_put:: char_type  
 로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>설명  
 형식은 템플릿 매개 변수는 동의어 **CharType**합니다.  
  
##  <a name="a-namenumputdoputa-numputdoput"></a><a name="num_put__do_put"></a>  num_put:: do_put  
 숫자의 시퀀스로 변환 하기 위해 호출 되는 가상 함수 **CharType**수를 나타내는 지정 된 로캘에 대해 서식이 지정 됩니다.  
  
```  
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    bool val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    long val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    unsigned long val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    double val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    long double val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    const void* val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    const long long val) const;

virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    const unsigned long long val) const;
```  
  
### <a name="parameters"></a>매개 변수  
 ` next`  
 삽입 된 문자열의 첫 번째 요소를 주소 지정 하는 반복기입니다.  
  
 `_Iosbase`  
 Numpunct 패싯 출력 및 출력 형식 지정에 대 한 플래그를 제약 하는 데 사용 된 로캘이 포함 된 스트림을 지정 합니다.  
  
 `_Fill`  
 간격에 사용 되는 문자입니다.  
  
 ` val`  
 숫자나를 출력 하는 부울 형식입니다.  
  
### <a name="return-value"></a>반환 값  
 출력 반복기 마지막 요소 하나 다음 위치에 생성 되는 주소입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 보호 된 가상 멤버 함수에서 시작 하는 순차 요소 생성 ` next` 의 값에서 정수 출력 필드를 생성 하 ` val`합니다. 함수 생성 된 정수 출력 필드 외에 요소를 삽입할 위치를 지정 하는 반복기를 반환 합니다.  
  
 정수 출력 필드는 일련의 생성을 위한 인쇄 기능에서 사용 하는 동일한 규칙으로 생성 됩니다 `char` 파일에는 요소입니다. 이러한 각 char 요소 형식의 해당 하는 요소에 매핑됩니다는 **CharType** 간단 하 고 일대일 매핑이 있습니다. 그러나 인쇄 기능 공백이 나 0으로 숫자 필드를 채우는 경우 `do_put` 대신 사용 하 여 **채우기**합니다. 해당 하는 인쇄 변환 사양 다음과 같이 결정 됩니다.  
  
-   경우 **iosbase**합니다. [플래그](../standard-library/ios-base-class.md#ios_base__flags) & `ios_base::basefield` == `ios_base::`[년 10 월](../Topic/%3Cios%3E%20functions.md#oct), 변환 사양은 **lo**합니다.  
  
-   경우 **iosbase.flags** & **ios_base::basefield** == `ios_base::`[16 진수](../Topic/%3Cios%3E%20functions.md#hex), 변환 사양은 **lx**합니다.  
  
-   그렇지 않으면 변환 사양은 **ld**합니다.  
  
 경우 **iosbase**합니다. [너비](../standard-library/ios-base-class.md#ios_base__width) 는 0이 아닌 경우이 값의 필드 너비를 앞에 추가 합니다. 이 함수는 다음 호출 **iosbase**합니다. **너비**(0)를 필드 너비를 0으로 다시 설정 합니다.  
  
 안쪽 여백 경우에 최소 요소 수 *N* 출력 필드를 지정 하는 데 필요한 보다 작은 **iosbase**합니다. [너비](../standard-library/ios-base-class.md#ios_base__width)합니다. 이러한 채우기의 시퀀스로 구성 되어 *N* – **너비** 의 복사본을 **채우기**합니다. 그런 다음 안쪽 여백 다음과 같이 발생 합니다.  
  
-   경우 **iosbase**합니다. **플래그** & `ios_base::adjustfield` == `ios_base::`[왼쪽](../Topic/%3Cios%3E%20functions.md#left), 플래그 **–** 앞에 추가 합니다. (패딩 생성된 된 텍스트 이후에 발생합니다.)  
  
-   경우 **iosbase.flags** & **ios_base::adjustfield** == `ios_base::`[내부](../Topic/%3Cios%3E%20functions.md#internal), 플래그 **0** 앞에 추가 합니다. (숫자 출력 필드에 대 한 안쪽 여백 발생 위치 0 인쇄 기능 채워야 합니다.)  
  
-   그렇지 않은 경우 추가 플래그가 앞에 추가 합니다. (패딩 생성된 된 시퀀스 하기 전에 발생 합니다.)  
  
 마지막으로:  
  
-   경우 **iosbase**합니다. **플래그** & `ios_base::`[showpos](../Topic/%3Cios%3E%20functions.md#showpos) 이 값은 0 플래그 **+** 앞에 변환 사양에 추가 됩니다.  
  
-   경우 **iosbase**합니다. **플래그** & **ios_base::**[showbase](../Topic/%3Cios%3E%20functions.md#showbase) 이 값은 0 플래그 **#** 앞에 변환 사양에 추가 됩니다.  
  
 정수 형식의 출력 필드에 의해 추가로 결정 됩니다는 [로캘 패싯](../standard-library/locale-class.md#facet_class)**fac** 호출에서 반환한 [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [numpunct](../standard-library/numpunct-class.md)\< **Elem**> ( **iosbase**합니다. [getloc](../standard-library/ios-base-class.md#ios_base__getloc)). 구체적으로는 다음과 같습니다.  
  
- **fac**합니다. [그룹화](../standard-library/numpunct-class.md#numpunct__grouping) 숫자를 소수점의 왼쪽에 그룹화 하는 방법을 결정 합니다.  
  
- **fac**합니다. [thousands_sep](../standard-library/numpunct-class.md#numpunct__thousands_sep) 소수점의 왼쪽에 있는 숫자 그룹을 구분 하는 순서를 결정 합니다.  
  
 그룹화 제한이에 의해 적용 되는 경우 **fac**합니다. **그룹화** (첫 번째 요소에 값이 있는 CHAR_MAX)의 인스턴스가 다음 **fac**합니다. `thousands_sep` 출력 필드에 생성 됩니다. 그렇지 않은 경우 인쇄 변환이 발생 한 후에 구분 기호가 삽입 됩니다.  
  
 두 번째 보호 된 가상 멤버 함수:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    unsigned long val) const;
```  
  
 변환 사양을 대체 한다는 점을 제외 하면 첫 번째 동일 하 게 동작 **ld** 와 **lu**합니다.  
  
 세 번째 보호 된 가상 멤버 함수:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    double val) const;
```  
  
 값에서 부동 소수점 출력 필드를 생성 한다는 점을 제외 하면 첫 번째 동일 하 게 동작 **val**합니다. **fac**합니다. [decimal_point](../standard-library/numpunct-class.md#numpunct__decimal_point) 소수 자릿수의 정수 부분을 구분 하는 시퀀스를 결정 합니다. 해당 하는 인쇄 변환 사양 다음과 같이 결정 됩니다.  
  
-   경우 **iosbase**합니다. **플래그** & `ios_base::floatfield` == `ios_base::`[고정](../Topic/%3Cios%3E%20functions.md#fixed), 변환 사양은 **lf**합니다.  
  
-   경우 **iosbase**합니다. **플래그** & **ios_base::floatfield** == `ios_base::`[과학](../Topic/%3Cios%3E%20functions.md#scientific), 변환 사양은 `le`합니다. 경우 **iosbase**합니다. **플래그** & `ios_base::`[대문자](../Topic/%3Cios%3E%20functions.md#uppercase) 이 값은 0 **e** 바뀝니다 **E**합니다.  
  
-   그렇지 않으면 변환 사양은 **lg**합니다. 경우 **iosbase**합니다. **플래그** & **ios_base::uppercase** 이 값은 0 **g** 바뀝니다 **G**합니다.  
  
 경우 **iosbase**합니다. **플래그** & **ios_base::fixed** 0이 아닌 경우 **iosbase**합니다. [전체 자릿수](../standard-library/ios-base-class.md#ios_base__precision) 값을 가진 전체 자릿수가 0 보다 크면 **iosbase**합니다. **전체 자릿수** 앞에 변환 사양에 추가 됩니다. 채움을 정수 출력 필드의 경우와 동일 하 게 작동 합니다. 안쪽 여백 문자는 **채우기**합니다. 마지막으로:  
  
-   경우 **iosbase**합니다. **플래그** & `ios_base::`[showpos](../Topic/%3Cios%3E%20functions.md#showpos) 이 값은 0 플래그 **+** 앞에 변환 사양에 추가 됩니다.  
  
-   경우 **iosbase**합니다. **플래그** & `ios_base::`[showpoint](../Topic/%3Cios%3E%20functions.md#showpoint) 이 값은 0 플래그 **#** 앞에 변환 사양에 추가 됩니다.  
  
 네 번째 보호 된 가상 멤버 함수:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    long double val) const;
```  
  
 점을 제외 하 고 세 번째 동일 하 게 작동 한정자 **l** 변환 사양을 대체 됩니다 **L**합니다.  
  
 다섯 번째 보호 된 가상 멤버 함수:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    const void* val) const;
```  
  
 변환 사양 않는다는 제외 하면 첫 번째 동일 하 게 작동 `p`**,** plus 안쪽 여백을 지정 하는 데 필요한 모든 한정자입니다.  
  
 여섯 번째 보호 된 가상 멤버 함수:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    bool val) const;
```  
  
 부울 출력 필드를 생성 한다는 점을 제외 하면 첫 번째 동일 하 게 동작 ` val`합니다.  
  
 부울 출력 필드는 두 가지 형태 중 하나를 사용 합니다. 경우 **iosbase**합니다. **플래그** & `ios_base::`[boolalpha](../Topic/%3Cios%3E%20functions.md#boolalpha) 는 **false**, 멤버 함수는 반환 `do_put`(_ *다음*, \_ *Iosbase*, \_ *채우기*, ( **긴**) ` val`), 일반적으로 0의 생성 된 시퀀스 생성 (에 대 한 **false**) 또는 1 (에 대 한 **true**). 그렇지 않으면 생성 된 시퀀스는 하나 **fac**합니다. [falsename](../standard-library/numpunct-class.md#numpunct__falsename)`)` (에 대 한 **false**), 또는 **fac**합니다. [truename](../standard-library/numpunct-class.md#numpunct__truename) (에 대 한 **true**).  
  
 일곱 번째 보호 된 가상 멤버 함수:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,  
    Elem fill,
    long long val) const;
```  
  
 변환 사양을 대체 한다는 점을 제외 하면 첫 번째 동일 하 게 동작 **ld** 와 **lld**합니다.  
  
 여덟 번째 보호 된 가상 멤버 함수:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,  
    Elem fill,
    unsigned long long val) const;
```  
  
 변환 사양을 대체 한다는 점을 제외 하면 첫 번째 동일 하 게 동작 `ld` 와 `llu`합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [배치](#num_put__put), 되는 호출 `do_put`합니다.  
  
##  <a name="a-namenumputitertypea-numputitertype"></a><a name="num_put__iter_type"></a>  num_put:: iter_type  
 출력 반복기에 대해 설명하는 형식입니다.  
  
```  
typedef OutputIterator iter_type;  
```  
  
### <a name="remarks"></a>설명  
 형식은 템플릿 매개 변수는 동의어 **OutputIterator 합니다.**  
  
##  <a name="a-namenumputnumputa-numputnumput"></a><a name="num_put__num_put"></a>  num_put:: num_put  
 `num_put` 형식의 개체에 대한 생성자입니다.  
  
```  
explicit num_put(size_t _Refs = 0);
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
  
 생성자와 해당 기본 개체 **로캘::**[패싯](../standard-library/locale-class.md#facet_class)(_ *Refs*).  
  
##  <a name="a-namenumputputa-numputput"></a><a name="num_put__put"></a>  num_put:: put  
 숫자의 시퀀스로 변환 **CharType**수를 나타내는 지정 된 로캘에 대해 서식이 지정 됩니다.  
  
```  
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    bool val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    long val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    unsigned long val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    Long long val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    Unsigned long long val) const;

 
 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    double val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    long double val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    const void* val) const;
```  
  
### <a name="parameters"></a>매개 변수  
 ` dest`  
 삽입 된 문자열의 첫 번째 요소를 주소 지정 하는 반복기입니다.  
  
 `_Iosbase`  
 Numpunct 패싯 출력 및 출력 형식 지정에 대 한 플래그를 제약 하는 데 사용 된 로캘을 포함 하는 스트림을 지정 합니다.  
  
 `_Fill`  
 간격에 사용 되는 문자입니다.  
  
 ` val`  
 숫자나를 출력 하는 부울 형식입니다.  
  
### <a name="return-value"></a>반환 값  
 출력 반복기 마지막 요소 하나 다음 위치에 생성 되는 주소입니다.  
  
### <a name="remarks"></a>설명  
 모든 멤버 함수 반환 [do_put](#num_put__do_put)( ` next`, `_Iosbase`, `_Fill`, ` val`).  
  
### <a name="example"></a>예제  
  
```  
// num_put_put.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
   basic_stringstream<char> psz2;  
   ios_base::iostate st = 0;  
   long double fVal;  
   cout << "The thousands separator is: "   
        << use_facet < numpunct <char> >(loc).thousands_sep( )   
        << endl;  
  
   psz2.imbue( loc );  
   use_facet < num_put < char > >  
      ( loc ).put(basic_ostream<char>::_Iter(psz2.rdbuf( ) ),  
                    psz2, ' ', fVal=1000.67);  
  
   if ( st & ios_base::failbit )  
      cout << "num_put( ) FAILED" << endl;  
   else  
      cout << "num_put( ) = " << psz2.rdbuf( )->str( ) << endl;  
}  
```  
  
```Output  
The thousands separator is: .  
num_put( ) = 1.000,67  
```  
  
## <a name="see-also"></a>참고 항목  
 [\< 로캘>](../standard-library/locale.md)   
 [facet 클래스](../standard-library/locale-class.md#facet_class)   
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)

