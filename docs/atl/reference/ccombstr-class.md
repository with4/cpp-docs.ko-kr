---
title: CComBSTR 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComBSTR
- ATLBASE/ATL::CComBSTR
- ATLBASE/ATL::CComBSTR::CComBSTR
- ATLBASE/ATL::CComBSTR::Append
- ATLBASE/ATL::CComBSTR::AppendBSTR
- ATLBASE/ATL::CComBSTR::AppendBytes
- ATLBASE/ATL::CComBSTR::ArrayToBSTR
- ATLBASE/ATL::CComBSTR::AssignBSTR
- ATLBASE/ATL::CComBSTR::Attach
- ATLBASE/ATL::CComBSTR::BSTRToArray
- ATLBASE/ATL::CComBSTR::ByteLength
- ATLBASE/ATL::CComBSTR::Copy
- ATLBASE/ATL::CComBSTR::CopyTo
- ATLBASE/ATL::CComBSTR::Detach
- ATLBASE/ATL::CComBSTR::Empty
- ATLBASE/ATL::CComBSTR::Length
- ATLBASE/ATL::CComBSTR::LoadString
- ATLBASE/ATL::CComBSTR::ReadFromStream
- ATLBASE/ATL::CComBSTR::ToLower
- ATLBASE/ATL::CComBSTR::ToUpper
- ATLBASE/ATL::CComBSTR::WriteToStream
- ATLBASE/ATL::CComBSTR::m_str
dev_langs:
- C++
helpviewer_keywords:
- BSTRs, wrapper
- CComBSTR class
- CComBSTR
ms.assetid: 8fea1879-a05e-47a5-a803-8dec60eaa534
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a9130dec2de7d22cfec8a76cdeb31e11388a205
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ccombstr-class"></a>CComBSTR 클래스
이 클래스에 대 한 래퍼는 `BSTR`s입니다.  
  
## <a name="syntax"></a>구문  
  
```
class CComBSTR
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComBSTR::CComBSTR](#ccombstr)|생성자입니다.|  
|[CComBSTR:: ~ CComBSTR](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComBSTR::Append](#append)|문자열을 추가 `m_str`합니다.|  
|[CComBSTR::AppendBSTR](#appendbstr)|추가 `BSTR` 를 `m_str`합니다.|  
|[CComBSTR::AppendBytes](#appendbytes)|지정 된 바이트 수를 추가 `m_str`합니다.|  
|[CComBSTR::ArrayToBSTR](#arraytobstr)|만듭니다는 `BSTR` safearray에 있는 각 요소의 첫 번째 문자에 연결 된 `CComBSTR` 개체입니다.|  
|[CComBSTR::AssignBSTR](#assignbstr)|할당 한 `BSTR` 를 `m_str`합니다.|  
|[CComBSTR::Attach](#attach)|연결 된 `BSTR` 에 `CComBSTR` 개체입니다.|  
|[CComBSTR::BSTRToArray](#bstrtoarray)|여기서는 배열의 각 요소는 문자를 0부터 시작 1 차원 safearray 만듭니다는 `CComBSTR` 개체입니다.|  
|[CComBSTR::ByteLength](#bytelength)|길이 반환 `m_str` (바이트)에서입니다.|  
|[CComBSTR::Copy](#copy)|복사본을 반환 `m_str`합니다.|  
|[CComBSTR::CopyTo](#copyto)|복사본을 반환 `m_str` 통해는 **[out]** 매개 변수|  
|[CComBSTR::Detach](#detach)|분리 `m_str` 에서 `CComBSTR` 개체입니다.|  
|[CComBSTR::Empty](#empty)|해제 `m_str`합니다.|  
|[CComBSTR::Length](#length)|길이 반환 `m_str`합니다.|  
|[CComBSTR::LoadString](#loadstring)|문자열 리소스를 로드합니다.|  
|[CComBSTR::ReadFromStream](#readfromstream)|로드 한 `BSTR` 스트림에서 개체입니다.|  
|[CComBSTR::ToLower](#tolower)|문자열을 소문자로 변환합니다.|  
|[CComBSTR::ToUpper](#toupper)|문자열을 대문자로 변환합니다.|  
|[CComBSTR::WriteToStream](#writetostream)|저장 `m_str` 스트림으로 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[BSTR CComBSTR::operator](#operator_bstr)|캐스트는 `CComBSTR` 개체는 `BSTR`합니다.|  
|[CComBSTR::operator!](#operator_not)|반환 `true` 또는 `false`인지 여부에 따라 `m_str`은 `NULL`합니다.|  
|[CComBSTR::operator! =](#operator_neq)|비교는 `CComBSTR` 문자열로 합니다.|  
|[CComBSTR::operator &](#operator_amp)|주소를 반환 `m_str`합니다.|  
|[CComBSTR::operator + =](#operator_add_eq)|추가 `CComBSTR` 개체입니다.|  
|[CComBSTR::operator <](#operator_lt)|비교는 `CComBSTR` 문자열로 합니다.|  
|[CComBSTR::operator =](#operator_eq)|에 값을 할당 `m_str`합니다.|  
|[CComBSTR::operator = =](#operator_eq_eq)|비교는 `CComBSTR` 문자열로 합니다.|  
|[CComBSTR::operator >](#operator_gt)|비교는 `CComBSTR` 문자열로 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CComBSTR::m_str](#m_str)|포함 된 `BSTR` 와 관련 된는 `CComBSTR` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 `CComBSTR` 클래스에 대 한 래퍼는 `BSTR`s는 문자열 길이 접두사가 있는 합니다. 길이 정수 데이터 앞에 문자열의 메모리 위치에 저장 됩니다.  
  
 A [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) 은 null로 끝나는 마지막 문자 계산 되었지만 문자열 내에 포함 된 null 문자가 포함 될 수도 있습니다. 문자열 길이 문자 수를 첫 번째 null 문자에 따라 결정 됩니다.  
  
> [!NOTE]
>  `CComBSTR` 클래스는 다양 한 ANSI 또는 유니코드 문자열을 인수로 사용 하는 멤버 (생성자, 대입 연산자 및 비교 연산자)를 제공 합니다. 이러한 함수의 ANSI 버전은 임시 유니코드 문자열은 내부적으로 생성 되기도 하기 때문에 해당 하는 유니코드 함수와 보다 효율성이 떨어집니다. 효율성을 높이기 위해 가능한 경우 유니코드 버전을 사용 합니다.  
  
> [!NOTE]
>  Visual Studio.NET에서 구현 된 향상 된 조회 동작으로 인해 코드와 같은 `bstr = L"String2" + bstr;`, 이전 릴리스에서 컴파일한 수를 대신 구현 해야 `bstr = CStringW(L"String2") + bstr`합니다.  
  
 사용 시 주의 사항 목록은 `CComBSTR`, 참조 [CComBSTR을 사용한 프로그래밍](../../atl/programming-with-ccombstr-atl.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="append"></a>  CComBSTR::Append  
 추가 하거나 `lpsz` 또는 `BSTR` 소속 `bstrSrc` 를 [m_str](#m_str)합니다.  
  
```
HRESULT Append(const CComBSTR& bstrSrc) throw();
HRESULT Append(wchar_t ch) throw();
HRESULT Append(char ch) throw();
HRESULT Append(LPCOLESTR lpsz) throw();
HRESULT Append(LPCSTR lpsz) throw();
HRESULT Append(LPCOLESTR lpsz, int nLen) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `bstrSrc`  
 [in] A `CComBSTR` 추가할 개체입니다.  
  
 *ch*  
 [in] 추가할 문자입니다.  
  
 `lpsz`  
 [in] 0으로 끝나는 문자 추가할 문자열입니다. 통해 유니코드 문자열을 전달 하는 **LPCOLESTR** 오버 로드 또는 ANSI 문자열을 통해는 `LPCSTR` 버전입니다.  
  
 `nLen`  
 [in] 문자 수가 `lpsz` 추가할 합니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK` 성공 또는 표준에서 `HRESULT` 오류 값입니다.  
  
### <a name="remarks"></a>설명  
 추가할 하기 전에 ANSI 문자열이 유니코드로 변환 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities#32](../../atl/codesnippet/cpp/ccombstr-class_1.cpp)]  
  
##  <a name="appendbstr"></a>  CComBSTR::AppendBSTR  
 지정 된 추가 `BSTR` 를 [m_str](#m_str)합니다.  
  
```
HRESULT AppendBSTR(BSTR p) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 [in] A `BSTR` 추가할 합니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK` 성공 또는 표준에서 `HRESULT` 오류 값입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드에 일반적인 와이드 문자 문자열을 전달 하지 마십시오. 컴파일러 오류를 catch 하 고 런타임 오류가 발생할 수 없습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities#33](../../atl/codesnippet/cpp/ccombstr-class_2.cpp)]  
  
##  <a name="appendbytes"></a>  CComBSTR::AppendBytes  
 지정 된 바이트 수가 추가 [m_str](#m_str) 변환 하지 않고 있습니다.  
  
```
HRESULT AppendBytes(const char* lpsz, int nLen) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpsz`  
 [in] 추가할 바이트 배열에 대 한 포인터입니다.  
  
 `p`  
 [in] 추가 하는 바이트 수입니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK` 성공 또는 표준에서 `HRESULT` 오류 값입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities#34](../../atl/codesnippet/cpp/ccombstr-class_3.cpp)]  
  
##  <a name="arraytobstr"></a>  CComBSTR::ArrayToBSTR  
 기존 문자열에 저장을 해제는 `CComBSTR` 개체를 다음 만듭니다는 `BSTR` safearray에 있는 각 요소의 첫 번째 문자에 연결 하 고는 `CComBSTR` 개체입니다.  
  
```
HRESULT ArrayToBSTR(const SAFEARRAY* pSrc) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pSrc`  
 [in] 문자열을 만드는 사용 되는 요소를 포함 하는 safearray 합니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK` 성공 또는 표준에서 `HRESULT` 오류 값입니다.  
  
##  <a name="assignbstr"></a>  CComBSTR::AssignBSTR  
 할당 한 `BSTR` 를 [m_str](#m_str)합니다.  
  
```
HRESULT AssignBSTR(const BSTR bstrSrc) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `bstrSrc`  
 [in] A `BSTR` 현재에 할당할 `CComBSTR` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK` 성공 또는 표준에서 `HRESULT` 오류 값입니다.  
  
##  <a name="attach"></a>  CComBSTR::Attach  
 연결 된 `BSTR` 에 `CComBSTR` 설정 하 여 개체는 [m_str](#m_str) 멤버를 *src*합니다.  
  
```
void Attach(BSTR src) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *src*  
 [in] `BSTR` 개체에 연결 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드에 일반적인 와이드 문자 문자열을 전달 하지 마십시오. 컴파일러 오류를 catch 하 고 런타임 오류가 발생할 수 없습니다.  
  
> [!NOTE]
>  이 메서드는 경우 어설션 `m_str` 이 아닌 **NULL**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]  
  
##  <a name="bstrtoarray"></a>  CComBSTR::BSTRToArray  
 여기서는 배열의 각 요소는 문자를 0부터 시작 1 차원 safearray 만듭니다는 `CComBSTR` 개체입니다.  
  
```
HRESULT BSTRToArray(LPSAFEARRAY* ppArray) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `ppArray`  
 [out] 함수의 결과 저장 하는 데 사용 safearray 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK` 성공 또는 표준에서 `HRESULT` 오류 값입니다.  
  
##  <a name="bytelength"></a>  CComBSTR::ByteLength  
 바이트 수를 반환 `m_str`, null 종결 문자를 제외 합니다.  
  
```
unsigned int ByteLength() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 길이 [m_str](#m_str) 멤버 (바이트)에서입니다.  
  
### <a name="remarks"></a>설명  
 0을 반환 `m_str` 은 **NULL**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities#36](../../atl/codesnippet/cpp/ccombstr-class_5.cpp)]  
  
##  <a name="ccombstr"></a>  CComBSTR::CComBSTR  
 생성자입니다. 기본 생성자 집합은 [m_str](#m_str) 멤버 **NULL**합니다.  
  
```
CComBSTR() throw();
CComBSTR(const CComBSTR& src);  
CComBSTR(REFGUID  guid);  
CComBSTR(int nSize);  
CComBSTR(int nSize, LPCOLESTR sz);  
CComBSTR(int nSize, LPCSTR sz);  
CComBSTR(LPCOLESTR pSrc);  
CComBSTR(LPCSTR pSrc);  
CComBSTR(CComBSTR&& src) throw(); // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>매개 변수  
 `nSize`  
 [in] `sz`에서 복사할 문자 수 또는 `CComBSTR`에 대한 문자의 초기 크기입니다.  
  
 `sz`  
 [in] 복사할 문자열입니다. 유니코드 버전 지정는 **LPCOLESTR**; ANSI 버전 지정는 `LPCSTR`합니다.  
  
 `pSrc`  
 [in] 복사할 문자열입니다. 유니코드 버전 지정는 **LPCOLESTR**; ANSI 버전 지정는 `LPCSTR`합니다.  
  
 *src*  
 [in] `CComBSTR` 개체입니다.  
  
 `guid`  
 [in] 에 대 한 참조는 **GUID** 구조입니다.  
  
### <a name="remarks"></a>설명  
 복사 생성자 집합 `m_str` 의 복사본에는 `BSTR` 소속 *src*합니다. **REFGUID** 변환 생성자는 **GUID** 사용 하 여 문자열을 **StringFromGUID2** 고 결과 저장 합니다.  
  
 다른 생성자는 `m_str`을 지정된 문자열의 복사본으로 설정합니다. `nSize`에 대한 값을 전달하면 `nSize` 문자만 복사되고 그 뒤에 null 종결 문자가 옵니다.  
  
 `CComBSTR`은 이동 의미 체계를 지원합니다. 이동 생성자를 사용할 수 있습니다 (rvalue 참조를 사용 하는 생성자 ( `&&`) 개체를 복사 하는 오버 헤드 없이 인수로 전달한 이전 개체와 동일한 기본 데이터를 사용 하는 새 개체를 만듭니다.  
  
 소멸자는 `m_str`에서 가리키는 문자열을 해제합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities#37](../../atl/codesnippet/cpp/ccombstr-class_6.cpp)]  
  
##  <a name="dtor"></a>  CComBSTR:: ~ CComBSTR  
 소멸자입니다.  
  
```
~CComBSTR();
```  
  
### <a name="remarks"></a>설명  
 소멸자는 `m_str`에서 가리키는 문자열을 해제합니다.  
  
##  <a name="copy"></a>  CComBSTR::Copy  
 할당의 복사본을 반환 하 고 `m_str`합니다.  
  
```
BSTR Copy() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 복사본은 [m_str](#m_str) 멤버입니다. 경우 `m_str` 은 **NULL**, 반환 **NULL**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities#38](../../atl/codesnippet/cpp/ccombstr-class_7.cpp)]  
  
##  <a name="copyto"></a>  CComBSTR::CopyTo  
 할당의 복사본을 반환 하 고 [m_str](#m_str) 는 매개 변수를 통해 합니다.  
  
```
HRESULT CopyTo(BSTR* pbstr) throw();

HRESULT CopyTo(VARIANT* pvarDest) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *pbstr*  
 [out] 주소는 `BSTR` 를이 메서드에 의해 할당 된 문자열을 반환 합니다.  
  
 `pvarDest`  
 [out] 주소는 **VARIANT** 를이 메서드에 의해 할당 된 문자열을 반환 합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 복사본의 성공 여부를 나타내는 값입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 호출한 후의 **VARIANT** 가리키는 `pvarDest` 유형 중 하나가 됩니다 `VT_BSTR`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities#39](../../atl/codesnippet/cpp/ccombstr-class_8.cpp)]  
  
##  <a name="detach"></a>  CComBSTR::Detach  
 분리 [m_str](#m_str) 에서 `CComBSTR` 개체 및 집합 `m_str` 를 **NULL**합니다.  
  
```
BSTR Detach() throw();
```  
  
### <a name="return-value"></a>반환 값  
 `BSTR` 연관 된 `CComBSTR` 개체입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities#40](../../atl/codesnippet/cpp/ccombstr-class_9.cpp)]  
  
##  <a name="empty"></a>  CComBSTR::Empty  
 해제 된 [m_str](#m_str) 멤버입니다.  
  
```
void Empty() throw();
```  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities#41](../../atl/codesnippet/cpp/ccombstr-class_10.cpp)]  
  
##  <a name="length"></a>  CComBSTR::Length  
 에 있는 문자의 수를 반환 `m_str`, null 종결 문자를 제외 합니다.  
  
```
unsigned int Length() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 길이 [m_str](#m_str) 멤버입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities#42](../../atl/codesnippet/cpp/ccombstr-class_11.cpp)]  
  
##  <a name="loadstring"></a>  CComBSTR::LoadString  
 로 지정 된 문자열 리소스 로드 `nID` 이 개체에 저장 합니다.  
  
```
bool LoadString(HINSTANCE hInst, UINT nID) throw();
bool LoadString(UINT nID) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 참조 [LoadString](http://msdn.microsoft.com/library/windows/desktop/ms647486) in the Windows SDK입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 문자열이 성공적으로 고, 그렇지 않으면 로드 된 경우 반환 **false**합니다.  
  
### <a name="remarks"></a>설명  
 통해 사용자에 의해 식별 된 모듈에서 리소스를 로드 하는 첫 번째 함수는 `hInst` 매개 변수입니다. 와 연결 된 리소스 모듈에서 리소스를 로드 하는 두 번째 함수는 [CComModule](../../atl/reference/ccommodule-class.md)-이 프로젝트에 사용 되는 개체를 파생 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities#43](../../atl/codesnippet/cpp/ccombstr-class_12.cpp)]  
  
##  <a name="m_str"></a>  CComBSTR::m_str  
 포함 된 `BSTR` 와 관련 된는 `CComBSTR` 개체입니다.  
  
```
BSTR m_str;
```  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities#49](../../atl/codesnippet/cpp/ccombstr-class_13.cpp)]  
  
##  <a name="operator_bstr"></a>  BSTR CComBSTR::operator  
 캐스트는 `CComBSTR` 개체는 `BSTR`합니다.  
  
```  
operator BSTR() const throw();
```  
  
### <a name="remarks"></a>설명  
 전달할 수 있도록 `CComBSTR` 가 있는 함수 개체 **[in] BSTR** 매개 변수입니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CComBSTR::m_str](#m_str)합니다.  
  
##  <a name="operator_not"></a>  CComBSTR::operator!  
 확인 여부 `BSTR` 문자열은 NULL입니다.  
  
```
bool operator!() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 경우는 [m_str](#m_str) 멤버는 **NULL**, 그렇지 않으면 **false**합니다.  
  
### <a name="remarks"></a>설명  
 이 연산자는 빈 문자열에 대해 NULL 값만 확인합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]  
  
##  <a name="operator_neq"></a>  CComBSTR::operator! =  
 논리적 반대를 반환 [연산자 = =](#operator_eq_eq)합니다.  
  
```
bool operator!= (const CComBSTR& bstrSrc) const throw();
bool operator!= (LPCOLESTR pszSrc) const;
bool operator!= (LPCSTR pszSrc) const;
bool operator!= (int nNull) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `bstrSrc`  
 [in] `CComBSTR` 개체입니다.  
  
 `pszSrc`  
 [in] 0으로 끝나는 문자열입니다.  
  
 `nNull`  
 [in] 해야 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 비교 되는 항목에 같은지는 `CComBSTR` 개체; 그렇지 않으면 반환 **false**합니다.  
  
### <a name="remarks"></a>설명  
 `CComBSTR`s는 사용자의 기본 로캘이의 컨텍스트에서 함수와 비교 됩니다. 최종 비교 연산자에 대해 포함 된 문자열을 비교 방금 **NULL**합니다.  
  
##  <a name="operator_amp"></a>  CComBSTR::operator &amp;  
 주소를 반환 하는 `BSTR` 에 저장 된는 [m_str](#m_str) 멤버입니다.  
  
```
BSTR* operator&() throw();
```  
  
### <a name="remarks"></a>설명  
 `CComBstr operator &` 에 특수 한 어설션을 하기 위해 연결 된 메모리 누수를 식별 합니다. 프로그램은 어설션 시기는 `m_str` 멤버가 초기화 됩니다. 이 어설션이 생성 프로그래머가 사용 하는 상황을 파악 하는 `& operator` 새 값을 할당할 `m_str` 멤버의 첫 번째 할당 해제 되지 않은 상태로 `m_str`합니다. 경우 `m_str` NULL 이면 프로그램 해당 m_str 아직 할당 되지 않은 것으로 가정 합니다. 이 경우 프로그램 어설션 하지 않습니다.  
  
 이 어설션이 기본적으로 사용 되지 않습니다. 정의 `ATL_CCOMBSTR_ADDRESS_OF_ASSERT` 이 어설션은 사용할 수 있도록 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities#46](../../atl/codesnippet/cpp/ccombstr-class_14.cpp)]  
  
 [!code-cpp[NVC_ATL_Utilities#47](../../atl/codesnippet/cpp/ccombstr-class_15.cpp)]  
  
##  <a name="operator_add_eq"></a>  CComBSTR::operator + =  
 문자열을 추가 하 고 `CComBSTR` 개체입니다.  
  
```
CComBSTR& operator+= (const CComBSTR& bstrSrc);  
CComBSTR& operator+= (const LPCOLESTR pszSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 `bstrSrc`  
 [in] A `CComBSTR` 추가할 개체입니다.  
  
 `pszSrc`  
 [in] 0으로 끝나는 추가할 문자열입니다.  
  
### <a name="remarks"></a>설명  
 `CComBSTR`s는 사용자의 기본 로캘이의 컨텍스트에서 함수와 비교 됩니다. **LPCOLESTR** 비교가 수행 사용 하 여 `memcmp` 각 문자열의 원시 데이터에 있습니다. `LPCSTR` 비교 수행 하는 동일한 방식으로 임시 유니코드의 복사 되 면 `pszSrc` 만들어졌습니다. 최종 비교 연산자에 대해 포함 된 문자열을 비교 방금 **NULL**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities#48](../../atl/codesnippet/cpp/ccombstr-class_16.cpp)]  
  
##  <a name="operator_lt"></a>  CComBSTR::operator &lt;  
 비교는 `CComBSTR` 문자열로 합니다.  
  
```
bool operator<(const CComBSTR& bstrSrc) const throw();
bool operator<(LPCOLESTR pszSrc) const throw();
bool operator<(LPCSTR pszSrc) const throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 비교 하 고 항목을 보다 작은 `CComBSTR` 개체; 그렇지 않으면 반환 **false**합니다.  
  
### <a name="remarks"></a>설명  
 사용자의 기본 로캘을 사용 하 여 비교 합니다.  
  
##  <a name="operator_eq"></a>  CComBSTR::operator =  
 설정의 [m_str](#m_str) 멤버의 복사본을 `pSrc` 또는의 복사본에는 `BSTR` 소속 *src*합니다. 이동 할당 연산자 이동 `src` 복사 하지 않고 있습니다.   
  
```
CComBSTR& operator= (const CComBSTR& src);  
CComBSTR& operator= (LPCOLESTR pSrc);  
CComBSTR& operator= (LPCSTR pSrc);
CComBSTR& operator= (CComBSTR&& src) throw(); // (Visual Studio 2017)
```  
  
### <a name="remarks"></a>설명  
 `pSrc` 매개 변수를 지정 하거나 한 **LPCOLESTR** 유니코드 버전에 대 한 또는 `LPCSTR` ANSI 버전에 대 한 합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CComBSTR::Copy](#copy)합니다.  
  
##  <a name="operator_eq_eq"></a>  CComBSTR::operator = =  
 비교는 `CComBSTR` 문자열로 합니다. `CComBSTR`s는 사용자의 기본 로캘이의 컨텍스트에서 함수와 비교 됩니다.  
  
```
bool operator== (const CComBSTR& bstrSrc) const throw();
bool operator== (LPCOLESTR pszSrc) const;
bool operator== (LPCSTR pszSrc) const;
bool operator== (int nNull) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `bstrSrc`  
 [in] `CComBSTR` 개체입니다.  
  
 `pszSrc`  
 [in] 0으로 끝나는 문자열입니다.  
  
 `nNull`  
 [in] 해야 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 비교 되는 항목에 같은지는 `CComBSTR` 개체; 그렇지 않으면 반환 **false**합니다.  
  
### <a name="remarks"></a>설명  
 최종 비교 연산자에 대해 포함 된 문자열을 비교 방금 **NULL**합니다.  
  
##  <a name="operator_gt"></a>  CComBSTR::operator &gt;  
 비교는 `CComBSTR` 문자열로 합니다.  
  
```
bool operator>(const CComBSTR& bstrSrc) const throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 비교 되는 항목 보다 큰 경우는 `CComBSTR` 개체; 그렇지 않으면 반환 **false**합니다.  
  
### <a name="remarks"></a>설명  
 사용자의 기본 로캘을 사용 하 여 비교 합니다.  
  
##  <a name="readfromstream"></a>  CComBSTR::ReadFromStream  
 설정은 [m_str](#m_str) 멤버는 `BSTR` 에 지정된 된 스트림을 포함 합니다.  
  
```
HRESULT ReadFromStream(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pStream`  
 [in] 에 대 한 포인터는 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) 인터페이스에서 데이터를 포함 하는 스트림입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 **ReadToStream** 필요를 호출 하 여 기록 데이터 형식을 호환 가능 하도록 현재 위치의 스트림의 내용을 [WriteToStream](#writetostream)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities#44](../../atl/codesnippet/cpp/ccombstr-class_17.cpp)]  
  
##  <a name="tolower"></a>  CComBSTR::ToLower  
 포함 된 문자열을 소문자로 변환합니다.  
  
```
HRESULT ToLower() throw();
```  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 참조 **CharLowerBuff** 변환이 수행 하는 방법에 대 한 자세한 내용은 합니다.  
  
##  <a name="toupper"></a>  CComBSTR::ToUpper  
 포함 된 문자열을 대문자로 변환합니다.  
  
```
HRESULT ToUpper() throw();
```  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 참조 **CharUpperBuff** 변환이 수행 하는 방법에 대 한 자세한 내용은 합니다.  
  
##  <a name="writetostream"></a>  CComBSTR::WriteToStream  
 저장 된 [m_str](#m_str) 스트림에 멤버입니다.  
  
```
HRESULT WriteToStream(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pStream`  
 [in] 에 대 한 포인터는 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) 스트림에서 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 BSTR에서 사용 하 여 스트림의 내용 다시 만들 수 있습니다는 [ReadFromStream](#readfromstream) 함수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities#45](../../atl/codesnippet/cpp/ccombstr-class_18.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)   
 [ATL 및 MFC 문자열 변환 매크로](string-conversion-macros.md)
