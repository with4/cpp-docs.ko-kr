---
title: "num_get 클래스 | Microsoft Docs"
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
  - "num_get"
  - "std::num_get"
  - "std.num_get"
  - "xlocnum/std::num_get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "num_get 클래스"
ms.assetid: 9933735d-3918-4b17-abad-5fca2adc62d7
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# num_get 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CharType` 형식의 시퀀스에서 숫자 값으로 변환을 제어하는 로캘 패싯으로 사용 가능한 개체에 대해 설명하는 템플릿 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>  
class num_get : public locale::facet;
```  
  
#### <a name="parameters"></a>매개 변수  
 `CharType`  
 로캘의 문자를 인코딩하기 위해 프로그램 내 사용하는 형식입니다.  
  
 `InputIterator`  
 숫자 get 함수가 입력을 읽어올 반복기의 형식입니다.  
  
## <a name="remarks"></a>설명  
 모든 로캘 패싯과 마찬가지로, 고정 개체 ID에는 초기값 0이 저장되어 있습니다. 에 고유한 양수 값을 저장 하는 저장된 된 값에 액세스 하려고 하는 첫 번째 **id입니다.**  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[num_get](#num_get__num_get)|시퀀스에서 숫자 값을 추출하는 데 사용되는 `num_get` 형식의 개체에 대한 생성자입니다.|  
  
### <a name="typedefs"></a>형식 정의  
  
|||  
|-|-|  
|[char_type](#num_get__char_type)|로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.|  
|[iter_type](#num_get__iter_type)|입력 반복기에 대해 설명하는 형식입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[do_get](#num_get__do_get)|문자 시퀀스에서 숫자 또는 부울 값을 추출하기 위해 호출하는 가상 함수입니다.|  
|[가져오기](#num_get__get)|문자 시퀀스에서 숫자 또는 부울 값을 추출합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \< 로캘>  
  
 **네임스페이스:** std  
  
##  <a name="a-namenumgetchartypea-numgetchartype"></a><a name="num_get__char_type"></a>  num_get:: char_type  
 로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>설명  
 형식은 템플릿 매개 변수는 동의어 **CharType**합니다.  
  
##  <a name="a-namenumgetdogeta-numgetdoget"></a><a name="num_get__do_get"></a>  num_get:: do_get  
 문자 시퀀스에서 숫자 또는 부울 값을 추출하기 위해 호출하는 가상 함수입니다.  
  
```
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long& val) const;virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned short& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned int& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    float& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `first`  
 시작 문자를 읽을 수 있는 범위입니다.  
  
 `last`  
 끝의 문자를 읽을 수 있는 범위입니다.  
  
 `_Iosbase`  
  [ios_base](../standard-library/ios-base-class.md) 인 플래그는 변환에 의해 사용 됩니다.  
  
 `_State`  
 어떤 failbit 상태 (참조 [ios_base:: iostate](../standard-library/ios-base-class.md#ios_base__iostate)) 실패 시 추가 됩니다.  
  
 `val`  
 읽은 값입니다.  
  
### <a name="return-value"></a>반환 값  
 값은 읽은 후 반복기입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 보호 된 가상 멤버 함수  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `long& val`  
  
 `) const;`  
  
 시작 하는 순차 요소와 일치 `first` 시퀀스에서 `[``first``,` `last``)` 전체에서 인식, 될 때까지 비어 있지 않은 정수 필드를 입력 합니다. 경우 성공적으로 변환이 필드는 해당 하는 값 형식으로 `long``,` 에 결과 저장 하 고 `val`합니다. 숫자 입력된 필드의 첫 번째 요소를 지정 하는 반복기를 반환 합니다. 그렇지 않으면 함수가 저장의 경우 nothing `val` 설정 `ios_base::failbit` 에서 `state`합니다. 유효한 정수 입력된 필드의 접두사의 첫 번째 요소를 지정 하는 반복기를 반환 합니다. 두 경우 모두 반환 값이 같은 경우 `last`, 함수 집합 `ios_base::eofbit` 에서 `state`합니다.  
  
 정수 입력된 필드와 일치 하는 일련의 변환 및 검색 함수에서 사용 하는 동일한 규칙으로 변환 됩니다 `char` 파일에서 요소입니다. (이러한 각 `char` 요소 형식의 해당 하는 요소에 매핑됩니다는 `Elem` 으로 단순 하 고, 일대일 매핑.) 해당 하는 검색 변환 사양 다음과 같이 결정 됩니다.  
  
 경우 `iosbase.`[ios_base:: flags](../standard-library/ios-base-class.md#ios_base__flags)`() & ios_base::basefield == ios_base::`[년 10 월](../Topic/%3Cios%3E%20functions.md#oct), 변환 사양은 `lo`합니다.  
  
 경우 `iosbase.flags() & ios_base::basefield == ios_base::`[16 진수](../Topic/%3Cios%3E%20functions.md#hex), 변환 사양은 `lx`합니다.  
  
 경우 `iosbase.flags() & ios_base::basefield == 0`, 변환 사양은 `li`합니다.  
  
 그렇지 않으면 변환 사양은 `ld`합니다.  
  
 정수 입력된 필드의 형식에 따른 추가는 [로캘 패싯](../standard-library/locale-class.md#facet_class)`fac` 호출에서 반환한 [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) `<`[numpunct](../standard-library/numpunct-class.md)`<Elem>(iosbase.` [ios_base:: getloc](../standard-library/ios-base-class.md#ios_base__getloc)`())`합니다. 구체적으로는 다음과 같습니다.  
  
 `fac.` [numpunct:: grouping](../standard-library/numpunct-class.md#numpunct__grouping) `()` 숫자를 소수점의 왼쪽에 그룹화 하는 방법을 결정 합니다.  
  
 `fac.` [numpunct:: thousands_sep](../standard-library/numpunct-class.md#numpunct__thousands_sep) `()` 소수점의 왼쪽에 있는 숫자 그룹을 구분 하는 순서를 결정 합니다.  
  
 인스턴스가 없으면 `fac.thousands_sep()` 그룹화 제한이 적용 되는 숫자 입력된 필드에서 발생 합니다. 모든 그룹화 제약 조건에 따라 적용 되는 그렇지 않은 경우 `fac.grouping()` 권한은 구분 기호는 검색 변환이 발생 하기 전에 제거 됩니다.  
  
 네 번째 보호 된 가상 멤버 함수:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `unsigned long& val`  
  
 `) const;`  
  
 변환 사양을 대체 한다는 점을 제외 하면 첫 번째 동일 하 게 동작 `ld` 와 `lu`합니다. 경우 성공 숫자 입력된 필드를 변환할 형식의 값을 `unsigned long` 에 해당 값을 저장 하 고 `val`합니다.  
  
 다섯 번째 보호 된 가상 멤버 함수:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `long long& val`  
  
 `) const;`  
  
 변환 사양을 대체 한다는 점을 제외 하면 첫 번째 동일 하 게 동작 `ld` 와 `lld`합니다. 경우 성공 숫자 입력된 필드를 변환할 형식의 값을 `long long` 에 해당 값을 저장 하 고 `val`합니다.  
  
 여섯 번째 보호 된 가상 멤버 함수:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `unsigned long long& val`  
  
 `) const;`  
  
 변환 사양을 대체 한다는 점을 제외 하면 첫 번째 동일 하 게 동작 `ld` 와 `llu`합니다. 경우 성공 숫자 입력된 필드를 변환할 형식의 값을 `unsigned long long` 에 해당 값을 저장 하 고 `val`합니다.  
  
 일곱 번째 보호 된 가상 멤버 함수:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `float& val`  
  
 `) const;`  
  
 완전 하 고 비어 있지 않은 부동 소수점 입력된 필드와 일치 하도록 노력 한다는 점을 제외 하면 첫 번째 동일 하 게 동작 합니다. `fac.`[numpunct:: decimal_point](../standard-library/numpunct-class.md#numpunct__decimal_point)`()` 소수 자릿수의 정수 부분을 구분 하는 시퀀스를 결정 합니다. 해당 하는 검색 변환 지정자는 `lf`합니다.  
  
 여덟 번째 보호 된 가상 멤버 함수:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `double& val`  
  
 `) const;`  
  
 완전 하 고 비어 있지 않은 부동 소수점 입력된 필드와 일치 하도록 노력 한다는 점을 제외 하면 첫 번째 동일 하 게 동작 합니다. `fac.`[numpunct:: decimal_point](../standard-library/numpunct-class.md#numpunct__decimal_point)`()` 소수 자릿수의 정수 부분을 구분 하는 시퀀스를 결정 합니다. 해당 하는 검색 변환 지정자는 `lf`합니다.  
  
 아홉 번째 보호 된 가상 멤버 함수:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `long double& val`  
  
 `) const;`  
  
 점을 제외 하 고 해당 하는 검색 변환 지정자는 여덟 번째 동일 하 게 동작 `Lf`합니다.  
  
 아홉 번째 보호 된 가상 멤버 함수:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `void *& val`  
  
 `) const;`  
  
 해당 하는 검색 변환 지정자가 제외 하 고 첫 번째 동일 하 게 작동 `p`합니다.  
  
 마지막 가상 (열 한 번째) 보호 된 멤버 함수:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `bool& val`  
  
 `) const;`  
  
 완전 하 고 비어 있지 않은 부울 입력된 필드와 일치 하도록 노력 한다는 점을 제외 하면 첫 번째 동일 하 게 동작 합니다. 경우 성공적으로 부울 입력된 필드를 변환할 형식의 값을 `bool` 에 해당 값을 저장 하 고 `val`합니다.  
  
 부울 입력된 필드는 두 가지 형태 중 하나를 사용 합니다. 경우 `iosbase.flags() & ios_base::`[boolalpha](../Topic/%3Cios%3E%20functions.md#boolalpha) 가 false 인 것 같습니다 정수 입력된 필드는 변환 된 값은 0 (false) 또는 1 (true) 중 하나 여야 합니다. 그렇지 않으면 시퀀스 중 하 나와 일치 해야 `fac.`[numpunct:: falsename](../standard-library/numpunct-class.md#numpunct__falsename)`()` (false)에 대 한 또는 `fac.`[numpunct:: truename](../standard-library/numpunct-class.md#numpunct__truename)`()` (true) 용입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [가져오기](#num_get__get), 에서 가상 멤버 함수를 호출 하는 경우, `do_get`합니다.  
  
##  <a name="a-namenumgetgeta-numgetget"></a><a name="num_get__get"></a>  num_get:: get  
 문자 시퀀스에서 숫자 또는 부울 값을 추출합니다.  
  
```
iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned short& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned int& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    float& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `first`  
 시작 문자를 읽을 수 있는 범위입니다.  
  
 `last`  
 끝의 문자를 읽을 수 있는 범위입니다.  
  
 `_Iosbase`  
  [ios_base](../standard-library/ios-base-class.md) 인 플래그는 변환에 의해 사용 됩니다.  
  
 `_State`  
 어떤 failbit 상태 (참조 [ios_base:: iostate](../standard-library/ios-base-class.md#ios_base__iostate)) 실패 시 추가 됩니다.  
  
 `val`  
 읽은 값입니다.  
  
### <a name="return-value"></a>반환 값  
 값은 읽은 후 반복기입니다.  
  
### <a name="remarks"></a>설명  
 모든 멤버 함수 반환 [do_get](#num_get__do_get)( `first`, `last`, `_Iosbase`, `_State`, `val`).  
  
 첫 번째 보호 된 가상 멤버 함수는 시퀀스에서 처음에 시작 되는 순차 요소를 일치 시 키 려 [ `first`, `last`) 전체에서 인식, 될 때까지 비어 있지 않은 정수 필드를 입력 합니다. 경우 성공적으로 변환이 필드는 해당 하는 값 형식으로 **긴** 에 결과 저장 하 고 `val`합니다. 숫자 입력된 필드의 첫 번째 요소를 지정 하는 반복기를 반환 합니다. 그렇지 않으면 함수가 저장의 경우 nothing `val` 설정 `ios_base::failbit` _에 *상태*합니다. 유효한 정수 입력된 필드의 접두사의 첫 번째 요소를 지정 하는 반복기를 반환 합니다. 두 경우 모두 반환 값이 같은 경우 **마지막**, 함수 집합 `ios_base::eofbit` 에서 `_State`합니다.  
  
 정수 입력된 필드와 일치 하는 일련의 변환 및 검색 함수에서 사용 하는 동일한 규칙으로 변환 됩니다 `char` 파일에서 요소입니다. 이러한 각 `char` 요소 형식의 해당 하는 요소에 매핑됩니다는 **CharType** 간단 하 고 일대일 매핑이 있습니다. 해당 하는 검색 변환 사양 다음과 같이 결정 됩니다.  
  
-   경우 **iosbase**합니다. [플래그](../standard-library/ios-base-class.md#ios_base__flags) & `ios_base::basefield` == `ios_base::`[년 10 월](../Topic/%3Cios%3E%20functions.md#oct), 변환 사양은 **lo**합니다.  
  
-   경우 **iosbase.flags** & **ios_base::basefield** == `ios_base::`[16 진수](../Topic/%3Cios%3E%20functions.md#hex), 변환 사양은 **lx**합니다.  
  
-   경우 **iosbase.flags** & **ios_base::basefield** = = 0의 변환 사양은 `li`합니다.  
  
-   그렇지 않으면 변환 사양은 **ld**합니다.  
  
 정수 입력된 필드의 형식에 따른 추가는 [로캘 패싯](../standard-library/locale-class.md#facet_class)**fac** 호출에서 반환한 [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [numpunct](../standard-library/numpunct-class.md)\< **Elem**> ( **iosbase**합니다. [getloc](../standard-library/ios-base-class.md#ios_base__getloc)). 구체적으로는 다음과 같습니다.  
  
- **fac**합니다. [그룹화](../standard-library/numpunct-class.md#numpunct__grouping) 숫자를 소수점의 왼쪽에 그룹화 하는 방법을 결정 합니다.  
  
- **fac**합니다. [thousands_sep](../standard-library/numpunct-class.md#numpunct__thousands_sep) 구분 소수점의 왼쪽에는 시퀀스를 결정 합니다.  
  
 인스턴스가 없으면 **fac**합니다. `thousands_sep` 그룹화 제한이 적용 되어, 숫자 입력된 필드에 발생 합니다. 모든 그룹화 제약 조건에 따른 그렇지 **fac**합니다. **그룹화** 적용 되는지와 구분 기호는 검색 변환이 발생 하기 전에 제거 됩니다.  
  
 두 번째 보호 된 가상 멤버 함수:  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;
```  
  
 변환 사양을 대체 한다는 점을 제외 하면 첫 번째 동일 하 게 동작 **ld** 와 **lu**합니다. 경우 성공 숫자 입력된 필드를 변환할 형식의 값을 `unsigned long` 에 해당 값을 저장 하 고 `val`합니다.  
  
 세 번째 보호 된 가상 멤버 함수:  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;
```  
  
 완전 하 고 비어 있지 않은 부동 소수점 입력된 필드와 일치 하도록 시도 한다는 점을 제외 하면 첫 번째 동일 하 게 동작 합니다. **fac**합니다. [decimal_point](../standard-library/numpunct-class.md#numpunct__decimal_point) 소수 자릿수의 정수 부분을 구분 하는 시퀀스를 결정 합니다. 해당 하는 검색 변환 지정자는 **lf**합니다.  
  
 네 번째 보호 된 가상 멤버 함수:  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;
```  
  
 동일 하 게 작동 세 번째, 점을 제외 하 고 해당 하는 검색 변환 지정자 **Lf**합니다.  
  
 다섯 번째 보호 된 가상 멤버 함수:  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```  
  
 해당 하는 검색 변환 지정자가 제외 하 고 첫 번째 동일 하 게 작동 **p**합니다.  
  
 여섯 번째 보호 된 가상 멤버 함수:  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```  
  
 완전 하 고 비어 있지 않은 부울 입력된 필드와 일치 하도록 시도 한다는 점을 제외 하면 첫 번째 동일 하 게 동작 합니다. 경우 성공적으로 부울 입력된 필드를 변환할 형식의 값을 `bool` 에 해당 값을 저장 하 고 `val`합니다.  
  
 부울 입력된 필드는 두 가지 형태 중 하나를 사용 합니다. 경우 **iosbase**합니다. **플래그** & `ios_base::`[boolalpha](../Topic/%3Cios%3E%20functions.md#boolalpha) 는 **false**, 이 정수 입력된 필드와 동일 하 게 제외 하 고 변환 된 값에는 0 이어야 합니다 (에 대 한 **false**) 또는 1 (에 대 한 **true**). 그렇지 않으면 시퀀스 중 하 나와 일치 해야 **fac**합니다. [falsename](../standard-library/numpunct-class.md#numpunct__falsename) (에 대 한 **false**), 또는 **fac**합니다. [truename](../standard-library/numpunct-class.md#numpunct__truename) (에 대 한 **true**).  
  
### <a name="example"></a>예제  
  
```  
// num_get_get.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   basic_stringstream<char> psz, psz2;  
   psz << "-1000,56";  
  
   ios_base::iostate st = 0;  
   long double fVal;  
   cout << use_facet <numpunct <char> >(loc).thousands_sep( ) << endl;  
  
   psz.imbue( loc );  
   use_facet <num_get <char> >  
   (loc).get( basic_istream<char>::_Iter( psz.rdbuf( ) ),  
           basic_istream<char>::_Iter(0), psz, st, fVal );  
  
   if ( st & ios_base::failbit )  
      cout << "money_get( ) FAILED" << endl;  
   else  
      cout << "money_get( ) = " << fVal << endl;  
}  
```  
  
##  <a name="a-namenumgetitertypea-numgetitertype"></a><a name="num_get__iter_type"></a>  num_get:: iter_type  
 입력 반복기에 대해 설명하는 형식입니다.  
  
```
typedef InputIterator iter_type;
```  
  
### <a name="remarks"></a>설명  
 형식은 템플릿 매개 변수는 동의어 **InputIterator**합니다.  
  
##  <a name="a-namenumgetnumgeta-numgetnumget"></a><a name="num_get__num_get"></a>  num_get:: num_get  
 시퀀스에서 숫자 값을 추출하는 데 사용되는 `num_get` 형식의 개체에 대한 생성자입니다.  
  
```
explicit num_get(size_t _Refs = 0);
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
  
## <a name="see-also"></a>참고 항목  
 [\< 로캘>](../standard-library/locale.md)   
 [facet 클래스](../standard-library/locale-class.md#facet_class)   
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)



