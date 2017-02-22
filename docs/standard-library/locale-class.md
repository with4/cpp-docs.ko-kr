---
title: "locale 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xlocale/std::locale"
  - "std::locale"
  - "std.locale"
  - "locale"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "locale 클래스"
ms.assetid: 7dd6d271-472d-4750-8fb5-ea8f55fbef62
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# locale 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

문화별 정보를 특정 지역별 환경을 전체적으로 정의하는 패싯 집합으로 캡슐화하는 로캘 개체에 대해 설명하는 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class locale;  
```  
  
## <a name="remarks"></a>설명  
 패싯 클래스에서 파생 된 클래스의 개체에 대 한 포인터는 [패싯](#facet_class) 양식의 공용 개체를 가진:  
  
```  
static locale::id id;  
```  
  
 이러한 패싯의 개방형 집합을 정의할 수 있습니다. 또한 임의 수의 패싯을 지정하는 로캘 개체를 만들 수 있습니다.  
  
 이러한 패싯의 미리 정의 된 그룹 나타냅니다는 [로캘 범주](#locale__category) 일반적으로 관리 하는 표준 C 라이브러리 함수에 의해 `setlocale`합니다.  
  
 범주 collate(LC_COLLATE)에 포함되는 패싯:  
  
```  
collate<char>  
collate<wchar_t>  
```  
  
 범주 ctype(LC_CTYPE)에 포함되는 패싯:  
  
```  
ctype<char>  
ctype<wchar_t>  
codecvt<char, char, mbstate_t>  
codecvt<wchar_t, char, mbstate_t>  
codecvt<char16_t, char, mbstate_t>  
codecvt<char32_t, char, mbstate_t>  
```  
  
 범주 monetary(LC_MONETARY)에 포함되는 패싯:  
  
```  
moneypunct<char, false>  
moneypunct<wchar_t, false>  
moneypunct<char, true>  
moneypunct<wchar_t, true>  
money_get<char, istreambuf_iterator<char>>  
money_get<wchar_t, istreambuf_iterator<wchar_t>>  
money_put<char, ostreambuf_iterator<char>>  
money_put<wchar_t, ostreambuf_iterator<wchar_t>>  
```  
  
 범주 numeric(LC_NUMERIC)에 포함되는 패싯:  
  
```  
num_get<char, istreambuf_iterator<char>>  
num_get<wchar_t, istreambuf_iterator<wchar_t>>  
num_put<char, ostreambuf_iterator<char>>  
num_put<wchar_t, ostreambuf_iterator<wchar_t>>  
numpunct<char>  
numpunct<wchar_t>  
```  
  
 범주 time(LC_TIME)에 포함되는 패싯:  
  
```  
time_get<char, istreambuf_iterator<char>>  
time_get<wchar_t, istreambuf_iterator<wchar_t>>  
time_put<char, ostreambuf_iterator<char>>  
time_put<wchar_t, ostreambuf_iterator<wchar_t>>  
```  
  
 범주 messages(LC_MESSAGES)에 포함되는 패싯:  
  
```  
messages<char>  
messages<wchar_t>  
```  
  
 (마지막 범주는 Posix에 필요하지만 C 표준은 해당하지 않습니다.)  
  
 이러한 미리 정의된 패싯 중 일부는 iostreams 클래스가 숫자 값과 텍스트 시퀀스 사이의 변환을 제어하는 데 사용됩니다.  
  
 클래스 로캘 개체는 또한 로캘 이름을 클래스의 개체로 저장 [문자열](../Topic/%3Cstring%3E%20typedefs.md#string)합니다. 클래스의 개체를 throw 하는 로캘 패싯 또는 로캘 개체를 생성 하려면 잘못 된 로캘 이름을 사용 하 여 [runtime_error](../standard-library/runtime-error-class.md)합니다. 로캘 개체를 확인할 수 없고 C-스타일 로캘이 개체로 표현된 로캘에 정확히 해당할 경우 저장된 로캘 이름은 `"*"`입니다. 그렇지 않으면 로캘 개체에 대 한 표준 C 라이브러리 내에서 일치 하는 로캘을 설정할 수 있습니다 `_Loc`, 를 호출 하 여 `setlocale`(LC_ALL `,` `_Loc`합니다. [이름](#locale__name)`().c_str()`).  
  
 이 구현에서는 정적 멤버 함수도 호출하여  
  
```  
static locale empty();
```  
  
 패싯이 없는 로캘 개체를 구성할 수 있습니다. 투명 로캘 이기도 경우 템플릿 함수 [has_facet](../Topic/%3Clocale%3E%20functions.md#has_facet) 및 [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) 요청 된 패싯을 찾을 수 없습니다 투명 로캘에서 참조 먼저 전역 로캘을 한 다음, 투명 하 게 하는 경우 클래식 로캘을 합니다. 따라서, 다음과 같이 작성할 수 있습니다.  
  
```  
cout.imbue(locale::empty());
```  
  
 다음의 삽입 [cout](../Topic/%3Ciostream%3E%20functions.md#cout) 전역 로캘의 현재 상태에 따라 조정 됩니다. 다음과 같이 작성할 수도 있습니다.  
  
```  
locale loc(locale::empty(),
    locale::classic(),  
    locale::numeric);

cout.imbue(loc);
```   
  
 전역 로캘에서 날짜 및 통화 금액 삽입에 대해 달라진 규칙을 제공하는 경우에도 `cout`에 대한 후속 삽입 숫자 서식 지정 규칙은 C 로캘과 동일하게 유지됩니다.  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[로캘](#locale__locale)|패싯 또는 범주를 다른 로캘의 패싯 또는 범주로 대체한 경우 로캘 또는 로캘의 복사본을 만듭니다.|  
  
### <a name="typedefs"></a>형식 정의  
  
|||  
|-|-|  
|[범주](#locale__category)|표준 패싯 범주를 나타내는 비트 마스크 값을 제공하는 정수 형식입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[결합](#locale__combine)|지정된 로캘의 패싯을 대상 로캘로 삽입합니다.|  
|[이름](#locale__name)|저장된 로캘 이름을 반환합니다.|  
  
### <a name="static-functions"></a>정적 함수  
  
|||  
|-|-|  
|[클래식](#locale__classic)|정적 멤버 함수는 클래식 C 로캘을 나타내는 로캘 개체를 반환합니다.|  
|[전역](#locale__global)|프로그램에 대한 기본 로컬을 다시 설정합니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[연산자! =](#locale__operator_neq)|두 로캘이 다른지 테스트합니다.|  
|[연산자)](#locale__operator__)|두 `basic_string` 개체를 비교합니다.|  
|[연산자 = =](#locale__operator_eq_eq)|두 로캘이 같은지 테스트합니다.|  
  
### <a name="classes"></a>클래스  
  
|||  
|-|-|  
|[패싯](#facet_class)|모든 로캘 패싯에 대한 기본 클래스로 사용하는 클래스입니다.|  
|[id](#id_class)|멤버 클래스는 로캘의 패싯을 조회하기 위한 인덱스로 사용되는 고유한 패싯 ID를 제공합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \< 로캘>  
  
 **네임스페이스:** std  
  
##  <a name="a-namelocalecategorya-localecategory"></a><a name="locale__category"></a>  locale:: category  
 표준 패싯 범주를 나타내는 비트 마스크 값을 제공하는 정수 형식입니다.  
  
```  
typedef int category;  
static const int collate = LC_COLLATE;  
static const int ctype = LC_CTYPE;  
static const int monetary = LC_MONETARY;  
static const int numeric = LC_NUMERIC;  
static const int time = LC_TIME;  
static const int messages = LC_MESSAGES;  
static const int all = LC_ALL;  
static const int none = 0;  
```  
  
### <a name="remarks"></a>설명  
 형식이 대 한 동의어는 `int` 는 비트 마스크의 개별 요소 그룹을 나타낼 수 있는 형식 클래스 로캘 로컬 입력 하거나 해당 C 로캘 범주 중 하나를 나타내는 데 사용할 수 있습니다. 요소는:  
  
- **collate**, LC_COLLATE C 범주에 해당 하는,  
  
- **ctype**, LC_CTYPE C 범주에 해당 하는,  
  
- **통화**, LC_MONETARY C 범주에 해당 하는,  
  
- **숫자**, LC_NUMERIC C 범주에 해당 하는,  
  
- **시간**, LC_TIME C 범주에 해당 하는,  
  
- **메시지**, LC_MESSAGES Posix 범주에 해당 하는,  
  
 또한 두 개의 유용한 값은 같습니다.  
  
- **none**, C 범주 중 어떤 항목에 해당 하는,  
  
- **모든**, LC_ALL 모든 범주의 C 공용 구조체에 해당 하는,  
  
 범주는 임의의 그룹을 사용 하 여 나타낼 수 있습니다 `OR` 다음과 같이이 상수 **통화** &#124; **시간**합니다.  
  
##  <a name="a-namelocaleclassica-localeclassic"></a><a name="locale__classic"></a>  locale:: classic  
 정적 멤버 함수는 클래식 C 로캘을 나타내는 로캘 개체를 반환합니다.  
  
```  
static const locale& classic();
```  
  
### <a name="return-value"></a>반환 값  
 C에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 클래식 C 로캘을 미국 국제화 하지는 않는 프로그램에서 암시적으로 사용 되는 표준 C 라이브러리 내에서 영어 ASCII 로캘.  
  
### <a name="example"></a>예제  
  
```  
// locale_classic.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
using namespace std;  
  
int main( )   
{  
   locale loc1( "german" );  
   locale loc2 = locale::global( loc1 );  
   cout << "The name of the previous locale is: " << loc2.name( )  
        << "." << endl;  
   cout << "The name of the current locale is: " << loc1.name( )   
        << "." << endl;  
  
   if (loc2 == locale::classic( ) )  
      cout << "The previous locale was classic." << endl;  
   else  
      cout << "The previous locale was not classic." << endl;  
  
   if (loc1 == locale::classic( ) )  
      cout << "The current locale is classic." << endl;  
   else  
      cout << "The current locale is not classic." << endl;  
}  
```  
  
```Output  
The name of the previous locale is: C.  
The name of the current locale is: German_Germany.1252.  
The previous locale was classic.  
The current locale is not classic.  
```  
  
##  <a name="a-namelocalecombinea-localecombine"></a><a name="locale__combine"></a>  locale:: combine  
 지정된 로캘의 패싯을 대상 로캘로 삽입합니다.  
  
```  
template <class Facet>  
locale combine(const locale& _Loc) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Loc`  
 대상 로캘의에 삽입 되 면 포함 된 로캘.  
  
### <a name="return-value"></a>반환 값  
 멤버 함수를 추가 하거나이에서 대체 하는 로캘 개체를 반환 **\*이** 패싯 `Facet` 에 나열 된 `_Loc`합니다.  
  
### <a name="example"></a>예제  
  
```  
// locale_combine.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <tchar.h>  
using namespace std;  
  
int main() {  
   locale loc ( "German_germany" );  
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s; it comes before z in the German alphabet  
   _TCHAR * s2 = _T("Das ist weizzz.");  
   int result1 = use_facet<collate<_TCHAR> > ( loc ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc ) << result1 << endl;  
  
   locale loc2 ( "C" );  
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc2 )  << result2 << endl;  
  
   locale loc3 = loc2.combine<collate<_TCHAR> > (loc);  
   int result3 = use_facet<collate<_TCHAR> > ( loc3 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc3 ) << result3 << endl;  
}  
```  
  
##  <a name="a-namefacetclassa-facet-class"></a><a name="facet_class"></a>  facet 클래스  
 모든 로캘 패싯에 대한 기본 클래스로 사용하는 클래스입니다.  
  
클래스 패싯 {보호: 명시적 패싯 (size_t _Refs = 0); 가상 ~ facet(); 개인: facet(const facet&) / void 연산자를 정의 하지 / =(const facet&) / 정의 되지 /};  
  
### <a name="remarks"></a>설명  
 참고 복사 하거나 클래스 패싯의 개체를 할당할 수 없습니다. 생성 하는 클래스에서 파생 된 개체를 소멸 시킬 `locale::facet` 하지만 적절 한 기본 클래스의 개체가 아니라 합니다. 개체를 생성 하는 일반적으로 `_Myfac` 에서 같이 로캘을 생성할 때 패싯에서 파생 된 **localeloc**( `locale::classic`(), **새**`_Myfac`);  
  
 이러한 경우 기본 클래스 패싯에 대 한 생성자는 0 이어야 `_Refs` 인수입니다. 개체가 더 이상 필요 하 고, 삭제 됩니다. 0이 아닌 _ 제공 따라서 *Refs* 수행 하는 데는 개체의 수명에 대 한 책임 드문 경우에만 인수입니다.  
  
##  <a name="a-namelocaleglobala-localeglobal"></a><a name="locale__global"></a>  locale:: global  
 프로그램에 대 한 기본 로캘을 다시 설정합니다. 이 C 및 c + +에 대 한 전역 로캘을 영향을 줍니다.  
  
```  
static locale global(const locale& _Loc);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Loc`  
 프로그램에서 기본 로캘로 사용할 로캘.  
  
### <a name="return-value"></a>반환 값  
 기본 로캘을 다시 설정 하기 전에 이전 로캘.  
  
### <a name="remarks"></a>설명  
 프로그램을 시작할 때 전역 로캘을 클래식 로캘을와 같습니다.  `global()` 함수 호출 `setlocale( LC_ALL, loc.name. c_str())` 표준 C 라이브러리에서 일치 하는 로캘을 설정할 수 있습니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// locale_global.cpp  
// compile by using: /EHsc  
#include <locale>  
#include <iostream>  
#include <tchar.h>  
using namespace std;  
  
int main( )  
{  
   locale loc ( "German_germany" );  
   locale loc1;  
   cout << "The initial locale is: " << loc1.name( ) << endl;  
   locale loc2 = locale::global ( loc );  
   locale loc3;  
   cout << "The current locale is: " << loc3.name( ) << endl;  
   cout << "The previous locale was: " << loc2.name( ) << endl;  
}  
```  
  
```Output  
The initial locale is: C  
The current locale is: German_Germany.1252  
The previous locale was: C  
```  
  
##  <a name="a-nameidclassa-id-class"></a><a name="id_class"></a>  id 클래스  
 멤버 클래스는 로캘의 패싯을 조회하기 위한 인덱스로 사용되는 고유한 패싯 ID를 제공합니다.  
  
클래스 id {보호: id (), 개인: id(const id&) / void 연산자를 정의 하지 / =(const id&) / 정의 되지 /};  
  
### <a name="remarks"></a>설명  
 멤버 클래스는 각 고유 로캘 패싯에 필요한 정적 멤버 개체를 설명 합니다. 참고 복사 하거나 클래스의 개체를 할당할 수 없습니다 **id**합니다.  
  
##  <a name="a-namelocalelocalea-localelocale"></a><a name="locale__locale"></a>  locale:: locale  
 패싯 또는 범주를 다른 로캘의 패싯 또는 범주로 대체한 경우 로캘 또는 로캘의 복사본을 만듭니다.  
  
```  
locale();

explicit locale(
    const char* _Locname,  
    category _Cat = all);

explicit locale(
    const string& _Locname);

locale(
    const locale& _Loc);

locale(
    const locale& _Loc,   
    const locale& _Other,  
    category _Cat);

locale(
    const locale& _Loc,   
    const char* _Locname,  
    category _Cat);

template <class Facet>  
locale(
 const locale& _Loc,   
    const Facet* _Fac);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Locname`  
 로캘의의 이름입니다.  
  
 `_Loc`  
 새 로캘을 구성할 때 복사 되는 로캘.  
  
 `_Other`  
 범주를 선택할 수 있는 로캘.  
  
 `_Cat`  
 범주에 생성 된 로캘을 대체입니다.  
  
 `_Fac`  
 생성 된 로캘에 대체에 사용 되는 패싯.  
  
### <a name="remarks"></a>설명  
 첫 번째 생성자는 전역 로캘과 일치 하도록 개체를 초기화 합니다. 두 번째 및 세 번째 생성자는 동작이 로캘 이름과 일치 하도록 모든 로캘 범주를 초기화 `_Locname`합니다. 나머지 생성자 복사 `_Loc`, 와 같이 예외가 있습니다.  
  
 `locale(const locale& _Loc, const locale& _Other, category _Cat);`  
  
 대체 `_Other` 범주에 해당 하는 C는 C에 대 한 이러한 패싯을 & `_Cat` 0입니다.  
  
 `locale(const locale& _Loc, const char* _Locname, category _Cat);`  
  
 `locale(const locale& _Loc, const string& _Locname, category _Cat);`  
  
 대체 `locale(_Locname, _All)` 범주에 해당 하는 C는 C에 대 한 이러한 패싯을 & `_Cat`0입니다.  
  
 `template<class Facet> locale(const locale& _Loc, Facet* _Fac);`  
  
 바꿉니다 (또는 추가) `_Loc` 패싯 `_Fac`, 경우 `_Fac` 는 null 포인터가 아니어야 합니다.  
  
 로캘 이름 경우 `_Locname` 가 null 포인터 또는 함수를 유효 하지 않음 throw [runtime_error](../standard-library/runtime-error-class.md).  
  
### <a name="example"></a>예제  
  
```  
// locale_locale.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <tchar.h>  
using namespace std;  
  
int main( ) {  
  
   // Second constructor  
   locale loc ( "German_germany" );  
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s, it comes before z in the German alphabet  
   _TCHAR * s2 = _T("Das ist weizzz.");  
   int result1 = use_facet<collate<_TCHAR> > ( loc ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc ) << result1 << endl;  
  
   // The first (default) constructor  
   locale loc2;  
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc2 )  << result2 << endl;  
  
   // Third constructor  
   locale loc3 (loc2,loc, _M_COLLATE );  
   int result3 = use_facet<collate<_TCHAR> > ( loc3 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc3 ) << result3 << endl;  
  
   // Fourth constructor  
   locale loc4 (loc2, "German_Germany", _M_COLLATE );  
   int result4 = use_facet<collate<_TCHAR> > ( loc4 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc4 ) << result4 << endl;  
}  
```  
  
##  <a name="a-namelocalenamea-localename"></a><a name="locale__name"></a>  locale:: name  
 저장된 로캘 이름을 반환합니다.  
  
```  
string name() const;
```  
  
### <a name="return-value"></a>반환 값  
 로캘 이름을 지정 하는 문자열입니다.  
  
### <a name="example"></a>예제  
  
```  
// locale_name.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
using namespace std;  
  
int main( )   
{  
   locale loc1( "german" );  
   locale loc2 = locale::global( loc1 );  
   cout << "The name of the previous locale is: "   
        << loc2.name( ) << "." << endl;  
   cout << "The name of the current locale is: "   
        << loc1.name( ) << "." << endl;  
}  
```  
  
```Output  
The name of the previous locale is: C.  
The name of the current locale is: German_Germany.1252.  
```  
  
##  <a name="a-namelocaleoperatorneqa-localeoperator"></a><a name="locale__operator_neq"></a>  locale:: operator! =  
 두 로캘이 다른지 테스트합니다.  
  
```  
bool operator!=(const locale& right) const;
```  
  
### <a name="parameters"></a>매개 변수  
 ` right`  
 같지 않은지 테스트할 로캘 중 하나입니다.  
  
### <a name="return-value"></a>반환 값  
 부울 값이 **true** 로캘을 동일한 로캘로;의 복사본이 없는 경우 **false** 경우 로캘을 복사본이 동일한 로캘로 설정 됩니다.  
  
### <a name="remarks"></a>설명  
 두 로캘이 다른 사본을 경우 동일한 로캘로 또는 이름이 같은 경우 동일 합니다.  
  
### <a name="example"></a>예제  
  
```  
// locale_op_ne.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
using namespace std;  
  
int main( )   
{  
   locale loc1( "German_Germany" );  
   locale loc2( "German_Germany" );  
   locale loc3( "English" );  
  
   if ( loc1 != loc2 )  
      cout << "locales loc1 (" << loc1.name( )  
      << ") and\n loc2 (" << loc2.name( ) << ") are not equal." << endl;  
   else  
      cout << "locales loc1 (" << loc1.name( )  
      << ") and\n loc2 (" << loc2.name( ) << ") are equal." << endl;  
  
   if ( loc1 != loc3 )  
      cout << "locales loc1 (" << loc1.name( )  
      << ") and\n loc3 (" << loc3.name( ) << ") are not equal." << endl;  
   else  
      cout << "locales loc1 (" << loc1.name( )  
      << ") and\n loc3 (" << loc3.name( ) << ") are equal." << endl;  
}  
```  
  
```Output  
locales loc1 (German_Germany.1252) and  
 loc2 (German_Germany.1252) are equal.  
locales loc1 (German_Germany.1252) and  
 loc3 (English_United States.1252) are not equal.  
```  
  
##  <a name="a-namelocaleoperatora-localeoperator"></a><a name="locale__operator__"></a>  locale:: operator)  
 두 `basic_string` 개체를 비교합니다.  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator()(
    const basic_string<CharType, Traits, Allocator>& left,  
    const basic_string<CharType, Traits, Allocator>& right) const;
```  
  
### <a name="parameters"></a>매개 변수  
 ` left`  
 왼쪽된 문자열입니다.  
  
 ` right`  
 오른쪽 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 멤버 함수를 반환합니다.  
  
-   첫 번째 시퀀스 비교 하는 두 번째 시퀀스 보다 적은 경우-1입니다.  
  
-   두 번째 시퀀스 비교 하는 첫 번째 시퀀스 보다 작은 경우 + 1입니다.  
  
-   시퀀스는 해당 하는 경우 0입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수를 효과적으로 실행 합니다.  
  
```  
const collate<CharType>& fac = use_fac<collate<CharType>>(*this);

return (fac.compare(left.begin(), left.end(), right.begin(), right.end()) <0);
```  
  
 따라서 함수 개체로 로캘 개체를 사용할 수 있습니다.  
  
### <a name="example"></a>예제  
  
```  
// locale_op_compare.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
int main( )   
{  
   using namespace std;  
   wchar_t *sa = L"ztesting";  
   wchar_t *sb = L"\0x00DFtesting";  
   basic_string<wchar_t> a( sa );  
   basic_string<wchar_t> b( sb );  
  
   locale loc( "German_Germany" );  
   cout << loc( a,b ) << endl;  
  
   const collate<wchar_t>& fac = use_facet<collate<wchar_t> >( loc );  
   cout << ( fac.compare( sa, sa + a.length( ),  
       sb, sb + b.length( ) ) < 0) << endl;  
}  
```  
  
```Output  
0  
0  
```  
  
##  <a name="a-namelocaleoperatoreqeqa-localeoperator"></a><a name="locale__operator_eq_eq"></a>  locale:: operator = =  
 두 로캘이 같은지 테스트합니다.  
  
```  
bool operator==(const locale& right) const;
```  
  
### <a name="parameters"></a>매개 변수  
 ` right`  
 같음에 대해 테스트 하는 로캘 중 하나입니다.  
  
### <a name="return-value"></a>반환 값  
 부울 값이 **true** 로캘을 복사본 동일한 로캘의 경우 **false** 로캘을 동일한 로캘로의 복사본이 없는 경우.  
  
### <a name="remarks"></a>설명  
 두 로캘이 다른 사본을 경우 동일한 로캘로 또는 이름이 같은 경우 동일 합니다.  
  
### <a name="example"></a>예제  
  
```  
// locale_op_eq.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
using namespace std;  
  
int main( )   
{  
   locale loc1( "German_Germany" );  
   locale loc2( "German_Germany" );  
   locale loc3( "English" );  
  
   if ( loc1 == loc2 )  
      cout << "locales loc1 (" << loc1.name( )  
      << ")\n and loc2 (" << loc2.name( ) << ") are equal."   
      << endl;  
   else  
      cout << "locales loc1 (" << loc1.name( )  
      << ")\n and loc2 (" << loc2.name( ) << ") are not equal."   
      << endl;  
  
   if ( loc1 == loc3 )  
      cout << "locales loc1 (" << loc1.name( )  
      << ")\n and loc3 (" << loc3.name( ) << ") are equal."   
      << endl;  
   else  
      cout << "locales loc1 (" << loc1.name( )  
      << ")\n and loc3 (" << loc3.name( ) << ") are not equal."   
      << endl;  
}  
```  
  
```Output  
locales loc1 (German_Germany.1252)  
 and loc2 (German_Germany.1252) are equal.  
locales loc1 (German_Germany.1252)  
 and loc3 (English_United States.1252) are not equal.  
```  
  
## <a name="see-also"></a>참고 항목  
 [\< 로캘>](../standard-library/locale.md)   
 [코드 페이지](../c-runtime-library/code-pages.md)   
 [로캘 이름, 언어 및 국가/지역 문자열](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)

