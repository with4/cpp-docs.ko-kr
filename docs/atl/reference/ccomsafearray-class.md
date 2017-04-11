---
title: "CComSafeArray 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSafeArray
- ATLSAFE/ATL::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::Add
- ATLSAFE/ATL::CComSafeArray::Attach
- ATLSAFE/ATL::CComSafeArray::CopyFrom
- ATLSAFE/ATL::CComSafeArray::CopyTo
- ATLSAFE/ATL::CComSafeArray::Create
- ATLSAFE/ATL::CComSafeArray::Destroy
- ATLSAFE/ATL::CComSafeArray::Detach
- ATLSAFE/ATL::CComSafeArray::GetAt
- ATLSAFE/ATL::CComSafeArray::GetCount
- ATLSAFE/ATL::CComSafeArray::GetDimensions
- ATLSAFE/ATL::CComSafeArray::GetLowerBound
- ATLSAFE/ATL::CComSafeArray::GetSafeArrayPtr
- ATLSAFE/ATL::CComSafeArray::GetType
- ATLSAFE/ATL::CComSafeArray::GetUpperBound
- ATLSAFE/ATL::CComSafeArray::IsSizable
- ATLSAFE/ATL::CComSafeArray::MultiDimGetAt
- ATLSAFE/ATL::CComSafeArray::MultiDimSetAt
- ATLSAFE/ATL::CComSafeArray::Resize
- ATLSAFE/ATL::CComSafeArray::SetAt
- ATLSAFE/ATL::CComSafeArray::m_psa
dev_langs:
- C++
helpviewer_keywords:
- CComSafeArray class
ms.assetid: ee349aef-33db-4c85-bd08-5d86a3c9d53a
caps.latest.revision: 26
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 6e1337bee7dc6ca6f64f59657379f7d8ae40f5f8
ms.lasthandoff: 04/04/2017

---
# <a name="ccomsafearray-class"></a>CComSafeArray 클래스
이 클래스는 **SAFEARRAY** 구조체의 래퍼입니다.  
  
## <a name="syntax"></a>구문  
  
```
template <typename T, VARTYPE _vartype = _ATL_AutomationType<T>::type>
class CComSafeArray
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 배열에 저장할 데이터의 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComSafeArray::CComSafeArray](#ccomsafearray)|생성자입니다.|  
|[CComSafeArray:: ~ CComSafeArray](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComSafeArray::Add](#add)|하나 이상의 요소 또는 **SAFEARRAY** 구조체를 `CComSafeArray`에 추가합니다.|  
|[CComSafeArray::Attach](#attach)|**SAFEARRAY** 구조체를 `CComSafeArray` 개체에 연결합니다.|  
|[CComSafeArray::CopyFrom](#copyfrom)|**SAFEARRAY** 구조체의 내용을 `CComSafeArray` 개체에 복사합니다.|  
|[CComSafeArray::CopyTo](#copyto)|`CComSafeArray` 개체의 복사본을 만듭니다.|  
|[Ccomsafearray:: Create](#create)|
          `CComSafeArray` 개체를 만듭니다.|  
|[Ccomsafearray:: Destroy](#destroy)|`CComSafeArray` 개체를 제거합니다.|  
|[CComSafeArray::Detach](#detach)|**SAFEARRAY** 를 `CComSafeArray` 개체에서 분리합니다.|  
|[CComSafeArray::GetAt](#getat)|1차원 배열에서 단일 요소를 검색합니다.|  
|[CComSafeArray::GetCount](#getcount)|배열의 요소 수를 반환합니다.|  
|[CComSafeArray::GetDimensions](#getdimensions)|배열의 차원 수를 반환합니다.|  
|[CComSafeArray::GetLowerBound](#getlowerbound)|배열의 지정된 차원에 대한 하한을 반환합니다.|  
|[CComSafeArray::GetSafeArrayPtr](#getsafearrayptr)|`m_psa` 데이터 멤버의 주소를 반환합니다.|  
|[CComSafeArray::GetType](#gettype)|배열에 저장된 데이터의 형식을 반환합니다.|  
|[CComSafeArray::GetUpperBound](#getupperbound)|배열의 모든 차원에 대한 상한을 반환합니다.|  
|[CComSafeArray::IsSizable](#issizable)|`CComSafeArray` 개체의 크기를 조정할 수 있는지 테스트합니다.|  
|[CComSafeArray::MultiDimGetAt](#multidimgetat)|다차원 배열에서 단일 요소를 검색합니다.|  
|[CComSafeArray::MultiDimSetAt](#multidimsetat)|다차원 배열의 요소 값을 설정합니다.|  
|[CComSafeArray::Resize](#resize)|`CComSafeArray` 개체의 크기를 조정합니다.|  
|[CComSafeArray::SetAt](#setat)|1차원 배열의 요소 값을 설정합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CComSafeArray::operator LPSAFEARRAY](#operator_lpsafearray)|**SAFEARRAY** 포인터에 값을 캐스팅합니다.|  
|[CComSafeArray::operator\[\]](ccomsafearray-class.md#operator_at)|배열에서 요소를 검색합니다.|  
|[CComSafeArray::operator =](#operator_eq)|대입 연산자입니다.|  

  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CComSafeArray::m_psa](#m_psa)|이 데이터 멤버는 **SAFEARRAY** 구조체의 주소를 유지합니다.|  
  
## <a name="remarks"></a>주의  
 `CComSafeArray`에 대 한 래퍼를 제공는 [SAFEARRAY 데이터 형식](http://msdn.microsoft.com/en-us/9ec8025b-4763-4526-ab45-390c5d8b3b1e) 만들고의 거의 모든 VARIANT 지원 형식의 1 차원 및 다차원 배열을 관리를 간단 하 게 만드는 클래스입니다.  
  
 `CComSafeArray`는 프로세스 간의 배열 전달을 간소화할 뿐만 아니라 상한과 하한에 대해 배열 인덱스 값을 확인하여 추가 보안을 제공합니다.  
  
 `CComSafeArray`의 하한은 모든 사용자 정의 값에서 시작할 수 있지만 C++를 통해 액세스하는 배열에서는 0을 하한으로 사용해야 합니다. Visual Basic과 같은 다른 언어에서는 다른 경계 값(예: -10~10)을 사용할 수 있습니다.  
  
 사용 하 여 [ccomsafearray:: Create](#create) 를 만드는 `CComSafeArray` 개체 및 [ccomsafearray:: Destroy](#destroy) 삭제할 수 있습니다.  
  
 `CComSafeArray` 는 VARIANT 데이터 형식의 다음 하위 집합을 포함할 수 있습니다.  
  
|VARTYPE|설명|  
|-------------|-----------------|  
|VT_I1|char|  
|VT_I2|short|  
|VT_I4|int|  
|VT_I4|long|  
|VT_I8|longlong|  
|VT_UI1|byte|  
|VT_UI2|ushort|  
|VT_UI4|uint|  
|VT_UI4|ulong|  
|VT_UI8|ulonglong|  
|VT_R4|float|  
|VT_R8|double|  
|VT_DECIMAL|decimal pointer|  
|VT_VARIANT|variant pointer|  
|VT_CY|Currency 데이터 형식|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsafe.h  
  
## <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities # 75](../../atl/codesnippet/cpp/ccomsafearray-class_1.cpp)]  
  
##  <a name="add"></a>CComSafeArray::Add  
 하나 이상의 요소 또는 **SAFEARRAY** 구조체를 `CComSafeArray`에 추가합니다.  
  
```
HRESULT Add(const SAFEARRAY* psaSrc);
HRESULT Add(ULONG ulCount, const T* pT, BOOL bCopy = TRUE);
HRESULT Add(const T& t, BOOL bCopy = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `psaSrc`  
 에 대 한 포인터는 **SAFEARRAY** 개체입니다.  
  
 `ulCount`  
 배열에 추가할 개체의 수입니다.  
  
 *pT*  
 배열에 추가할 하나 이상의 개체에 대 한 포인터입니다.  
  
 *t*  
 배열에 추가할 개체에 대 한 참조입니다.  
  
 `bCopy`  
 데이터의 복사본을 만들어야 하는지 여부를 나타냅니다. 기본값은 **TRUE**합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 새 개체는 기존의 끝에 추가 됩니다. **SAFEARRAY** 개체입니다. 개체를 추가 하는 다차원 **SAFEARRAY** 개체가 지원 되지 않습니다. 기존 개체의 배열에 추가할 때는 두 배열에 동일한 형식의 요소가 있어야 합니다.  
  
 `bCopy` 플래그 고려할 때 형식의 요소 `BSTR` 또는 **VARIANT** 배열에 추가 됩니다. 기본값 **TRUE** 요소 배열에 추가 될 때 데이터의 새 복사본이 생성 되 보장 합니다.  
  
##  <a name="attach"></a>CComSafeArray::Attach  
 **SAFEARRAY** 구조체를 `CComSafeArray` 개체에 연결합니다.  
  
```
HRESULT Attach(const SAFEARRAY* psaSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 `psaSrc`  
 에 대 한 포인터는 **SAFEARRAY** 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 연결는 **SAFEARRAY** 구조체는 `CComSafeArray` 개체를 기존 `CComSafeArray` 사용할 수 있는 방법입니다.  
  
##  <a name="ccomsafearray"></a>CComSafeArray::CComSafeArray  
 생성자입니다.  
  
```
CComSafeArray();
CComSafeArray(const SAFEARRAYBOUND& bound);
CComSafeArray(ULONG  ulCount, LONG lLBound = 0);
CComSafeArray(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
CComSafeArray(const CComSafeArray& saSrc);
CComSafeArray(const SAFEARRAY& saSrc);
CComSafeArray(const SAFEARRAY* psaSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 `bound`  
 A **SAFEARRAYBOUND** 구조입니다.  
  
 `ulCount`  
 배열의 요소 수입니다.  
  
 `lLBound`  
 하 한 값입니다. 즉, 배열의 첫 번째 요소의 인덱스입니다.  
  
 `pBound`  
 에 대 한 포인터는 **SAFEARRAYBOUND** 구조입니다.  
  
 `uDims`  
 배열의 차원 수입니다.  
  
 `saSrc`  
 에 대 한 참조는 **SAFEARRAY** 구조 또는 `CComSafeArray` 개체입니다. 두 경우 모두 생성자가이 참조를 사용 하 여 생성 한 후 배열을 참조 하지 않는 정도의 배열의 복사본을 만들어야 하 합니다.  
  
 `psaSrc`  
 에 대 한 포인터는 **SAFEARRAY** 구조입니다. 생성자는이 주소를 사용 하 여 배열 생성 한 후 참조 되지 않은 정도의 배열의 복사본을 만들어야 하 합니다.  
  
### <a name="remarks"></a>설명  
 
          `CComSafeArray` 개체를 만듭니다.  
  
##  <a name="dtor"></a>CComSafeArray:: ~ CComSafeArray  
 소멸자입니다.  
  
```
~CComSafeArray() throw()
```  
  
### <a name="remarks"></a>주의  
 할당 된 모든 리소스를 해제합니다.  
  
##  <a name="copyfrom"></a>CComSafeArray::CopyFrom  
 **SAFEARRAY** 구조체의 내용을 `CComSafeArray` 개체에 복사합니다.  
  
```
HRESULT CopyFrom(LPSAFEARRAY* ppArray);
```  
  
### <a name="parameters"></a>매개 변수  
 `ppArray`  
 에 대 한 포인터는 **SAFEARRAY** 복사 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 콘텐츠를 복사 하는이 메서드는 **SAFEARRAY** 현재 `CComSafeArray` 개체입니다. 배열의 기존 내용은 대체 됩니다.  
  
##  <a name="copyto"></a>CComSafeArray::CopyTo  
 `CComSafeArray` 개체의 복사본을 만듭니다.  
  
```
HRESULT CopyTo(LPSAFEARRAY* ppArray);
```  
  
### <a name="parameters"></a>매개 변수  
 `ppArray`  
 만들 새 위치에 대 한 포인터 **SAFEARRAY**합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 콘텐츠를 복사 하는이 메서드는 `CComSafeArray` 개체는 **SAFEARRAY** 구조입니다.  
  
##  <a name="create"></a>Ccomsafearray:: Create  
 
          `CComSafeArray`을 만듭니다.  
  
```
HRESULT Create(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
HRESULT Create(ULONG ulCount = 0, LONG lLBound = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `pBound`  
 에 대 한 포인터는 **SAFEARRAYBOUND** 개체입니다.  
  
 `uDims`  
 배열의 차원 수를 지정 합니다.  
  
 `ulCount`  
 배열의 요소 수입니다.  
  
 `lLBound`  
 하 한 값입니다. 즉, 배열의 첫 번째 요소의 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 A `CComSafeArray` 기존 개체를 만들 수 **SAFEARRAYBOUND** 구조와 차원 또는 한과 배열의 요소 수를 지정 하 여 수 있습니다. 배열이 Visual c + +에서 액세스 해야 하는 경우 하한값 0 이어야 합니다. 다른 언어 하한값 (예:-10 ~ 10 같은 범위를 요소와 Visual Basic에서는 배열)에 대 한 다른 값을 허용할 수 있습니다.  
  
##  <a name="destroy"></a>Ccomsafearray:: Destroy  
 `CComSafeArray` 개체를 제거합니다.  
  
```
HRESULT Destroy();
```  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 기존 소멸 `CComSafeArray` 개체와 모든 포함 된 데이터입니다.  
  
##  <a name="detach"></a>CComSafeArray::Detach  
 **SAFEARRAY** 를 `CComSafeArray` 개체에서 분리합니다.  
  
```
LPSAFEARRAY Detach();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터를 반환 합니다.는 **SAFEARRAY** 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 분리는 **SAFEARRAY** 에서 개체는 `CComSafeArray` 개체입니다.  
  
##  <a name="getat"></a>CComSafeArray::GetAt  
 1차원 배열에서 단일 요소를 검색합니다.  
  
```
T& GetAt(LONG lIndex) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `lIndex`  
 반환할 배열에 있는 값의 인덱스 번호입니다.  
  
### <a name="return-value"></a>반환 값  
 필요한 배열 요소에 대 한 참조를 반환합니다.  
  
##  <a name="getcount"></a>CComSafeArray::GetCount  
 배열의 요소 수를 반환합니다.  
  
```
ULONG GetCount(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `uDim`  
 배열 차원입니다.  
  
### <a name="return-value"></a>반환 값  
 배열의 요소 수를 반환합니다.  
  
### <a name="remarks"></a>주의  
 다차원 배열에 사용 하는 경우이 메서드는 특정 차원에서 요소 수를 반환 합니다.  
  
##  <a name="getdimensions"></a>CComSafeArray::GetDimensions  
 배열의 차원 수를 반환합니다.  
  
```
UINT GetDimensions() const;
```  
  
### <a name="return-value"></a>반환 값  
 배열의 차원 수를 반환합니다.  
  
##  <a name="getlowerbound"></a>CComSafeArray::GetLowerBound  
 배열의 지정된 차원에 대한 하한을 반환합니다.  
  
```
LONG GetLowerBound(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `uDim`  
 하한값을 가져올 배열 차원입니다. 생략할 경우 기본값은 0입니다.  
  
### <a name="return-value"></a>반환 값  
 하한값을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 하 한이 0 이면 해당 첫 번째 요소는 요소 번호 0는 C 형식의 배열을 나타냅니다. 오류 발생 시 예를 들어 잘못 된 차원 인수에이 메서드를 호출 `AtlThrow` 오류를 설명 하는 hresult입니다.  
  
##  <a name="getsafearrayptr"></a>CComSafeArray::GetSafeArrayPtr  
 `m_psa` 데이터 멤버의 주소를 반환합니다.  
  
```
LPSAFEARRAY* GetSafeArrayPtr() throw();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터를 반환 합니다.는 [CComSafeArray::m_psa](#m_psa) 데이터 멤버입니다.  
  
##  <a name="gettype"></a>CComSafeArray::GetType  
 배열에 저장된 데이터의 형식을 반환합니다.  
  
```
VARTYPE GetType() const;
```  
  
### <a name="return-value"></a>반환 값  
 다음 유형 중 하나가 될 수 있는 배열에 저장 된 데이터 형식을 반환 합니다.  
  
|VARTYPE|설명|  
|-------------|-----------------|  
|VT_I1|char|  
|VT_I2|short|  
|VT_I4|int|  
|VT_I4|long|  
|VT_I8|longlong|  
|VT_UI1|byte|  
|VT_UI2|ushort|  
|VT_UI4|uint|  
|VT_UI4|ulong|  
|VT_UI8|ulonglong|  
|VT_R4|float|  
|VT_R8|double|  
|VT_DECIMAL|decimal pointer|  
|VT_VARIANT|variant pointer|  
|VT_CY|Currency 데이터 형식|  
  
##  <a name="getupperbound"></a>CComSafeArray::GetUpperBound  
 배열의 모든 차원에 대한 상한을 반환합니다.  
  
```
LONG GetUpperBound(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `uDim`  
 상한 값을 가져올 배열 차원입니다. 생략할 경우 기본값은 0입니다.  
  
### <a name="return-value"></a>반환 값  
 상한 값을 반환합니다. 이 값은 포함을이 차원에 대 한 유효한 최대 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 오류 발생 시 예를 들어 잘못 된 차원 인수에이 메서드를 호출 `AtlThrow` 오류를 설명 하는 hresult입니다.  
  
##  <a name="issizable"></a>CComSafeArray::IsSizable  
 `CComSafeArray` 개체의 크기를 조정할 수 있는지 테스트합니다.  
  
```
bool IsSizable() const;
```  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 경우는 `CComSafeArray` 조정할 수 있는 **false** 불가능 한 경우.  
  
##  <a name="m_psa"></a>CComSafeArray::m_psa  
 주소를 보유는 **SAFEARRAY** 구조에 액세스 합니다.  
  
```
LPSAFEARRAY m_psa;
```  
  
##  <a name="multidimgetat"></a>CComSafeArray::MultiDimGetAt  
 다차원 배열에서 단일 요소를 검색합니다.  
  
```
HRESULT MultiDimGetAt(const LONG* alIndex, T& t);
```  
  
### <a name="parameters"></a>매개 변수  
 `alIndex`  
 배열의 각 차원에 대 한 인덱스의 vector에 대 한 포인터입니다. 맨 왼쪽 (최상위) 차원이 `alIndex[0]`합니다.  
  
 *t*  
 반환 되는 데이터에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="multidimsetat"></a>CComSafeArray::MultiDimSetAt  
 다차원 배열의 요소 값을 설정합니다.  
  
```
HRESULT MultiDimSetAt(const LONG* alIndex, const T& t);
```  
  
### <a name="parameters"></a>매개 변수  
 `alIndex`  
 배열의 각 차원에 대 한 인덱스의 vector에 대 한 포인터입니다. 오른쪽에 있는 (최하위) 차원이 `alIndex`[0].  
  
 *T*  
 새 요소의 값을 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 이의 다차원 버전 [CComSafeArray::SetAt](#setat)합니다.  
  
##  <a name="operator_at"></a>CComSafeArray::operator\[\]  
 배열에서 요소를 검색합니다.  
  
```
T& operator[](long lindex) const;
T& operator[]int nindex) const;
```  
  
### <a name="parameters"></a>매개 변수  
 *nIndex 색인입니다.*  
 인덱스 번호는 배열에 있는 필수 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 적절 한 배열 요소를 반환합니다.  
  
### <a name="remarks"></a>설명  
 비슷한 기능을 수행 [CComSafeArray::GetAt](#getat)있지만이 연산자는 1 차원 배열에만 작동 합니다.  
  
##  <a name="operator_eq"></a>CComSafeArray::operator =  
 대입 연산자입니다.  
  
```
ATL::CComSafeArray<T>& operator=(const ATL::CComSafeArray& saSrc);
ATL::CComSafeArray<T>& operator=(const SAFEARRAY* psaSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 `saSrc`  
 `CComSafeArray` 개체에 대한 참조입니다.  
  
 `psaSrc`  
 에 대 한 포인터는 **SAFEARRAY** 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 배열에 저장된 데이터의 형식을 반환합니다.  
  
##  <a name="operator_lpsafearray"></a>CComSafeArray::operator LPSAFEARRAY  
 **SAFEARRAY** 포인터에 값을 캐스팅합니다.  
  
```
operator LPSAFEARRAY() const;
```  
  
### <a name="return-value"></a>반환 값  
 **SAFEARRAY** 포인터에 값을 캐스팅합니다.  
  
##  <a name="resize"></a>CComSafeArray::Resize  
 `CComSafeArray` 개체의 크기를 조정합니다.  
  
```
HRESULT Resize(const SAFEARRAYBOUND* pBound);
HRESULT Resize(ULONG ulCount, LONG lLBound = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `pBound`  
 에 대 한 포인터는 **SAFEARRAYBOUND** 요소 수 및 배열의 하한값에 대 한 정보가 포함 된 구조체입니다.  
  
 `ulCount`  
 요청 된 크기가 조정 된 배열에 있는 개체 수입니다.  
  
 `lLBound`  
 하 한입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 맨 오른쪽 차원만 조정합니다. 반환 하는 배열 크기가 조정 되지 것입니다 **IsResizable** 으로 **false**합니다.  
  
##  <a name="setat"></a>CComSafeArray::SetAt  
 1차원 배열의 요소 값을 설정합니다.  
  
```
HRESULT SetAt(LONG lIndex, const T& t, BOOL bCopy = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `lIndex`  
 설정할 수 있는 배열 요소의 인덱스 번호입니다.  
  
 *t*  
 지정한 요소의 새 값입니다.  
  
 `bCopy`  
 데이터의 복사본을 만들어야 하는지 여부를 나타냅니다. 기본값은 **TRUE**합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 `bCopy` 플래그 고려할 때 형식의 요소 `BSTR` 또는 **VARIANT** 배열에 추가 됩니다. 기본값 **TRUE** 요소 배열에 추가 될 때 데이터의 새 복사본이 생성 되 보장 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SAFEARRAY 데이터 형식](http://msdn.microsoft.com/en-us/9ec8025b-4763-4526-ab45-390c5d8b3b1e)   
 [Ccomsafearray:: Create](#create)   
 [Ccomsafearray:: Destroy](#destroy)   
 [클래스 개요](../../atl/atl-class-overview.md)

