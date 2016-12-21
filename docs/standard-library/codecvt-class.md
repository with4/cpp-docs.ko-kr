---
title: "codecvt 클래스 | Microsoft Docs"
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
  - "codecvt"
  - "std::codecvt"
  - "std.codecvt"
  - "xlocale/std::codecvt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt 클래스"
ms.assetid: 37d3efa1-2b7f-42b6-b04f-7a972c8c2c86
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# codecvt 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

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
 로 사용할 수 있는 개체를 설명 하는 템플릿 클래스는 [로캘 패싯](../standard-library/locale-class.md#facet_class), 형식 값의 시퀀스 사이의 변환을 제어 하기 위해 `CharType` 형식의 값의 시퀀스와 `Byte`합니다. 클래스 `StateType`은 변환을 특성화하고 `StateType` 클래스의 개체는 변환 중 모든 상태 정보를 저장합니다.  
  
 내부 인코딩은 일반적으로 `char` 형식 또는 `wchar_t` 형식의 문자당 고정 바이트 수를 사용한 표현을 사용합니다.  
  
 모든 로캘 패싯과 마찬가지로, 고정 개체 `id`에는 초기값 0이 저장되어 있습니다. 에 고유한 양수 값을 저장 하는 저장된 된 값에 액세스 하려고 하는 첫 번째 `id`합니다.  
  
 템플릿 버전은 [do_in](#codecvt__do_in) 및 [do_out](#codecvt__do_out) 항상 반환 `codecvt_base::noconv`합니다.  
  
 표준 C++ 라이브러리는 여러 명시적 특수화를 정의합니다.  
  
 `template<>`  
  
 `codecvt<wchar_t, char, mbstate_t>`  
  
 `wchar_t` 및 `char` 시퀀스 사이에서 변환합니다.  
  
 `template<>`  
  
 `codecvt<char16_t, char, mbstate_t>`  
  
 UTF-16으로 인코딩된 `char16_t` 시퀀스와 UTF-8로 인코딩된 `char` 시퀀스 사이에서 변환합니다.  
  
 `template<>`  
  
 `codecvt<char32_t, char, mbstate_t>`  
  
 UTF-32(UCS-4)로 인코딩된 `char32_t` 시퀀스와 UTF-8로 인코딩된 `char` 시퀀스 사이에서 변환합니다.  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[codecvt](#codecvt__codecvt)|변환을 처리할 로캘 패싯으로 사용할 `codecvt` 클래스 개체의 생성자입니다.|  
  
### <a name="typedefs"></a>형식 정의  
  
|||  
|-|-|  
|[extern_type](#codecvt__extern_type)|외부 표현에 사용되는 문자 형식입니다.|  
|[intern_type](#codecvt__intern_type)|내부 표현에 사용되는 문자 형식입니다.|  
|[state_type](#codecvt__state_type)|내부 및 외부 표현 사이의 변환 중간 상태를 나타내는 데 사용하는 문자 형식입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[always_noconv](#codecvt__always_noconv)|변환을 수행해야 하는지 여부를 테스트합니다.|  
|[do_always_noconv](#codecvt__do_always_noconv)|변환을 수행해야 하는지 여부를 테스트하기 위해 호출하는 가상 함수입니다.|  
|[do_encoding](#codecvt__do_encoding)|`Byte` 스트림의 인코딩이 상태에 의존하는지 여부, 사용한 `Byte`와 만들어진 `CharType`의 비율이 일정한지 여부를 테스트하고, 그럴 경우, 해당 비율 값을 결정하는 가상 함수입니다.|  
|[do_in](#codecvt__do_in)|내부 `Byte`의 시퀀스를 외부 `CharType`의 시퀀스로 변환하기 위해 호출하는 가상 함수입니다.|  
|[do_length](#codecvt__do_length)|외부 `Byte`의 지정된 시퀀스 중 몇 `Byte`가 몇 개 이하의 내부 `CharType`을 만들고 같은 수의 `Byte`를 반환하는지를 결정하는 가상 함수입니다.|  
|[do_max_length](#codecvt__do_max_length)|하나의 내부 `CharType`을 만드는 데 필요한 외부 바이트의 최대 수를 반환하는 가상 함수입니다.|  
|[do_out](#codecvt__do_out)|내부 `CharType`의 시퀀스를 외부 바이트의 시퀀스로 변환하기 위해 호출하는 가상 함수입니다.|  
|[do_unshift](#codecvt__do_unshift)|`Byte`의 시퀀스에서 마지막 문자를 완료하기 위해 상태 의존 변환에 필요한 `Byte`를 제공하기 위해 호출하는 가상 함수입니다.|  
|[인코딩](#codecvt__encoding)|`Byte` 스트림의 인코딩이 상태에 의존하는지 여부, 사용한 `Byte`와 만들어진 `CharType`의 비율이 일정한지 여부를 테스트하고, 그럴 경우, 해당 비율 값을 결정합니다.|  
|[에서](#codecvt__in)|`Byte`의 시퀀스의 외부 표현을 `CharType`의 시퀀스의 내부 표현으로 변환합니다.|  
|[길이](#codecvt__length)|외부 `Byte`의 지정된 시퀀스 중 몇 `Byte`가 몇 개 이하의 내부 `CharType`을 만들고 같은 수의 `Byte`를 반환하는지를 결정합니다.|  
|[max_length](#codecvt__max_length)|하나의 내부 `Byte`을 만드는 데 필요한 외부 `CharType`의 최대 수를 반환합니다.|  
|[아웃](#codecvt__out)|내부 `CharType`을 외부 `Byte`의 시퀀스로 변환합니다.|  
|[unshift](#codecvt__unshift)|`Byte`의 시퀀스에서 마지막 문자를 완료하기 위해 상태 의존 변환에 필요한 외부 `Byte`를 제공합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \< 로캘>  
  
 **네임스페이스:** std  
  
##  <a name="a-namecodecvtalwaysnoconva-codecvtalwaysnoconv"></a><a name="codecvt__always_noconv"></a>  codecvt:: always_noconv  
 변환을 수행해야 하는지 여부를 테스트합니다.  
  
```  
bool always_noconv() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 부울 값이 **true** 변환이; 수행 해야 하는 경우 **false** 는 하나 이상의 작업을 수행 해야 합니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 반환 [do_always_noconv](#codecvt__do_always_noconv)합니다.  
  
### <a name="example"></a>예제  
  
```  
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
  
##  <a name="a-namecodecvtcodecvta-codecvtcodecvt"></a><a name="codecvt__codecvt"></a>  codecvt:: codecvt  
 변환을 처리할 로캘 패싯으로 사용 되는 클래스 codecvt의 개체에 대 한 생성자입니다.  
  
```  
explicit codecvt(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Refs`  
 개체에 대 한 메모리 관리의 유형을 지정 하는 데 사용 되는 정수 값입니다.  
  
### <a name="remarks"></a>설명  
 가능한 값은 `_Refs` 매개 변수 및 그 중요성은:  
  
-   0:를 포함 하는 로캘을에서 개체의 수명을 관리 합니다.  
  
-   1: 개체의 수명을 수동으로 관리 해야 합니다.  
  
-   \> 0:이 값이 정의 되지 않습니다.  
  
 생성자를 초기화 합니다. 해당 `locale::facet` 기준 개체와 **로캘::**[패싯](../standard-library/locale-class.md#facet_class)( `_Refs`) *합니다.*  
  
##  <a name="a-namecodecvtdoalwaysnoconva-codecvtdoalwaysnoconv"></a><a name="codecvt__do_always_noconv"></a>  codecvt:: do_always_noconv  
 변환을 수행해야 하는지 여부를 테스트하기 위해 호출하는 가상 함수입니다.  
  
```  
virtual bool do_always_noconv() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 보호 된 가상 멤버 함수는 반환 **true** 경우에만 호출 될 때마다 [do_in](#codecvt__do_in) 또는 [do_out](#codecvt__do_out) 반환 **noconv**합니다.  
  
 서식 파일 버전을 항상 반환 **true**합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [always_noconv](#codecvt__always_noconv), 를 호출 하 `do_always_noconv`합니다.  
  
##  <a name="a-namecodecvtdoencodinga-codecvtdoencoding"></a><a name="codecvt__do_encoding"></a>  codecvt:: do_encoding  
 있는지 여부를 테스트 하는 가상 함수의 인코딩을 **바이트** 상태에 의존, 여부 스트림이 사이의 비율은 **바이트**사용한 및 **CharType**만들어진 일정 하 고, 그렇다면 해당 비율 값을 결정 합니다.  
  
```  
virtual int do_encoding() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 보호 된 가상 멤버 함수를 반환합니다.  
  
-   -1을 하는 경우 형식의 시퀀스의 인코딩을 `extern_type` 상태를 따라 달라 집니다.  
  
-   다양 한 길이의 시퀀스는 인코딩하는 경우 0입니다.  
  
- *N*, 만 시퀀스의 길이 인코딩하는 경우, *N*  
  
### <a name="example"></a>예제  
  예를 참조 [인코딩](#codecvt__encoding), 되는 호출 `do_encoding`합니다.  
  
##  <a name="a-namecodecvtdoina-codecvtdoin"></a><a name="codecvt__do_in"></a>  codecvt:: do_in  
 외부의 시퀀스로 변환 하는 가상 함수 호출 **바이트**의 내부 시퀀스로 **CharType**s.  
  
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
 멤버 함수를 호출 사이 유지 관리 되는 변환 상태입니다.  
  
 ` first1`  
 변환할 시퀀스의 시작 부분에 대 한 포인터입니다.  
  
 ` last1`  
 변환할 시퀀스의 끝에 대 한 포인터입니다.  
  
 ` next1`  
 첫 번째 문자의 하는 변환 된 시퀀스의 끝을 넘어 포인터입니다.  
  
 ` first2`  
 변환 된 시퀀스의 시작 부분에 대 한 포인터입니다.  
  
 ` last2`  
 변환 된 시퀀스의 끝에 대 한 포인터입니다.  
  
 ` next2`  
 에 대 한 포인터는 **CharType** 마지막 변환 후 제공 되 **CharType**, 대상 시퀀스의 첫 번째 변경 되지 않은 문자입니다.  
  
### <a name="return-value"></a>반환 값  
 성공, 부분 성공 또는 작업의 실패를 나타내는 반환 합니다. 함수를 반환합니다.  
  
- **codecvt_base::error** 소스 시퀀스의 형식이 잘못 경우 형성 합니다.  
  
- `codecvt_base::noconv` 함수 변환을 수행 하지 않습니다 하는 경우.  
  
- **codecvt_base::ok** 변환이 성공 합니다.  
  
- **codecvt_base::partial** 소스 충분 하지 않은 경우 또는 대상을 성공적으로 변환에 대 한 충분히 크지 않으면.  
  
### <a name="remarks"></a>설명  
 `_State` 새 소스 시퀀스의 시작 부분에는 초기 변환 상태가 나타내야 합니다. 함수는 성공적으로 변환의 현재 상태를 반영 하기 위해 필요에 따라 저장된 된 값을 변경 합니다. 그렇지 않은 경우 저장된 된 값 지정 되지 않았습니다.  
  
### <a name="example"></a>예제  
  예를 참조 [에서](#codecvt__in), 를 호출 하 `do_in`합니다.  
  
##  <a name="a-namecodecvtdolengtha-codecvtdolength"></a><a name="codecvt__do_length"></a>  codecvt:: do_length  
 결정 하는 가상 함수를 얼마나 많은 **바이트**의 지정 된 시퀀스를 외부 **바이트**s 이하의 지정된 된 수의 내부 **CharType**s 해당 개수를 반환 하 고 **바이트**s.  
  
```  
virtual int do_length(
    const StateType& _State,  
    const Byte* first1,   
    const Byte* last1,  
    size_t _Len2) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_State`  
 멤버 함수를 호출 사이 유지 관리 되는 변환 상태입니다.  
  
 ` first1`  
 외부 시퀀스의 시작 부분에 대 한 포인터입니다.  
  
 ` last1`  
 외부 시퀀스의 끝에 대 한 포인터입니다.  
  
 `_Len2`  
 최대 **바이트**멤버 함수에 의해 반환 될 수 있는 s.  
  
### <a name="return-value"></a>반환 값  
 보다 크지 않음 변환의 최대 수의 개수를 나타내는 정수 `_Len2`, 에서 외부 소스 시퀀스에서 정의 된 [ ` first1`, ` last1`).  
  
### <a name="remarks"></a>설명  
 효과적으로 보호 된 가상 멤버 함수를 호출 `do_in`( `_State`, ` first1`, ` last1`, ` next1`, `_Buf`, `_Buf` + `_Len2`, ` next2`)에 대 한 `_State` (상태의 복사본)을 일부 버퍼 `_Buf`, 포인터 및 ` next1`및 ` next2`합니다.  
  
 그런 다음 반환 ` next2` – **buf**합니다. 따라서 변환 보다 크지 않음의 최대 수를 계산한 `_Len2`, 에서 소스 시퀀스에서 정의 된 [ ` first1`, ` last1`).  
  
 서식 파일 버전은 항상 중에서 가장 작은 반환 ` last1` – ` first1` 및 `_Len2`합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [길이](#codecvt__length), 를 호출 하 **do_length**합니다.  
  
##  <a name="a-namecodecvtdomaxlengtha-codecvtdomaxlength"></a><a name="codecvt__do_max_length"></a>  codecvt:: do_max_length  
 외부의 최대 수를 반환 하는 가상 함수 **바이트**하나의 내부를 만드는 데 필요한 **CharType**합니다.  
  
```  
virtual int do_max_length() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 최대 **바이트**하나를 만드는 데 필요한 **CharType**합니다.  
  
### <a name="remarks"></a>설명  
 보호 된 가상 멤버 함수에서 반환 될 수 있는 가장 큰 허용 가능한 값을 반환 [do_length](#codecvt__do_length)( ` first1`, ` last1`, 1)의 임의의 유효한 값에 대 한 ` first1` 및 ` last1`합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [max_length](#codecvt__max_length), 를 호출 하 `do_max_length`합니다.  
  
##  <a name="a-namecodecvtdoouta-codecvtdoout"></a><a name="codecvt__do_out"></a>  codecvt:: do_out  
 내부 시퀀스로 변환 하는 가상 함수 호출 **CharType**외부의 시퀀스로 **바이트**s.  
  
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
 멤버 함수를 호출 사이 유지 관리 되는 변환 상태입니다.  
  
 ` first1`  
 변환할 시퀀스의 시작 부분에 대 한 포인터입니다.  
  
 ` last1`  
 변환할 시퀀스의 끝에 대 한 포인터입니다.  
  
 ` next1`  
 첫 번째에 대 한 포인터에 대 한 참조 변환 되지 않은 **CharType**, 마지막 **CharType** 변환 합니다.  
  
 ` first2`  
 변환 된 시퀀스의 시작 부분에 대 한 포인터입니다.  
  
 ` last2`  
 변환 된 시퀀스의 끝에 대 한 포인터입니다.  
  
 ` next2`  
 첫 번째에 대 한 포인터에 대 한 참조 변환 되지 않은 **바이트**, 마지막 **바이트** 변환 합니다.  
  
### <a name="return-value"></a>반환 값  
 함수를 반환합니다.  
  
- **codecvt_base::error** 소스 시퀀스의 형식이 잘못 경우 형성 합니다.  
  
- `codecvt_base::noconv` 함수 변환을 수행 하지 않습니다 하는 경우.  
  
- **codecvt_base::ok** 변환이 성공 합니다.  
  
- **codecvt_base::partial** 소스 충분 하지 않은 경우 또는 대상이 너무 작아 변환에 성공 하는 경우.  
  
### <a name="remarks"></a>설명  
 `_State` 새 소스 시퀀스의 시작 부분에는 초기 변환 상태가 나타내야 합니다. 함수는 성공적으로 변환의 현재 상태를 반영 하기 위해 필요에 따라 저장된 된 값을 변경 합니다. 그렇지 않은 경우 저장된 된 값 지정 되지 않았습니다.  
  
### <a name="example"></a>예제  
  예를 참조 [아웃](#codecvt__out), 되는 호출 `do_out`합니다.  
  
##  <a name="a-namecodecvtdounshifta-codecvtdounshift"></a><a name="codecvt__do_unshift"></a>  codecvt:: do_unshift  
 가상 함수를 제공 하기 위해 호출 된 **바이트**시퀀스의 마지막 문자를 완료 하기 위해 상태 의존 변환에 필요한 s **바이트**s.  
  
```  
virtual result do_unshift(
    StateType& _State,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_State`  
 멤버 함수를 호출 사이 유지 관리 되는 변환 상태입니다.  
  
 ` first2`  
 대상 범위에서 첫 번째 위치에 대 한 포인터입니다.  
  
 ` last2`  
 대상 범위에서 마지막 위치에 대 한 포인터입니다.  
  
 ` next2`  
 대상 시퀀스의 첫 번째 변경 되지 않은 요소에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 함수를 반환합니다.  
  
- **codecvt_base::error** 경우 _ *상태* 잘못 된 상태를 나타냅니다.  
  
- `codecvt_base::noconv` 함수에는 변환이 수행 하는 경우  
  
- **codecvt_base::ok** 변환이 성공 하는 경우  
  
- **codecvt_base::partial** 대상이 너무 작아 변환에 성공 하는 경우  
  
### <a name="remarks"></a>설명  
 보호 된 가상 멤버 함수는 소스 요소를 변환 하려고 합니다. **CharType**(0) 내에서 저장 하는 대상 시퀀스에 [ ` first2`, ` last2`)를 종료 하는 요소를 제외 하 고 **바이트**(0). 에 항상 저장 ` next2` 대상 시퀀스의 첫 번째 변경 되지 않은 요소에 대 한 포인터입니다.  
  
 _ *상태* 새 소스 시퀀스의 시작 부분에는 초기 변환 상태가 나타내야 합니다. 함수는 성공적으로 변환의 현재 상태를 반영 하기 위해 필요에 따라 저장된 된 값을 변경 합니다. 일반적으로 소스 요소를 변환 **CharType**(0)는 초기 변환 상태가 현재 상태를 유지 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [unshift](#codecvt__unshift), 되는 호출 `do_unshift`합니다.  
  
##  <a name="a-namecodecvtencodinga-codecvtencoding"></a><a name="codecvt__encoding"></a>  codecvt:: encoding  
 테스트의 인코딩을 **바이트** 상태에 의존, 여부 스트림이 사이의 비율은 **바이트**사용한 및 **CharType**만들어진 일정을 하 고, 그렇다면 해당 비율 값을 결정 합니다.  
  
```  
int encoding() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 값이 양수인 경우 해당 값은 일정 개수의 **바이트** 생성 하는 데 필요한 문자는 **CharType** 문자입니다.  
  
 보호 된 가상 멤버 함수를 반환합니다.  
  
-   -1을 하는 경우 형식의 시퀀스의 인코딩을 `extern_type` 상태를 따라 달라 집니다.  
  
-   다양 한 길이의 시퀀스는 인코딩하는 경우 0입니다.  
  
- *N*, 만 시퀀스의 길이 인코딩하는 경우, *명사.*  
  
### <a name="remarks"></a>설명  
 멤버 함수는 반환 [do_encoding](#codecvt__do_encoding)합니다.  
  
### <a name="example"></a>예제  
  
```  
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
  
##  <a name="a-namecodecvtexterntypea-codecvtexterntype"></a><a name="codecvt__extern_type"></a>  codecvt:: extern_type  
 외부 표현에 사용되는 문자 형식입니다.  
  
```  
typedef Byte extern_type;  
```  
  
### <a name="remarks"></a>설명  
 형식은 템플릿 매개 변수는 동의어 **바이트**합니다.  
  
##  <a name="a-namecodecvtina-codecvtin"></a><a name="codecvt__in"></a>  codecvt:: in  
 시퀀스의 외부 표현을 **바이트**시퀀스의 내부 표현으로 **CharType**s.  
  
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
 멤버 함수를 호출 사이 유지 관리 되는 변환 상태입니다.  
  
 ` first1`  
 변환할 시퀀스의 시작 부분에 대 한 포인터입니다.  
  
 ` last1`  
 변환할 시퀀스의 끝에 대 한 포인터입니다.  
  
 ` next1`  
 변환 된 첫 번째 문자의 시퀀스의 끝을 넘어 포인터입니다.  
  
 ` first2`  
 변환 된 시퀀스의 시작 부분에 대 한 포인터입니다.  
  
 ` last2`  
 변환 된 시퀀스의 끝에 대 한 포인터입니다.  
  
 ` next2`  
 에 대 한 포인터는 **CharType** 마지막 변환 후 제공 되 **Chartype** 대상 시퀀스의 첫 번째 변경 되지 않은 문자입니다.  
  
### <a name="return-value"></a>반환 값  
 성공, 부분적으로 성공 또는 작업의 실패를 나타내는 반환 합니다. 함수를 반환합니다.  
  
- **codecvt_base::error** 소스 시퀀스의 형식이 잘못 경우 형성 합니다.  
  
- `codecvt_base::noconv` 함수 변환을 수행 하지 않습니다 하는 경우.  
  
- **codecvt_base::ok** 변환이 성공 합니다.  
  
- **codecvt_base::partial** 소스 충분 하지 않은 경우 또는 대상이 너무 작아 변환에 성공 하는 경우.  
  
### <a name="remarks"></a>설명  
 `_State` 새 소스 시퀀스의 시작 부분에는 초기 변환 상태가 나타내야 합니다. 함수는 성공적으로 변환의 현재 상태를 반영 하기 위해 필요에 따라 저장된 된 값을 변경 합니다. 일부 변환 후 `_State` 변환을 새 문자 도착할 때 다시 시작을 허용 하도록 설정 해야 합니다.  
  
 멤버 함수는 반환 [do_in](#codecvt__do_in)( `_State`, _ *First1, 이름 성 1 성, next1, First2, _Llast2, next2*).  
  
### <a name="example"></a>예제  
  
```  
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
  
##  <a name="a-namecodecvtinterntypea-codecvtinterntype"></a><a name="codecvt__intern_type"></a>  codecvt:: intern_type  
 내부 표현에 사용되는 문자 형식입니다.  
  
```  
typedef CharType intern_type;  
```  
  
### <a name="remarks"></a>설명  
 형식은 템플릿 매개 변수는 동의어 **CharType**합니다.  
  
##  <a name="a-namecodecvtlengtha-codecvtlength"></a><a name="codecvt__length"></a>  codecvt:: length  
 결정 얼마나 많은 **바이트**의 지정 된 시퀀스를 외부 **바이트**s 이하의 지정된 된 수의 내부 **CharType**s 해당 개수를 반환 하 고 **바이트**s.  
  
```  
int length(
    const StateType& _State,  
    const Byte* first1,   
    const Byte* last1,  
    size_t _Len2) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_State`  
 멤버 함수를 호출 사이 유지 관리 되는 변환 상태입니다.  
  
 ` first1`  
 외부 시퀀스의 시작 부분에 대 한 포인터입니다.  
  
 ` last1`  
 외부 시퀀스의 끝에 대 한 포인터입니다.  
  
 `_Len2`  
 멤버 함수에 의해 반환 될 수 있는 바이트의 최대 수입니다.  
  
### <a name="return-value"></a>반환 값  
 보다 크지 않음 변환의 최대 수의 개수를 나타내는 정수 `_Len2`, 에서 외부 소스 시퀀스에서 정의 된 [ ` first1`, ` last1`).  
  
### <a name="remarks"></a>설명  
 멤버 함수는 반환 [do_length](#codecvt__do_length)( *_State, first1*, ` last1`, `_Len2`).  
  
### <a name="example"></a>예제  
  
```  
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
  
##  <a name="a-namecodecvtmaxlengtha-codecvtmaxlength"></a><a name="codecvt__max_length"></a>  codecvt:: max_length  
 외부의 최대 수를 반환 **바이트**하나의 내부를 만드는 데 필요한 **CharType**합니다.  
  
```  
int max_length() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 최대 **바이트**하나를 만드는 데 필요한 **CharType**합니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 반환 [do_max_length](#codecvt__do_max_length)합니다.  
  
### <a name="example"></a>예제  
  
```  
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
  
##  <a name="a-namecodecvtouta-codecvtout"></a><a name="codecvt__out"></a>  codecvt:: out  
 내부 시퀀스 변환 **CharType**외부의 시퀀스로 **바이트**s.  
  
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
 멤버 함수를 호출 사이 유지 관리 되는 변환 상태입니다.  
  
 ` first1`  
 변환할 시퀀스의 시작 부분에 대 한 포인터입니다.  
  
 ` last1`  
 변환할 시퀀스의 끝에 대 한 포인터입니다.  
  
 ` next1`  
 첫 번째에 대 한 포인터에 대 한 참조 변환 되지 않은 **CharType** 마지막 **CharType** 변환 합니다.  
  
 ` first2`  
 변환 된 시퀀스의 시작 부분에 대 한 포인터입니다.  
  
 ` last2`  
 변환 된 시퀀스의 끝에 대 한 포인터입니다.  
  
 ` next2`  
 첫 번째에 대 한 포인터에 대 한 참조 변환 되지 않은 **바이트** 마지막 변환 후 **바이트**합니다.  
  
### <a name="return-value"></a>반환 값  
 멤버 함수는 반환 [do_out](#codecvt__do_out)( `_State`, ` first1`, ` last1`, ` next1`, ` first2`, ` last2`, ` next2`).  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [codecvt:: do_out](#codecvt__do_out)합니다.  
  
### <a name="example"></a>예제  
  
```  
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
  
##  <a name="a-namecodecvtstatetypea-codecvtstatetype"></a><a name="codecvt__state_type"></a>  codecvt:: state_type  
 내부 및 외부 표현 사이의 변환 중간 상태를 나타내는 데 사용하는 문자 형식입니다.  
  
```  
typedef StateType state_type;  
```  
  
### <a name="remarks"></a>설명  
 형식은 템플릿 매개 변수는 동의어 **StateType**합니다.  
  
##  <a name="a-namecodecvtunshifta-codecvtunshift"></a><a name="codecvt__unshift"></a>  codecvt:: unshift  
 제공 된 **바이트**시퀀스의 마지막 문자를 완료 하기 위해 상태 의존 변환에 필요한 s **바이트**s.  
  
```  
result unshift(
    StateType& _State,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_State`  
 멤버 함수를 호출 사이 유지 관리 되는 변환 상태입니다.  
  
 ` first2`  
 대상 범위에서 첫 번째 위치에 대 한 포인터입니다.  
  
 ` last2`  
 대상 범위에서 마지막 위치에 대 한 포인터입니다.  
  
 ` next2`  
 대상 시퀀스의 첫 번째 변경 되지 않은 요소에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 함수를 반환합니다.  
  
- **codecvt_base::error** 상태가 잘못 된 상태를 나타내는 경우.  
  
- `codecvt_base::noconv` 함수 변환을 수행 하지 않습니다 하는 경우.  
  
- **codecvt_base::ok** 변환이 성공 합니다.  
  
- **codecvt_base::partial** 대상이 너무 작아 변환에 성공 하는 경우.  
  
### <a name="remarks"></a>설명  
 보호 된 가상 멤버 함수는 소스 요소를 변환 하려고 합니다. **CharType**(0) 내에서 저장 하는 대상 시퀀스에 [ ` first2`, ` last2`)를 종료 하는 요소를 제외 하 고 **바이트**(0). 에 항상 저장 ` next2` 대상 시퀀스의 첫 번째 변경 되지 않은 요소에 대 한 포인터입니다.  
  
 `_State` 새 소스 시퀀스의 시작 부분에는 초기 변환 상태가 나타내야 합니다. 함수는 성공적으로 변환의 현재 상태를 반영 하기 위해 필요에 따라 저장된 된 값을 변경 합니다. 일반적으로 소스 요소를 변환 **CharType**(0)는 초기 변환 상태가 현재 상태를 유지 합니다.  
  
 멤버 함수는 반환 [do_unshift](#codecvt__do_unshift)( `_State`, ` first2`, ` last2`, ` next2` ).  
  
## <a name="see-also"></a>참고 항목  
 [\< 로캘>](../standard-library/locale.md)   
 [코드 페이지](../c-runtime-library/code-pages.md)   
 [로캘 이름, 언어 및 국가/지역 문자열](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)

