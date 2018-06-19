---
title: CComVariant 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComVariant
- ATLCOMCLI/ATL::CComVariant
- ATLCOMCLI/ATL::CComVariant::CComVariant
- ATLCOMCLI/ATL::CComVariant::Attach
- ATLCOMCLI/ATL::CComVariant::ChangeType
- ATLCOMCLI/ATL::CComVariant::Clear
- ATLCOMCLI/ATL::CComVariant::Copy
- ATLCOMCLI/ATL::CComVariant::CopyTo
- ATLCOMCLI/ATL::CComVariant::Detach
- ATLCOMCLI/ATL::CComVariant::GetSize
- ATLCOMCLI/ATL::CComVariant::ReadFromStream
- ATLCOMCLI/ATL::CComVariant::SetByRef
- ATLCOMCLI/ATL::CComVariant::WriteToStream
dev_langs:
- C++
helpviewer_keywords:
- VARIANT macro
- CComVariant class
- VARIANT macro, ATL
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e2ebef74f6da48d2124d69f002a85c467db73406
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366018"
---
# <a name="ccomvariant-class"></a>CComVariant 클래스
이 클래스를 래핑하는 `VARIANT` 형식, 저장 된 데이터의 형식을 나타내는 멤버를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
cpp
class CComVariant : public tagVARIANT  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComVariant::CComVariant](#ccomvariant)|생성자입니다.|  
|[CComVariant:: ~ CComVariant](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComVariant::Attach](#attach)|연결 된 **VARIANT** 에 `CComVariant` 개체입니다.|  
|[CComVariant::ChangeType](#changetype)|변환 된 `CComVariant` 개체를 새 형식입니다.|  
|[CComVariant::Clear](#clear)|지웁니다는 `CComVariant` 개체입니다.|  
|[CComVariant::Copy](#copy)|복사는 **VARIANT** 에 `CComVariant` 개체입니다.|  
|[CComVariant::CopyTo](#copyto)|내용을 복사는 `CComVariant` 개체입니다.|  
|[CComVariant::Detach](#detach)|내부 분리 **VARIANT** 에서 `CComVariant` 개체입니다.|  
|[CComVariant::GetSize](#getsize)|크기의 내용의 바이트 수를 반환 된 `CComVariant` 개체입니다.|  
|[CComVariant::ReadFromStream](#readfromstream)|로드 한 **VARIANT** 스트림에서 합니다.|  
|[CComVariant::SetByRef](#setbyref)|초기화는 `CComVariant` 개체 및 설정은 **vt** 멤버를 **VT_BYREF**합니다.|  
|[CComVariant::WriteToStream](#writetostream)|내부 저장 **VARIANT** 스트림으로 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|||  
|-|-|  
|[CComVariant::operator <](#operator_lt)|나타냅니다 여부는 `CComVariant` 개체가 지정 된 보다 작은지 **VARIANT**합니다.|  
|[CComVariant::operator >](#operator_gt)|나타냅니다 여부는 `CComVariant` 개체가 지정 된 보다 큰지 **VARIANT**합니다.|  
|[operator! =](#operator_neq)|나타냅니다 여부는 `CComVariant` 지정 된 개체와 같지 않습니다 **VARIANT**합니다.|  
|[operator =](#operator_eq)|에 값을 할당는 `CComVariant` 개체입니다.|  
|[operator ==](#operator_eq_eq)|나타냅니다 여부는 `CComVariant` 개체가 지정 된 같음 **VARIANT**합니다.|  
  
## <a name="remarks"></a>설명  
 `CComVariant` 래핑하는 `VARIANT and VARIANTARG` 공용 구조체 및 공용 구조체에 저장 된 데이터의 형식을 나타내는 구성원으로 구성 된 유형입니다. **VARIANT**의자동화에서 일반적으로 사용 됩니다.  
  
 `CComVariant` 파생 되는 **VARIANT** 입력 될 수 있도록 아무 곳에 나 사용을 **VARIANT** 사용할 수 있습니다. 예를 들어 사용할 수 있습니다는 **V_VT** 유형을 추출 하는 매크로 `CComVariant` 하거나 액세스할 수 있습니다는 **vt** 멤버 수와 같은 직접 방법는 **VARIANT**합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `tagVARIANT`  
  
 `CComVariant`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcomcli.h  
  
##  <a name="attach"></a>  CComVariant::Attach  
 현재 콘텐츠를 안전 하 게 지웁니다는 `CComVariant` 개체의 내용을 복사, `pSrc` 이 개체에 다음에서 variant 형식의 설정 `pSrc` 를 `VT_EMPTY`합니다.  
  
```
HRESULT Attach(VARIANT* pSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 `pSrc`  
 [in] 가리키는 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) 개체에 연결 되어야 합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 에 보관 된 데이터의 소유권 `pSrc` 으로 전송 되는 `CComVariant` 개체입니다.  
  
##  <a name="ccomvariant"></a>  CComVariant::CComVariant  
 안전 초기화를 처리 하는 각 생성자는 `CComVariant` 호출 하 여 개체는 `VariantInit` Win32 함수 또는 개체의 값과 전달 된 매개 변수에 따라 형식을 설정 하 여 합니다.  
  
```
CComVariant() throw();
CComVariant(const CComVariant& varSrc);
CComVariant(const VARIANT& varSrc);
CComVariant(LPCOLESTR lpszSrc);
CComVariant(LPCSTR lpszSrc);
CComVariant(bool bSrc);
CComVariant(BYTE nSrc) throw();
CComVariant(int nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned int  nSrc, VARTYPE vtSrc = VT_UI4) throw();
CComVariant(shor  nSrc) throw();
CComVariant(unsigned short nSrc) throw();
CComVariant(long  nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned long  nSrc) throw();
CComVariant(LONGLONG  nSrc) throw();
CComVariant(ULONGLONG  nSrc) throw();
CComVariant(float  fltSrc) throw();
CComVariant(double  dblSrc, VARTYPE vtSrc = VT_R8) throw();
CComVariant(CY  cySrc) throw();
CComVariant(IDispatch* pSrc) throw();
CComVariant(IUnknown* pSrc) throw();
CComVariant(const SAFEARRAY* pSrc);
CComVariant(char  cSrc) throw();
CComVariant(const CComBSTR& bstrSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 *varSrc*  
 [in] `CComVariant` 또는 `VARIANT` 초기화 하는 데는 `CComVariant` 개체입니다. 소스 variant의 내용이 변환 하지 않고 대상으로 복사 됩니다.  
  
 `lpszSrc`  
 [in] 초기화 하는 데 사용할 문자열의 `CComVariant` 개체입니다. (0으로 종료 와이드 유니코드) 문자열을 전달할 수 있습니다는 **LPCOLESTR** 버전의 생성자 또는 ANSI 문자열에는 `LPCSTR` 버전입니다. 두 경우 모두에 문자열을 유니코드로 변환 됩니다 `BSTR` 사용 하 여 할당 **SysAllocString**합니다. 종류는 `CComVariant` 개체 됩니다 `VT_BSTR`합니다.  
  
 `bSrc`  
 [in] `bool` 초기화 하는 데는 `CComVariant` 개체입니다. `bool` 인수는 변환 된 **VARIANT_BOOL** 저장 되기 전에 합니다. 종류는 `CComVariant` 개체 됩니다 `VT_BOOL`합니다.  
  
 `nSrc`  
 [in] `int`, **바이트**, **짧은**, **긴**, **LONGLONG**, **ULONGLONG**, **부호 없는 short**, `unsigned long`, 또는 `unsigned int` 초기화 하는 데는 `CComVariant` 개체입니다. 종류는 `CComVariant` 개체 됩니다 `VT_I4`, `VT_UI1`, `VT_I2`, `VT_I4`, **VT_I8**, **VT_UI8**, **VT_UI2**,  **VT_UI4**, 또는 **VT_UI4**각각.  
  
 `vtSrc`  
 [in] Variant의 형식입니다. 첫 번째 매개 변수 인 경우 `int`, 올바른 유형은 `VT_I4` 및 **VT_INT**합니다. 첫 번째 매개 변수 인 경우 **긴**, 올바른 유형은 `VT_I4` 및 `VT_ERROR`합니다. 첫 번째 매개 변수 인 경우 **double**, 올바른 유형은 `VT_R8` 및 `VT_DATE`합니다. 첫 번째 매개 변수 인 경우 `unsigned int`, 올바른 유형은 **VT_UI4** 및 **VT_UINT**합니다.  
  
 `fltSrc`  
 [in] **float** 초기화 하는 데는 `CComVariant` 개체입니다. 종류는 `CComVariant` 개체 됩니다 `VT_R4`합니다.  
  
 `dblSrc`  
 [in] **double** 초기화 하는 데는 `CComVariant` 개체입니다. 종류는 `CComVariant` 개체 됩니다 `VT_R8`합니다.  
  
 `cySrc`  
 [in] **CY** 초기화 하는 데는 `CComVariant` 개체입니다. 종류는 `CComVariant` 개체 됩니다 `VT_CY`합니다.  
  
 `pSrc`  
 [in] `IDispatch` 또는 **IUnknown** 포인터를 초기화 하는 데 사용 된 `CComVariant` 개체입니다. `AddRef` 인터페이스 포인터에서 호출 됩니다. 유형의 `CComVariant` 개체 됩니다 **VT_DISPATCH** 또는 **VT_UNKNOWN**각각.  
  
 또는 **SAFERRAY** 포인터를 초기화 하는 데 사용 된 `CComVariant` 개체입니다. 복사본은 **SAFEARRAY** 에 저장 되는 `CComVariant` 개체입니다. 종류는 `CComVariant` 개체는 원래 유형의의 조합 수 있는지는 **SAFEARRAY** 및 **VT_ARRAY**합니다.  
  
 `cSrc`  
 [in] `char` 초기화 하는 데는 `CComVariant` 개체입니다. 종류는 `CComVariant` 개체 됩니다 **VT_I1**합니다.  
  
 `bstrSrc`  
 [in] 초기화를 사용 하는 BSTR는 `CComVariant` 개체입니다. 종류는 `CComVariant` 개체 됩니다 `VT_BSTR`합니다.  
  
### <a name="remarks"></a>설명  
 소멸자를 호출 하 여 정리 관리 [CComVariant::Clear](#clear)합니다.  
  
##  <a name="dtor"></a>  CComVariant:: ~ CComVariant  
 소멸자입니다.  
  
```
~CComVariant() throw();
```  
  
### <a name="remarks"></a>설명  
 이 메서드를 호출 하 여 정리 관리 [CComVariant::Clear](#clear)합니다.  
  
##  <a name="changetype"></a>  CComVariant::ChangeType  
 변환 된 `CComVariant` 개체를 새 형식입니다.  
  
```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `vtNew`  
 [in] 에 대 한 새 형식을 `CComVariant` 개체입니다.  
  
 `pSrc`  
 [in] 에 대 한 포인터는 `VARIANT` 값을 갖는 새 형식으로 변환 됩니다. 기본값은 **NULL**즉는 `CComVariant` 위치에서 개체를 변환 됩니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 에 대 한 값을 전달 하는 경우 `pSrc`, `ChangeType` ´ ֲ이 **VARIANT** 변환에 대 한 소스로 합니다. 그렇지 않은 경우는 `CComVariant` 개체 소스 됩니다.  
  
##  <a name="clear"></a>  CComVariant::Clear  
 지웁니다는 `CComVariant` 호출 하 여 개체는 `VariantClear` Win32 함수입니다.  
  
```
HRESULT Clear();
```  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 소멸자를 자동으로 호출 **지우기**합니다.  
  
##  <a name="copy"></a>  CComVariant::Copy  
 해제 된 `CComVariant` 개체를 지정 된 복사 할당 **VARIANT**합니다.  
  
```
HRESULT Copy(const VARIANT* pSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 `pSrc`  
 [in] 에 대 한 포인터는 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) 복사할 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="copyto"></a>  CComVariant::CopyTo  
 내용을 복사는 `CComVariant` 개체입니다.  
  
```
HRESULT CopyTo(BSTR* pstrDest);
```  
  
### <a name="parameters"></a>매개 변수  
 *pstrDest*  
 가리키는 `BSTR` 내용의 복사본을 받게 됩니다 하는 `CComVariant` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 **CComVariant** 개체 유형 이어야 `VT_BSTR`합니다.  
  
##  <a name="detach"></a>  CComVariant::Detach  
 내부 분리 **VARIANT** 에서 `CComVariant` 개체 및 개체의 형식을 설정 `VT_EMPTY`합니다.  
  
```
HRESULT Detach(VARIANT* pDest);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDest`  
 [out] 기본 반환 `VARIANT` 개체의 값입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 내용을 `VARIANT` 참조 `pDest` 호출의 종류와 값이 할당 되기 전에 자동으로 해제 됩니다 **CComVariant** 개체입니다.  
  
##  <a name="getsize"></a>  CComVariant::GetSize  
 단순 고정 크기에 대 한 `VARIANT`s,이 메서드는 반환 된 `sizeof` 기본 데이터 형식 더하기 `sizeof(VARTYPE)`합니다.  
  
```
ULONG GetSize() const;
```  
  
### <a name="return-value"></a>반환 값  
 현재 내용의 바이트 크기는 `CComVariant` 개체입니다.  
  
### <a name="remarks"></a>설명  
 경우는 `VARIANT` 인터페이스 포인터를 포함 `GetSize` 쿼리하는지 `IPersistStream` 또는 `IPersistStreamInit`합니다. 성공의 반환 값은 반환 값의 하위 32 비트 `GetSizeMax` 과 `sizeof` 는 `CLSID` 및 `sizeof(VARTYPE)`합니다. 인터페이스 포인터가 있으면 `NULL`, `GetSize` 반환는 `sizeof` 는 `CLSID` 플러스 `sizeof(VARTYPE)`합니다. 총 크기 보다 큰 경우 `ULONG_MAX`, `GetSize` 반환 `sizeof(VARTYPE)` 오류가 나타냅니다.  
  
 다른 모든 경우에, 임시 `VARIANT` 형식의 `VT_BSTR` 이 현재에서 강제 변환 `VARIANT`합니다. 이 길이 `BSTR` 크기 문자열의 길이 문자열 자체의 길이 null 문자를 더하기의 크기를 더한 값으로 계산 `sizeof(VARTYPE)`합니다. 경우는 `VARIANT` 으로 강제 변환할 수는 `VARIANT` 형식의 `VT_BSTR`, `GetSize` 반환 `sizeof(VARTYPE)`합니다.  
  
 이 메서드에 의해 반환 되는 크기에 사용 된 바이트 수와 일치 [CComVariant::WriteToStream](#writetostream) 성공 조건입니다.  
  
##  <a name="operator_eq"></a>  CComVariant::operator =  
 값과 해당 형식에 지정 된 `CComVariant` 개체입니다.  
  
```
CComVariant& operator=(const CComVariant& varSrc);
CComVariant& operator=(const VARIANT& varSrc);
CComVariant& operator=(const CComBSTR& bstrSrc);
CComVariant& operator=(LPCOLESTR lpszSrc);
CComVariant& operator=(LPCSTR lpszSrc);
CComVariant& operator=(bool bSrc);
CComVariant& operator=(BYTE nSrc) throw();
CComVariant& operator=int nSrc) throw();
CComVariant& operator=(unsigned int nSrc) throw();
CComVariant& operator=(short nSrc) throw();
CComVariant& operator=(unsigned short nSrc) throw();
CComVariant& operator=(long nSrc) throw();
CComVariant& operator=(unsigned long nSrc) throw();
CComVariant& operator=(LONGLONG nSrc) throw();
CComVariant& operator=(ULONGLONG nSrc) throw();
CComVariant& operator=(float fltSrc) throw();
CComVariant& operator=(double dblSrc) throw();
CComVariant& operator=(CY cySrc) throw();
CComVariant& operator=(IDispatch* pSrc) throw();
CComVariant& operator=(IUnknown* pSrc) throw();
CComVariant& operator=(const SAFEARRAY* pSrc);
CComVariant& operator=(char cSrc) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *varSrc*  
 [in] `CComVariant` 또는 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) 에 할당할 수는 `CComVariant` 개체입니다. 소스 variant의 내용이 변환 하지 않고 대상으로 복사 됩니다.  
  
 `bstrSrc`  
 [in] 에 할당할 BSTR는 `CComVariant` 개체입니다. 종류는 `CComVariant` 개체 됩니다 `VT_BSTR`합니다.  
  
 `lpszSrc`  
 [in] 에 할당할 문자열은 `CComVariant` 개체입니다. (0으로 종료 와이드 유니코드) 문자열을 전달할 수 있습니다는 **LPCOLESTR** 연산자나를 ANSI 문자열의 버전은 `LPCSTR` 버전입니다. 두 경우 모두, 문자열을 유니코드로 변환 됩니다 `BSTR` 사용 하 여 할당 **SysAllocString**합니다. 종류는 `CComVariant` 개체 됩니다 `VT_BSTR`합니다.  
  
 `bSrc`  
 [in] `bool` 에 할당할 수는 `CComVariant` 개체입니다. `bool` 인수는 변환 된 **VARIANT_BOOL** 저장 되기 전에 합니다. 종류는 `CComVariant` 개체 됩니다 `VT_BOOL`합니다.  
  
 `nSrc`  
 [in] `int`, **바이트**, **짧은**, **긴**, **LONGLONG**, **ULONGLONG**, **부호 없는 short**, `unsigned long`, 또는 `unsigned int` 에 할당할 수는 `CComVariant` 개체입니다. 종류는 `CComVariant` 개체 됩니다 `VT_I4`, `VT_UI1`, `VT_I2`, `VT_I4`, **VT_I8**, **VT_UI8**, **VT_UI2**,  **VT_UI4**, 또는 **VT_UI4**각각.  
  
 `fltSrc`  
 [in] **float** 에 할당할 수는 `CComVariant` 개체입니다. 종류는 `CComVariant` 개체 됩니다 `VT_R4`합니다.  
  
 `dblSrc`  
 [in] **double** 에 할당할 수는 `CComVariant` 개체입니다. 종류는 `CComVariant` 개체 됩니다 `VT_R8`합니다.  
  
 `cySrc`  
 [in] **CY** 에 할당할 수는 `CComVariant` 개체입니다. 종류는 `CComVariant` 개체 됩니다 `VT_CY`합니다.  
  
 `pSrc`  
 [in] `IDispatch` 또는 **IUnknown** 포인터에 할당할 수는 `CComVariant` 개체입니다. `AddRef` 인터페이스 포인터에서 호출 됩니다. 유형의 `CComVariant` 개체 됩니다 **VT_DISPATCH** 또는 **VT_UNKNOWN**각각.  
  
 또는, **SAFEARRAY** 포인터에 할당할 수는 `CComVariant` 개체입니다. 복사본은 **SAFEARRAY** 에 저장 되는 `CComVariant` 개체입니다. 종류는 `CComVariant` 개체는 원래 유형의의 조합 수 있는지는 **SAFEARRAY** 및 **VT_ARRAY**합니다.  
  
 `cSrc`  
 [in] 에 할당할 char는 `CComVariant` 개체입니다. 종류는 `CComVariant` 개체 됩니다 **VT_I1**합니다.  
  
##  <a name="operator_eq_eq"></a>  CComVariant::operator = =  
 나타냅니다 여부는 `CComVariant` 개체가 지정 된 같음 **VARIANT**합니다.  
  
```
bool operator==(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>설명  
 반환 **true** 경우의 유형과 값 *varSrc* 과 같은 값과 형식을, 각각의 `CComVariant` 개체입니다. 그렇지 않으면 **false**합니다. 연산자 비교를 수행 하려면 사용자의 기본 로캘을 사용 합니다.  
  
 연산자는 variant 형식의 값만 비교합니다. 문자열, 정수 및 부동 소수점 하지만 하지 배열 또는 레코드를 비교합니다.  
  
##  <a name="operator_neq"></a>  CComVariant::operator! =  
 나타냅니다 여부는 `CComVariant` 지정 된 개체와 같지 않습니다 **VARIANT**합니다.  
  
```
bool operator!=(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>설명  
 반환 **true** 경우 값 또는 유형의 *varSrc* , 형식 또는 값과 같지 않은 각각의 `CComVariant` 개체입니다. 그렇지 않으면 **false**합니다. 연산자 비교를 수행 하려면 사용자의 기본 로캘을 사용 합니다.  
  
 연산자는 variant 형식의 값만 비교합니다. 문자열, 정수 및 부동 소수점 하지만 하지 배열 또는 레코드를 비교합니다.  
  
##  <a name="operator_lt"></a>  CComVariant::operator &lt;  
 나타냅니다 여부는 `CComVariant` 개체가 지정 된 보다 작은지 **VARIANT**합니다.  
  
```
bool operator<(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>설명  
 반환 **true** 경우의 값은 `CComVariant` 개체의 값 보다 작으면 *varSrc*합니다. 그렇지 않으면 **false**합니다. 연산자 비교를 수행 하려면 사용자의 기본 로캘을 사용 합니다.  
  
##  <a name="operator_gt"></a>  CComVariant::operator &gt;  
 나타냅니다 여부는 `CComVariant` 개체가 지정 된 보다 큰지 **VARIANT**합니다.  
  
```
bool operator>(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>설명  
 반환 **true** 경우의 값은 `CComVariant` 개체의 값 보다 크면 *varSrc*합니다. 그렇지 않으면 **false**합니다. 연산자 비교를 수행 하려면 사용자의 기본 로캘을 사용 합니다.  
  
##  <a name="readfromstream"></a>  CComVariant::ReadFromStream  
 기본 설정 **VARIANT** 에 **VARIANT** 에 지정된 된 스트림을 포함 합니다.  
  
```
HRESULT ReadFromStream(IStream* pStream);
```  
  
### <a name="parameters"></a>매개 변수  
 `pStream`  
 [in] 에 대 한 포인터는 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) 인터페이스에서 데이터를 포함 하는 스트림입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 **ReadToStream** 이전 호출을 [WriteToStream](#writetostream)합니다.  
  
##  <a name="setbyref"></a>  CComVariant::SetByRef  
 초기화는 `CComVariant` 개체 및 설정은 **vt** 멤버를 **VT_BYREF**합니다.  
  
```
template < typename T >
void SetByRef(T* pT) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `T`  
 유형의 **VARIANT**, 예를 들어 `BSTR`, `int`, 또는 `char`합니다.  
  
 *pT*  
 초기화 하는 데 포인터는 `CComVariant` 개체입니다.  
  
### <a name="remarks"></a>설명  
 `SetByRef` 가 초기화 하는 함수 템플릿이 `CComVariant` 개체 포인터를 *pT* 설정 하 고는 **vt** 멤버를 **VT_BYREF**합니다. 예를 들어:  
  
 [!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]  
  
##  <a name="writetostream"></a>  CComVariant::WriteToStream  
 내부 저장 **VARIANT** 스트림으로 합니다.  
  
```
HRESULT WriteToStream(IStream* pStream);
```  
  
### <a name="parameters"></a>매개 변수  
 `pStream`  
 [in] 에 대 한 포인터는 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) 스트림에서 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)