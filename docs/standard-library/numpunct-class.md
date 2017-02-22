---
title: "numpunct 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xlocnum/std::numpunct"
  - "std::numpunct"
  - "numpunct"
  - "std.numpunct"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "numpunct 클래스"
ms.assetid: 73fb93cc-ac11-4c98-987c-bfa6267df596
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# numpunct 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CharType` 형식의 시퀀스에 대해 설명하는 로컬 패싯으로 사용할 수 있는 개체에 대해 설명하는 템플릿 클래스입니다. CharType 형식의 시퀀스는 숫자 및 부울 식의 서식 지정 및 문장 부호에 대한 정보를 나타내는 데 사용됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class CharType>  
class numpunct : public locale::facet;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `CharType`  
 로캘의 문자를 인코딩하기 위해 프로그램 내 사용하는 형식입니다.  
  
## <a name="remarks"></a>설명  
 모든 로캘 패싯과 마찬가지로, 고정 개체 ID에는 초기값 0이 저장되어 있습니다. 에 고유한 양수 값을 저장 하는 저장된 된 값에 액세스 하려고 하는 첫 번째 **id입니다.**  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[numpunct](#numpunct__numpunct)|`numpunct` 형식의 개체에 대한 생성자입니다.|  
  
### <a name="typedefs"></a>형식 정의  
  
|||  
|-|-|  
|[char_type](#numpunct__char_type)|로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.|  
|[string_type](#numpunct__string_type)|`CharType` 형식의 문자가 포함된 문자열을 설명하는 형식입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[decimal_point](#numpunct__decimal_point)|소수점으로 사용할 로캘별 요소를 반환합니다.|  
|[do_decimal_point](#numpunct__do_decimal_point)|소수점으로 사용할 로캘별 요소를 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.|  
|[do_falsename](#numpunct__do_falsename)|`false` 값을 텍스트로 표현하는 데 사용할 문자열을 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.|  
|[do_grouping](#numpunct__do_grouping)|소수점 자리 왼쪽의 숫자를 그룹화하는 방법을 결정하는 로캘별 규칙을 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.|  
|[do_thousands_sep](#numpunct__do_thousands_sep)|1000 단위 구분 기호로 사용할 로캘별 요소를 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.|  
|[do_truename](#numpunct__do_truename)|`true` 값을 텍스트로 표현하는 데 사용할 문자열을 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.|  
|[falsename](#numpunct__falsename)|`false` 값을 텍스트로 표현하기 위해 사용할 문자열을 반환합니다.|  
|[그룹화](#numpunct__grouping)|소수점 왼쪽의 숫자를 그룹화할 방법을 결정하기 위한 로캘별 규칙을 반환합니다.|  
|[thousands_sep](#numpunct__thousands_sep)|1000 단위 구분 기호로 사용할 로캘별 요소를 반환합니다.|  
|[truename](#numpunct__truename)|`true` 값을 텍스트로 표현하기 위해 사용할 문자열을 반환합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \< 로캘>  
  
 **네임스페이스:** std  
  
##  <a name="a-namenumpunctchartypea-numpunctchartype"></a><a name="numpunct__char_type"></a>  numpunct:: char_type  
 로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>설명  
 형식은 템플릿 매개 변수는 동의어 **CharType 합니다.**  
  
##  <a name="a-namenumpunctdecimalpointa-numpunctdecimalpoint"></a><a name="numpunct__decimal_point"></a>  numpunct:: decimal_point  
 소수점으로 사용할 로캘별 요소를 반환합니다.  
  
```  
CharType decimal_point() const;
```  
  
### <a name="return-value"></a>반환 값  
 소수점으로 사용할 로캘별 요소입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 반환 [do_decimal_point](#numpunct__do_decimal_point)합니다.  
  
### <a name="example"></a>예제  
  
```  
// numpunct_decimal_point.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const numpunct <char> &npunct =   
   use_facet <numpunct <char> >( loc);  
   cout << loc.name( ) << " decimal point "<<   
   npunct.decimal_point( ) << endl;  
   cout << loc.name( ) << " thousands separator "   
   << npunct.thousands_sep( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 decimal point ,  
German_Germany.1252 thousands separator .  
```  
  
##  <a name="a-namenumpunctdodecimalpointa-numpunctdodecimalpoint"></a><a name="numpunct__do_decimal_point"></a>  numpunct:: do_decimal_point  
 소수점으로 사용할 로캘별 요소를 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.  
  
```  
virtual CharType do_decimal_point() const;
```  
  
### <a name="return-value"></a>반환 값  
 소수점으로 사용할 로캘별 요소입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [decimal_point](#numpunct__decimal_point), 에서 가상 멤버 함수를 호출 하는 경우, `decimal_point`합니다.  
  
##  <a name="a-namenumpunctdofalsenamea-numpunctdofalsename"></a><a name="numpunct__do_falsename"></a>  numpunct:: do_falsename  
 값의 텍스트 표현으로 사용 하 여 시퀀스를 반환 하는 보호 된 가상 멤버 함수 **false**합니다.  
  
```  
virtual string_type do_falsename() const;
```  
  
### <a name="return-value"></a>반환 값  
 값의 텍스트 표현으로 사용 하는 순서를 포함 하는 문자열 **false**합니다.  
  
### <a name="remarks"></a>설명  
 "False" 값을 나타내는 문자열을 반환 하는 멤버 함수 **false** 모든 로캘에서 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [falsename](#numpunct__falsename), 에서 가상 멤버 함수를 호출 하는 경우, `falsename`합니다.  
  
##  <a name="a-namenumpunctdogroupinga-numpunctdogrouping"></a><a name="numpunct__do_grouping"></a>  numpunct:: do_grouping  
 소수점 자리 왼쪽의 숫자를 그룹화하는 방법을 결정하는 로캘별 규칙을 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.  
  
```  
virtual string do_grouping() const;
```  
  
### <a name="return-value"></a>반환 값  
 숫자를 소수점의 왼쪽에 그룹화 하는 방법을 결정 하기 위한 로캘별 규칙입니다.  
  
### <a name="remarks"></a>설명  
 보호된 가상 멤버 함수가 소수점 자리 왼쪽의 숫자를 그룹화하는 방법을 결정하는 로캘별 규칙을 반환합니다. 인코딩이 동일한 방식으로 **lconv::grouping**합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [그룹화](#numpunct__grouping), 에서 가상 멤버 함수를 호출 하는 경우, **그룹화**합니다.  
  
##  <a name="a-namenumpunctdothousandssepa-numpunctdothousandssep"></a><a name="numpunct__do_thousands_sep"></a>  numpunct:: do_thousands_sep  
 1000 단위 구분 기호로 사용할 로캘별 요소를 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.  
  
```  
virtual CharType do_thousands_sep() const;
```  
  
### <a name="return-value"></a>반환 값  
 1000 단위 구분 기호로 사용할 로캘별 요소를 반환합니다.  
  
### <a name="remarks"></a>설명  
 형식의 로캘별 요소를 반환 하는 보호 된 가상 멤버 함수 **CharType** 소수점의 왼쪽에는 그룹 구분 기호로 사용 하도록 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [thousands_sep](#numpunct__thousands_sep), 에서 가상 멤버 함수를 호출 하는 경우, `thousands_sep`합니다.  
  
##  <a name="a-namenumpunctdotruenamea-numpunctdotruename"></a><a name="numpunct__do_truename"></a>  numpunct:: do_truename  
 가상 멤버 함수는 값의 텍스트 표현으로 사용 하는 문자열을 반환 하기 위해 호출 하는 보호 된 **true**합니다.  
  
```  
virtual string_type do_truename() const;
```  
  
### <a name="remarks"></a>설명  
 값의 텍스트 표현으로 사용 하는 문자열 **true**합니다.  
  
 "True" 값을 나타내는 문자열을 반환 하는 모든 로캘에서 **true**합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [truename](#numpunct__truename), 에서 가상 멤버 함수를 호출 하는 경우, `truename`합니다.  
  
##  <a name="a-namenumpunctfalsenamea-numpunctfalsename"></a><a name="numpunct__falsename"></a>  numpunct:: falsename  
 값의 텍스트 표현으로 사용 하는 문자열을 반환 **false**합니다.  
  
```  
string_type falsename() const;
```  
  
### <a name="return-value"></a>반환 값  
 시퀀스를 포함 하는 문자열 **CharType**값의 텍스트 표현으로 사용 하 여 s **false**합니다.  
  
### <a name="remarks"></a>설명  
 "False" 값을 나타내는 문자열을 반환 하는 멤버 함수 **false** 모든 로캘에서 합니다.  
  
 멤버 함수는 반환 [do_falsename](#numpunct__do_falsename)합니다.  
  
### <a name="example"></a>예제  
  
```  
// numpunct_falsename.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "English" );  
  
   const numpunct <char> &npunct = use_facet <numpunct <char> >( loc );  
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;  
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;  
  
   locale loc2( "French" );  
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >(loc2);  
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;  
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;  
}  
```  
  
```Output  
English_United States.1252 truename true  
English_United States.1252 falsename false  
French_France.1252 truename true  
French_France.1252 falsename false  
```  
  
##  <a name="a-namenumpunctgroupinga-numpunctgrouping"></a><a name="numpunct__grouping"></a>  numpunct:: grouping  
 소수점 왼쪽의 숫자를 그룹화할 방법을 결정하기 위한 로캘별 규칙을 반환합니다.  
  
```  
string grouping() const;
```  
  
### <a name="return-value"></a>반환 값  
 숫자를 소수점의 왼쪽에 그룹화 하는 방법을 결정 하기 위한 로캘별 규칙입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 반환 [do_grouping](#numpunct__do_grouping)합니다.  
  
### <a name="example"></a>예제  
  
```  
// numpunct_grouping.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany");  
  
   const numpunct <char> &npunct =   
       use_facet < numpunct <char> >( loc );  
   for (unsigned int i = 0; i < npunct.grouping( ).length( ); i++)  
   {  
      cout << loc.name( ) << " international grouping:\n the "  
           << i <<"th group to the left of the radix character "  
           << "is of size " << (int)(npunct.grouping ( )[i])   
           << endl;  
   }  
}  
```  
  
```Output  
German_Germany.1252 international grouping:  
 the 0th group to the left of the radix character is of size 3  
```  
  
##  <a name="a-namenumpunctnumpuncta-numpunctnumpunct"></a><a name="numpunct__numpunct"></a>  numpunct:: numpunct  
 `numpunct` 형식의 개체에 대한 생성자입니다.  
  
```  
explicit numpunct(size_t _Refs = 0);
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
  
##  <a name="a-namenumpunctstringtypea-numpunctstringtype"></a><a name="numpunct__string_type"></a>  numpunct:: string_type  
 형식의 문자를 포함 하는 문자열을 설명 하는 형식 **CharType**합니다.  
  
```  
typedef basic_string<CharType, Traits, Allocator> string_type;  
```  
  
### <a name="remarks"></a>설명  
 템플릿 클래스의 특수화를 설명 하는 형식 [basic_string](../standard-library/basic-string-class.md) 인 개체는 문장 부호 시퀀스의 복사본을 저장할 수 있습니다.  
  
##  <a name="a-namenumpunctthousandssepa-numpunctthousandssep"></a><a name="numpunct__thousands_sep"></a>  numpunct:: thousands_sep  
 1000 단위 구분 기호로 사용할 로캘별 요소를 반환합니다.  
  
```  
CharType thousands_sep() const;
```  
  
### <a name="return-value"></a>반환 값  
 1000으로 사용할 로캘별 요소를 구분 합니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 반환 [do_thousands_sep](#numpunct__do_thousands_sep)합니다.  
  
### <a name="example"></a>예제  
  
```  
// numpunct_thou_sep.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const numpunct <char> &npunct =   
   use_facet < numpunct < char > >( loc );  
   cout << loc.name( ) << " decimal point "<<   
   npunct.decimal_point( ) << endl;  
   cout << loc.name( ) << " thousands separator "   
   << npunct.thousands_sep( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 decimal point ,  
German_Germany.1252 thousands separator .  
```  
  
##  <a name="a-namenumpuncttruenamea-numpuncttruename"></a><a name="numpunct__truename"></a>  numpunct:: truename  
 값의 텍스트 표현으로 사용 하는 문자열을 반환 **true**합니다.  
  
```  
string_type falsename() const;
```  
  
### <a name="return-value"></a>반환 값  
 값의 텍스트 표현으로 사용 하는 문자열 **true**합니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 반환 [do_truename](#numpunct__do_truename)합니다.  
  
 "True" 값을 나타내는 문자열을 반환 하는 모든 로캘에서 **true**합니다.  
  
### <a name="example"></a>예제  
  
```  
// numpunct_truename.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "English" );  
  
   const numpunct < char> &npunct = use_facet <numpunct <char> >( loc );  
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;  
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;  
  
   locale loc2("French");  
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >( loc2 );  
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;  
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;  
}  
```  
  
```Output  
English_United States.1252 truename true  
English_United States.1252 falsename false  
French_France.1252 truename true  
French_France.1252 falsename false  
```  
  
## <a name="see-also"></a>참고 항목  
 [\< 로캘>](../standard-library/locale.md)   
 [facet 클래스](../standard-library/locale-class.md#facet_class)   
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)

