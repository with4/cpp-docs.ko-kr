---
title: "codecvt 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- codecvt
- xlocale/std::codecvt
- locale/std::codecvt::extern_type
- locale/std::codecvt::intern_type
- locale/std::codecvt::state_type
- locale/std::codecvt::always_noconv
- locale/std::codecvt::do_always_noconv
- locale/std::codecvt::do_encoding
- locale/std::codecvt::do_in
- locale/std::codecvt::do_length
- locale/std::codecvt::do_max_length
- locale/std::codecvt::do_out
- locale/std::codecvt::do_unshift
- locale/std::codecvt::encoding
- locale/std::codecvt::in
- locale/std::codecvt::length
- locale/std::codecvt::max_length
- locale/std::codecvt::out
- locale/std::codecvt::unshift
dev_langs:
- C++
helpviewer_keywords:
- codecvt class
ms.assetid: 37d3efa1-2b7f-42b6-b04f-7a972c8c2c86
caps.latest.revision: 23
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
ms.openlocfilehash: 2f96bb4a2eb577eb490b492ec425220ea5ce9eb3
ms.contentlocale: ko-kr
ms.lasthandoff: 04/29/2017

---
# <a name="codecvt-class"></a>codecvt 클래스
로캘 패싯으로 사용할 수 있는 개체를 설명하는 템플릿 클래스입니다. 프로그램 내의 문자를 인코딩하는 데 사용하는 값의 시퀀스와 프로그램 밖의 문자를 인코딩하는 데 사용하는 값 사이의 변환을 제어할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class CharType, class Byte, class StateType>  
class codecvt : public locale::facet, codecvt_base;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `CharType`  
 문자를 인코딩하기 위해 프로그램 내 사용하는 형식  
  
 `Byte`  
 프로그램 밖의 문자를 인코딩하는 데 사용되는 형식입니다.  
  
 `StateType`  
 내부 및 외부 문자 표현 형식 사이의 변환의 중간 상태를 나타내는 데 사용할 수 있는 형식입니다.  
  
## <a name="remarks"></a>설명  
 템플릿 클래스는 `CharType` 형식의 값 시퀀스와 `Byte` 형식의 값 시퀀스 간의 변환을 제어하기 위해 [로캘 패싯](../standard-library/locale-class.md#facet_class)으로 사용할 수 있는 개체에 대해 설명합니다. 클래스 `StateType`은 변환을 특성화하고 `StateType` 클래스의 개체는 변환 중 모든 상태 정보를 저장합니다.  
  
 내부 인코딩은 일반적으로 `char` 형식 또는 `wchar_t` 형식의 문자당 고정 바이트 수를 사용한 표현을 사용합니다.  
  
 모든 로캘 패싯과 마찬가지로, 고정 개체 `id`에는 초기값 0이 저장되어 있습니다. 저장된 값에 액세스를 처음 시도하면 `id`에 고유한 양수 값이 저장됩니다.  
  
 [do_in](#do_in) 및 [do_out](#do_out)의 템플릿 버전은 항상 `codecvt_base::noconv`를 반환합니다.  
  
 C++ 표준 라이브러리는 여러 명시적 특수화를 정의합니다.  
  
 `template<>`  
  
 `codecvt<wchar_t, char, mbstate_t>`  
  
 `wchar_t` 및 `char` 시퀀스 사이에서 변환합니다.  
  
 `template<>`  
  
 `codecvt<char16_t, char, mbstate_t>`  
  
 UTF-16으로 인코드된 `char16_t` 시퀀스와 UTF-8로 인코드된 `char` 시퀀스 사이에서 변환합니다.  
  
 `template<>`  
  
 `codecvt<char32_t, char, mbstate_t>`  
  
 UTF-32(UCS-4)로 인코드된 `char32_t` 시퀀스와 UTF-8로 인코드된 `char` 시퀀스 사이에서 변환합니다.  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[codecvt](#codecvt)|변환을 처리할 로캘 패싯으로 사용할 `codecvt` 클래스 개체의 생성자입니다.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[extern_type](#extern_type)|외부 표현에 사용되는 문자 형식입니다.|  
|[intern_type](#intern_type)|내부 표현에 사용되는 문자 형식입니다.|  
|[state_type](#state_type)|내부 및 외부 표현 사이의 변환 중간 상태를 나타내는 데 사용하는 문자 형식입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[always_noconv](#always_noconv)|변환을 수행해야 하는지 여부를 테스트합니다.|  
|[do_always_noconv](#do_always_noconv)|변환을 수행해야 하는지 여부를 테스트하기 위해 호출하는 가상 함수입니다.|  
|[do_encoding](#do_encoding)|`Byte` 스트림의 인코딩이 상태에 의존하는지 여부, 사용한 `Byte`와 만들어진 `CharType`의 비율이 일정한지 여부를 테스트하고, 그럴 경우, 해당 비율 값을 결정하는 가상 함수입니다.|  
|[do_in](#do_in)|내부 `Byte`의 시퀀스를 외부 `CharType`의 시퀀스로 변환하기 위해 호출하는 가상 함수입니다.|  
|[do_length](#do_length)|외부 `Byte`의 지정된 시퀀스 중 몇 `Byte`가 몇 개 이하의 내부 `CharType`을 만들고 같은 수의 `Byte`를 반환하는지를 결정하는 가상 함수입니다.|  
|[do_max_length](#do_max_length)|하나의 내부 `CharType`을 만드는 데 필요한 외부 바이트의 최대 수를 반환하는 가상 함수입니다.|  
|[do_out](#do_out)|내부 `CharType`의 시퀀스를 외부 바이트의 시퀀스로 변환하기 위해 호출하는 가상 함수입니다.|  
|[do_unshift](#do_unshift)|`Byte`의 시퀀스에서 마지막 문자를 완료하기 위해 상태 의존 변환에 필요한 `Byte`를 제공하기 위해 호출하는 가상 함수입니다.|  
|[encoding](#encoding)|`Byte` 스트림의 인코딩이 상태에 의존하는지 여부, 사용한 `Byte`와 만들어진 `CharType`의 비율이 일정한지 여부를 테스트하고, 그럴 경우, 해당 비율 값을 결정합니다.|  
|[in](#in)|`Byte`의 시퀀스의 외부 표현을 `CharType`의 시퀀스의 내부 표현으로 변환합니다.|  
|[length](#length)|외부 `Byte`의 지정된 시퀀스 중 몇 `Byte`가 몇 개 이하의 내부 `CharType`을 만들고 같은 수의 `Byte`를 반환하는지를 결정합니다.|  
|[max_length](#max_length)|하나의 내부 `Byte`을 만드는 데 필요한 외부 `CharType`의 최대 수를 반환합니다.|  
|[out](#out)|내부 `CharType`을 외부 `Byte`의 시퀀스로 변환합니다.|  
|[unshift](#unshift)|`Byte`의 시퀀스에서 마지막 문자를 완료하기 위해 상태 의존 변환에 필요한 외부 `Byte`를 제공합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<locale>  
  
 **네임스페이스:** std  
  
##  <a name="always_noconv"></a>  codecvt::always_noconv  
 변환을 수행해야 하는지 여부를 테스트합니다.  
  
```  
bool always_noconv() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 변환을 수행하지 않아도 되는 경우 **true**인 부울 값이고, 하나 이상의 변환을 수행해야 하는 경우 **false**인 부울 값입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 [do_always_noconv](#do_always_noconv)를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// codecvt_always_noconv.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   bool result1 = use_facet<codecvt<char, char, mbstate_t> >   
      ( loc ).always_noconv( );  
  
   if ( result1 )  
      cout << "No conversion is needed." << endl;  
   else  
      cout << "At least one conversion is required." << endl;  
  
   bool result2 = use_facet<codecvt<wchar_t, char, mbstate_t> >   
      ( loc ).always_noconv( );  
  
   if ( result2 )  
      cout << "No conversion is needed." << endl;  
   else  
      cout << "At least one conversion is required." << endl;  
}  
```  
  
```Output  
No conversion is needed.  
At least one conversion is required.  
```  
  
##  <a name="codecvt"></a>  codecvt::codecvt  
 변환을 처리할 로캘 패싯으로 사용하는 codecvt 클래스 개체의 생성자입니다.  
  
```  
explicit codecvt(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Refs`  
 개체에 대한 메모리 관리 형식을 지정하는 데 사용하는 정수값입니다.  
  
### <a name="remarks"></a>설명  
 `_Refs` 매개 변수에 대해 사용 가능한 값과 해당 중요도는 다음과 같습니다.  
  
-   0: 개체를 포함하는 로캘에 의해 개체의 수명이 관리됩니다.  
  
-   1: 개체의 수명을 수동으로 관리해야 합니다.  
  
-   \>1: 이러한 값은 정의 되지 않습니다.  
  
 생성자를 초기화 합니다. 해당 `locale::facet` 기준 개체와 **로캘::**[패싯](../standard-library/locale-class.md#facet_class)(`_Refs`).  
  
##  <a name="do_always_noconv"></a>  codecvt::do_always_noconv  
 변환을 수행해야 하는지 여부를 테스트하기 위해 호출하는 가상 함수입니다.  
  
```  
virtual bool do_always_noconv() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 [do_in](#do_in) 또는 [do_out](#do_out)에 대한 모든 호출이 **noconv**를 반환하는 경우에만 보호된 가상 멤버 함수가 **true**를 반환합니다.  
  
 템플릿 버전은 항상 **true**를 반환합니다.  
  
### <a name="example"></a>예제  
  `do_always_noconv`를 호출하는 [always_noconv](#always_noconv)에 대한 예제를 참조하세요.  
  
##  <a name="do_encoding"></a>  codecvt::do_encoding  
 **바이트** 스트림의 인코딩이 상태에 의존하는 경우 사용한 **바이트**와 생성한 **CharType** 간의 비율이 일정한지 여부를 테스트하고, 비율이 일정하면 해당 비율 값을 결정하는 가상 함수입니다.  
  
```  
virtual int do_encoding() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 보호된 가상 멤버 함수는 다음을 반환합니다.  
  
-   -1을 반환 하는 경우 형식의 시퀀스의 인코딩을 `extern_type` 상태를 따라 달라 집니다.  
  
-   0: 인코딩에 다양한 길이의 시퀀스가 포함된 경우  
  
- *N*: 인코딩에 *N* 길이의 시퀀스만 포함된 경우  
  
### <a name="example"></a>예제  
  `do_encoding`을 호출하는 [encoding](#encoding)에 대한 예제를 참조하세요.  
  
##  <a name="do_in"></a>  codecvt::do_in  
 외부 **바이트** 시퀀스를 내부 **CharType** 시퀀스로 변환하기 위해 호출하는 가상 함수입니다.  
  
```  
virtual result do_in(
    StateType& _State,  
    const Byte* first1,   
    const Byte* last1,   
    const Byte*& next1,  
    CharType* first2,  
    CharType* last2,  
    CharType*& next2,) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_State`  
 멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.  
  
 `first1`  
 변환할 시퀀스의 시작 부분에 대한 포인터입니다.  
  
 `last1`  
 변환할 시퀀스의 끝 부분에 대한 포인터입니다.  
  
 `next1`  
 변환된 시퀀스의 끝 너머에 있는 포인터로, 변환되지 않은 첫 번째 문자에 대한 포인터입니다.  
  
 `first2`  
 변환된 시퀀스의 시작 부분에 대한 포인터입니다.  
  
 `last2`  
 변환된 시퀀스의 끝 부분에 대한 포인터입니다.  
  
 `next2`  
 변환된 마지막 **CharType** 뒤에 오는 **CharType**에 대한 포인터로, 대상 시퀀스의 변경되지 않은 첫 번째 문자에 대한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 작업의 성공, 부분적 성공 또는 실패를 나타내는 반환입니다. 함수에서 다음을 반환합니다.  
  
- 소스 시퀀스의 형식이 잘못된 경우 **codecvt_base::error**  
  
- 함수가 변환을 수행하지 않은 경우 `codecvt_base::noconv`  
  
- 변환이 성공한 경우 **codecvt_base::ok**  
  
- 소스가 충분하지 않은 경우 또는 변환이 성공하기에는 대상이 충분히 크지 않은 경우 **codecvt_base::partial**  
  
### <a name="remarks"></a>설명  
 `_State`는 새 소스 시퀀스의 시작 부분에 있는 초기 변환 상태를 나타내야 합니다. 함수는 성공적인 변환의 현재 상태를 반영하기 위해 필요에 따라 해당 저장 값을 변경합니다. 저장 값은 달리 지정되지 않습니다.  
  
### <a name="example"></a>예제  
  `do_in`을 호출하는 [in](#in)에 대한 예제를 참조하세요.  
  
##  <a name="do_length"></a>  codecvt::do_length  
 외부 **바이트**의 지정된 시퀀스 중 몇 **바이트**가 지정된 수보다 많지 않은 내부 **CharType**을 생성하는지 결정하고 해당 **Byte** 수를 반환하는 가상 함수입니다.  
  
```  
virtual int do_length(
    const StateType& _State,  
    const Byte* first1,   
    const Byte* last1,  
    size_t _Len2) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_State`  
 멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.  
  
 `first1`  
 외부 시퀀스의 시작 부분에 대한 포인터입니다.  
  
 `last1`  
 외부 시퀀스의 끝 부분에 대한 포인터입니다.  
  
 `_Len2`  
 멤버 함수에서 반환할 수 있는 최대 **바이트** 수입니다.  
  
### <a name="return-value"></a>반환 값  
 [`first1`, `last1`)에서 외부 소스 시퀀스로 정의된 `_Len2`보다 크지 않은 최대 변환 수의 개수를 나타내는 정수입니다.  
  
### <a name="remarks"></a>설명  
 보호된 가상 멤버 함수가 `_State`(상태의 복사본), 일부 버퍼 `_Buf` 그리고 포인터 `next1` 및 `next2`에 대해 `do_in`(`_State`, `first1`, `last1`, `next1`, `_Buf`, `_Buf` + `_Len2`, `next2`)를 효과적으로 호출합니다.  
  
 그런 다음 반환 `next2`  -  **buf**합니다. 따라서 [`first1`, `last1`)에서 소스 시퀀스로 정의된 `_Len2`보다 크지 않은 최대 변환 수를 계산합니다.  
  
 서식 파일 버전은 항상 중에서 가장 작은 반환 `last1`  -  `first1` 및 `_Len2`합니다.  
  
### <a name="example"></a>예제  
  **do_length**를 호출하는 [length](#length)에 대한 예제를 참조하세요.  
  
##  <a name="do_max_length"></a>  codecvt::do_max_length  
 하나의 내부 **CharType**을 생성하는 데 필요한 최대 외부 **바이트** 수를 반환하는 가상 함수입니다.  
  
```  
virtual int do_max_length() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 하나의 **CharType**을 생성하는 데 필요한 최대 **바이트** 수입니다.  
  
### <a name="remarks"></a>설명  
 보호된 가상 멤버 함수가 `first1` 및 `last1`의 유효한 임의 값에 대해 [do_length](#do_length)(`first1`, `last1`, 1)로 반환할 수 있는 가장 큰 허용 가능 값을 반환합니다.  
  
### <a name="example"></a>예제  
  `do_max_length`를 호출하는 [max_length](#max_length)에 대한 예제를 참조하세요.  
  
##  <a name="do_out"></a>  codecvt::do_out  
 내부 **CharType** 시퀀스를 외부 **바이트** 시퀀스로 변환하기 위해 호출하는 가상 함수입니다.  
  
```  
virtual result do_out(
    StateType& _State,  
    const CharType* first1,   
    const CharType* last1,  
    const CharType*& next1,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_State`  
 멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.  
  
 `first1`  
 변환할 시퀀스의 시작 부분에 대한 포인터입니다.  
  
 `last1`  
 변환할 시퀀스의 끝 부분에 대한 포인터입니다.  
  
 `next1`  
 마지막 **CharType**이 변환된 이후 나오는 변환되지 않은 첫 번째 **CharType**의 포인터에 대한 참조입니다.  
  
 `first2`  
 변환된 시퀀스의 시작 부분에 대한 포인터입니다.  
  
 `last2`  
 변환된 시퀀스의 끝 부분에 대한 포인터입니다.  
  
 `next2`  
 마지막 **바이트**가 변환된 이후 나오는 변환되지 않은 첫 번째 **바이트**의 포인터에 대한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 함수에서 다음을 반환합니다.  
  
- 소스 시퀀스의 형식이 잘못된 경우 **codecvt_base::error**  
  
- 함수가 변환을 수행하지 않은 경우 `codecvt_base::noconv`  
  
- 변환이 성공한 경우 **codecvt_base::ok**  
  
- 소스가 충분하지 않은 경우 또는 변환이 성공하기에는 대상이 충분히 크지 않은 경우 **codecvt_base::partial**.  
  
### <a name="remarks"></a>설명  
 `_State`는 새 소스 시퀀스의 시작 부분에 있는 초기 변환 상태를 나타내야 합니다. 함수는 성공적인 변환의 현재 상태를 반영하기 위해 필요에 따라 해당 저장 값을 변경합니다. 저장 값은 달리 지정되지 않습니다.  
  
### <a name="example"></a>예제  
  `do_out`을 호출하는 [out](#out)에 대한 예제를 참조하세요.  
  
##  <a name="do_unshift"></a>  codecvt::do_unshift  
 **바이트** 시퀀스의 마지막 문자를 완료하는 데 상태 의존 변환에 필요한 **바이트**를 제공하기 위해 호출하는 가상 함수입니다.  
  
```  
virtual result do_unshift(
    StateType& _State,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_State`  
 멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.  
  
 `first2`  
 대상 범위에서 첫 번째 위치에 대한 포인터입니다.  
  
 `last2`  
 대상 범위에서 마지막 위치에 대한 포인터입니다.  
  
 `next2`  
 대상 시퀀스의 변경되지 않은 첫 번째 요소에 대한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 함수에서 다음을 반환합니다.  
  
- _*State*가 잘못된 상태를 나타내는 경우 **codecvt_base::error**  
  
- 함수가 변환을 수행하지 않은 경우 `codecvt_base::noconv`  
  
- 변환이 성공한 경우 **codecvt_base::ok**  
  
- 변환이 성공하기에는 대상이 충분히 크지 않은 경우 **codecvt_base::partial**  
  
### <a name="remarks"></a>설명  
 보호된 가상 멤버 함수가 종료 요소 **Byte**(0)을 제외하고 [`first2`, `last2`) 내에 저장하는 대상 시퀀스로 소스 요소 **CharType**(0)을 변환하려고 합니다. 이 함수는 대상 시퀀스의 변경되지 않은 첫 번째 요소에 대한 포인터를 항상 `next2`에 저장합니다.  
  
 _*State*는 새 소스 시퀀스의 시작 부분에 있는 초기 변환 상태를 나타내야 합니다. 함수는 성공적인 변환의 현재 상태를 반영하기 위해 필요에 따라 해당 저장 값을 변경합니다. 일반적으로 소스 요소 **CharType**(0)을 변환하면 현재 상태가 초기 변환 상태로 유지됩니다.  
  
### <a name="example"></a>예제  
  `do_unshift`를 호출하는 [unshift](#unshift)에 대한 예제를 참조하세요.  
  
##  <a name="encoding"></a>  codecvt::encoding  
 **바이트** 스트림의 인코딩이 상태에 의존하는 경우 사용한 **바이트**와 생성한 **CharType** 간의 비율이 일정한지 여부를 테스트하고, 비율이 일정하면 해당 비율 값을 결정합니다.  
  
```  
int encoding() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 값이 양수이면 해당 값은 **CharType** 문자를 생성하는 데 필요한 일정한 수의 **바이트** 문자입니다.  
  
 보호된 가상 멤버 함수는 다음을 반환합니다.  
  
-   -1을 반환 하는 경우 형식의 시퀀스의 인코딩을 `extern_type` 상태를 따라 달라 집니다.  
  
-   0: 인코딩에 다양한 길이의 시퀀스가 포함된 경우  
  
- *N*: 인코딩에 *N* 길이의 시퀀스만 포함된 경우  
  
### <a name="remarks"></a>설명  
 멤버 함수는 [do_encoding](#do_encoding)을 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// codecvt_encoding.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   int result1 = use_facet<codecvt<char, char, mbstate_t> > ( loc ).encoding ( );  
   cout << result1 << endl;  
   result1 = use_facet<codecvt<wchar_t, char, mbstate_t> > ( loc ).encoding( );  
   cout << result1 << endl;  
   result1 = use_facet<codecvt<char, wchar_t, mbstate_t> > ( loc ).encoding( );  
   cout << result1 << endl;  
}  
```  
  
```Output  
1  
1  
1  
```  
  
##  <a name="extern_type"></a>  codecvt::extern_type  
 외부 표현에 사용되는 문자 형식입니다.  
  
```  
typedef Byte extern_type;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 템플릿 매개 변수 **Byte**의 동의어입니다.  
  
##  <a name="in"></a>  codecvt::in  
 **바이트** 시퀀스의 외부 표현을 **CharType** 시퀀스의 내부 표현으로 변환합니다.  
  
```  
result in(
    StateType& _State,  
    const Byte* first1,   
    const Byte* last1,   
    const Byte*& next1,  
    CharType* first2,  
    CharType* last2,  
    CharType*& next2,) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_State`  
 멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.  
  
 `first1`  
 변환할 시퀀스의 시작 부분에 대한 포인터입니다.  
  
 `last1`  
 변환할 시퀀스의 끝 부분에 대한 포인터입니다.  
  
 `next1`  
 변환된 시퀀스의 끝 너머에 있는 포인터로, 변환되지 않은 첫 번째 문자에 대한 포인터입니다.  
  
 `first2`  
 변환된 시퀀스의 시작 부분에 대한 포인터입니다.  
  
 `last2`  
 변환된 시퀀스의 끝 부분에 대한 포인터입니다.  
  
 `next2`  
 변환된 마지막 **Chartype** 뒤에 오는 **CharType**에 대한 포인터로, 대상 시퀀스의 변경되지 않은 첫 번째 문자에 대한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 작업의 성공, 부분적 성공 또는 실패를 나타내는 반환입니다. 함수에서 다음을 반환합니다.  
  
- 소스 시퀀스의 형식이 잘못된 경우 **codecvt_base::error**  
  
- 함수가 변환을 수행하지 않은 경우 `codecvt_base::noconv`  
  
- 변환이 성공한 경우 **codecvt_base::ok**  
  
- 소스가 충분하지 않은 경우 또는 변환이 성공하기에는 대상이 충분히 크지 않은 경우 **codecvt_base::partial**.  
  
### <a name="remarks"></a>설명  
 `_State`는 새 소스 시퀀스의 시작 부분에 있는 초기 변환 상태를 나타내야 합니다. 함수는 성공적인 변환의 현재 상태를 반영하기 위해 필요에 따라 해당 저장 값을 변경합니다. 일부 변환 이후 새 문자가 도착할 때 변환이 다시 시작할 수 있도록 `_State`를 설정해야 합니다.  
  
 멤버 함수가 [do_in](#do_in)(`_State`, _ *First1,  last1,  next1, First2, _Llast2,  next2*)를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// codecvt_in.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
using namespace std;  
#define LEN 90  
int main( )     
{  
   char* pszExt = "This is the string to be converted!";  
   wchar_t pwszInt [LEN+1];  
   memset(&pwszInt[0], 0, (sizeof(wchar_t))*(LEN+1));  
   const char* pszNext;  
   wchar_t* pwszNext;  
   mbstate_t state = {0};  
   locale loc("C");//English_Britain");//German_Germany  
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >  
     ( loc ).in( state,  
          pszExt, &pszExt[strlen(pszExt)], pszNext,  
          pwszInt, &pwszInt[strlen(pszExt)], pwszNext );  
   pwszInt[strlen(pszExt)] = 0;  
   wcout << ( (res!=codecvt_base::error)  L"It worked! " : L"It didn't work! " )  
   << L"The converted string is:\n ["  
   << &pwszInt[0]  
   << L"]" << endl;  
   exit(-1);  
}  
```  
  
```Output  
It worked! The converted string is:  
 [This is the string to be converted!]  
```  
  
##  <a name="intern_type"></a>  codecvt::intern_type  
 내부 표현에 사용되는 문자 형식입니다.  
  
```  
typedef CharType intern_type;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 템플릿 매개 변수 **CharType**의 동의어입니다.  
  
##  <a name="length"></a>  codecvt::length  
 외부 **바이트**의 지정된 시퀀스 중 몇 **바이트**가 지정된 수보다 많지 않은 내부 **CharType**을 생성하는지 결정하고 해당 **Byte** 수를 반환합니다.  
  
```  
int length(
    const StateType& _State,  
    const Byte* first1,   
    const Byte* last1,  
    size_t _Len2) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_State`  
 멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.  
  
 `first1`  
 외부 시퀀스의 시작 부분에 대한 포인터입니다.  
  
 `last1`  
 외부 시퀀스의 끝 부분에 대한 포인터입니다.  
  
 `_Len2`  
 멤버 함수에서 반환할 수 있는 최대 바이트 수입니다.  
  
### <a name="return-value"></a>반환 값  
 [`first1`, `last1`)에서 외부 소스 시퀀스로 정의된 `_Len2`보다 크지 않은 최대 변환 수의 개수를 나타내는 정수입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수가 [do_length](#do_length)(*_State,  first1*, `last1`, `_Len2`)를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// codecvt_length.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
using namespace std;  
#define LEN 90  
int main( )     
{  
   char* pszExt = "This is the string whose length is to be measured!";  
   mbstate_t state = {0};  
   locale loc("C");//English_Britain");//German_Germany  
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >  
     ( loc ).length( state,  
          pszExt, &pszExt[strlen(pszExt)], LEN );  
   cout << "The length of the string is: ";  
   wcout << res;  
   cout << "." << endl;  
   exit(-1);  
}  
```  
  
```Output  
The length of the string is: 50.  
```  
  
##  <a name="max_length"></a>  codecvt::max_length  
 하나의 내부 **CharType**을 생성하는 데 필요한 최대 외부 **바이트** 수를 반환합니다.  
  
```  
int max_length() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 하나의 **CharType**을 생성하는 데 필요한 최대 **바이트** 수입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 [do_max_length](#do_max_length)를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// codecvt_max_length.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc( "C");//English_Britain" );//German_Germany  
   int res = use_facet<codecvt<char, char, mbstate_t> >  
     ( loc ).max_length( );  
   wcout << res << endl;  
}  
```  
  
```Output  
1  
```  
  
##  <a name="out"></a>  codecvt::out  
 내부 **CharType** 시퀀스를 외부 **바이트** 시퀀스로 변환합니다.  
  
```  
result out(
    StateType& _State,  
    const CharType* first1,   
    const CharType* last1,  
    const CharType*& next1,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_State`  
 멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.  
  
 `first1`  
 변환할 시퀀스의 시작 부분에 대한 포인터입니다.  
  
 `last1`  
 변환할 시퀀스의 끝 부분에 대한 포인터입니다.  
  
 `next1`  
 마지막 **CharType**이 변환된 이후 나오는 변환되지 않은 첫 번째 **CharType**의 포인터에 대한 참조입니다.  
  
 `first2`  
 변환된 시퀀스의 시작 부분에 대한 포인터입니다.  
  
 `last2`  
 변환된 시퀀스의 끝 부분에 대한 포인터입니다.  
  
 `next2`  
 마지막으로 변환된 **바이트** 뒤에 나오는 변환되지 않은 첫 번째 **바이트**의 포인터에 대한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 멤버 함수는 [do_out](#do_out)(`_State`, `first1`, `last1`, `next1`, `first2`, `last2`, `next2`)를 반환합니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 [codecvt::do_out](#do_out)을 참조하세요.  
  
### <a name="example"></a>예제  
  
```cpp  
// codecvt_out.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
#include <wchar.h>  
using namespace std;  
#define LEN 90  
int main( )     
{  
   char pszExt[LEN+1];  
   wchar_t *pwszInt = L"This is the wchar_t string to be converted.";  
   memset( &pszExt[0], 0, ( sizeof( char ) )*( LEN+1 ) );  
   char* pszNext;  
   const wchar_t* pwszNext;  
   mbstate_t state;  
   locale loc("C");//English_Britain");//German_Germany  
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >  
      ( loc ).out( state,  
      pwszInt, &pwszInt[wcslen( pwszInt )], pwszNext ,  
      pszExt, &pszExt[wcslen( pwszInt )], pszNext );  
   pszExt[wcslen( pwszInt )] = 0;  
   cout << ( ( res!=codecvt_base::error )  "It worked: " : "It didn't work: " )  
   << "The converted string is:\n ["  
   << &pszExt[0]  
   << "]" << endl;  
}  
```  
  
```Output  
It worked: The converted string is:  
 [This is the wchar_t string to be converted.]  
```  
  
##  <a name="state_type"></a>  codecvt::state_type  
 내부 및 외부 표현 사이의 변환 중간 상태를 나타내는 데 사용하는 문자 형식입니다.  
  
```  
typedef StateType state_type;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 템플릿 매개 변수 **StateType**의 동의어입니다.  
  
##  <a name="unshift"></a>  codecvt::unshift  
 **바이트** 시퀀스의 마지막 문자를 완료하는 데 상태 의존 변환에 필요한 **바이트**를 제공합니다.  
  
```  
result unshift(
    StateType& _State,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_State`  
 멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.  
  
 `first2`  
 대상 범위에서 첫 번째 위치에 대한 포인터입니다.  
  
 `last2`  
 대상 범위에서 마지막 위치에 대한 포인터입니다.  
  
 `next2`  
 대상 시퀀스의 변경되지 않은 첫 번째 요소에 대한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 함수에서 다음을 반환합니다.  
  
- 상태가 잘못된 상태를 나타내는 경우 **codecvt_base::error**  
  
- 함수가 변환을 수행하지 않은 경우 `codecvt_base::noconv`  
  
- 변환이 성공한 경우 **codecvt_base::ok**  
  
- 변환이 성공하기에는 대상이 충분히 크지 않은 경우 **codecvt_base::partial**  
  
### <a name="remarks"></a>설명  
 보호된 가상 멤버 함수가 종료 요소 **Byte**(0)을 제외하고 [`first2`, `last2`) 내에 저장하는 대상 시퀀스로 소스 요소 **CharType**(0)을 변환하려고 합니다. 이 함수는 대상 시퀀스의 변경되지 않은 첫 번째 요소에 대한 포인터를 항상 `next2`에 저장합니다.  
  
 `_State`는 새 소스 시퀀스의 시작 부분에 있는 초기 변환 상태를 나타내야 합니다. 함수는 성공적인 변환의 현재 상태를 반영하기 위해 필요에 따라 해당 저장 값을 변경합니다. 일반적으로 소스 요소 **CharType**(0)을 변환하면 현재 상태가 초기 변환 상태로 유지됩니다.  
  
 멤버 함수는 [do_unshift](#do_unshift)(`_State`, `first2`, `last2`, `next2`)를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<locale>](../standard-library/locale.md)   
 [코드 페이지](../c-runtime-library/code-pages.md)   
 [로캘 이름, 언어 및 국가/지역 문자열](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)


