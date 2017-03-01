---
title: "CComSafeArray 클래스 | Microsoft 문서"
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e78c0cb7a0e2fb6cc1e1ac4bba9186d4beee98b4
ms.lasthandoff: 02/24/2017

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
|[CComSafeArray::Create](#create)|
          `CComSafeArray` 개체를 만듭니다.|  
|[CComSafeArray::Destroy](#destroy)|`CComSafeArray` 개체를 제거합니다.|  
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
 `CComSafeArray`에 대 한 래퍼를 제공 된 [SAFEARRAY 데이터 형식](http://msdn.microsoft.com/en-us/9ec8025b-4763-4526-ab45-390c5d8b3b1e) 클래스를 만들고 거의 모든 VARIANT 지원 유형의 단일 및 다차원 배열을 관리 하는 단순한 작업을 수행 합니다.  
  
 `CComSafeArray`는 프로세스 간의 배열 전달을 간소화할 뿐만 아니라 상한과 하한에 대해 배열 인덱스 값을 확인하여 추가 보안을 제공합니다.  
  
 `CComSafeArray`의 하한은 모든 사용자 정의 값에서 시작할 수 있지만 C++를 통해 액세스하는 배열에서는 0을 하한으로 사용해야 합니다. Visual Basic과 같은 다른 언어에서는 다른 경계 값(예: -10~10)을 사용할 수 있습니다.  
  
 사용 하 여 [CComSafeArray::Create](#create) 만들려는 `CComSafeArray` 개체를 및 [CComSafeArray::Destroy](#destroy) 삭제할 수 있습니다.  
  
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
 [!code-cpp[NVC_ATL_Utilities #&75;](../../atl/codesnippet/cpp/ccomsafearray-class_1.cpp)]  
  
##  <a name="a-nameadda--ccomsafearrayadd"></a><a name="add"></a>CComSafeArray::Add  
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
 새 개체는 기존의 끝에 추가 됩니다. **SAFEARRAY** 개체입니다. 에 다차원 개체를 추가 **SAFEARRAY** 개체가 지원 되지 않습니다. 개체의 기존 배열을 추가할 때 두 배열 같은 형식의 요소를 포함 해야 합니다.  
  
 `bCopy` 플래그 고려할 때 형식의 요소 `BSTR` 또는 **VARIANT** 배열에 추가 됩니다. 기본값 **TRUE** 배열에 요소를 추가할 때 데이터의 새 복사본이 생성 되 보장 합니다.  
  
##  <a name="a-nameattacha--ccomsafearrayattach"></a><a name="attach"></a>CComSafeArray::Attach  
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
 연결는 **SAFEARRAY** 구조체는 `CComSafeArray` 기존 있도록 개체를 `CComSafeArray` 메서드를 사용 합니다.  
  
##  <a name="a-nameccomsafearraya--ccomsafearrayccomsafearray"></a><a name="ccomsafearray"></a>CComSafeArray::CComSafeArray  
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
 에 대 한 참조는 **SAFEARRAY** 구조 또는 `CComSafeArray` 개체입니다. 두 경우 모두 생성자는이 참조를 사용 하 여 정도의 만들어야 하는 배열의 복사본 생성 후 배열을 참조 하지 않습니다.  
  
 `psaSrc`  
 에 대 한 포인터는 **SAFEARRAY** 구조입니다. 생성자는이 주소를 사용 하 여 정도의 만들어야 하는 배열의 복사본 생성 후 배열을 참조 하지 않습니다.  
  
### <a name="remarks"></a>주의  
 
          `CComSafeArray` 개체를 만듭니다.  
  
##  <a name="a-namedtora--ccomsafearrayccomsafearray"></a><a name="dtor"></a>CComSafeArray:: ~ CComSafeArray  
 소멸자입니다.  
  
```
~CComSafeArray() throw()
```  
  
### <a name="remarks"></a>주의  
 할당 된 모든 리소스를 해제합니다.  
  
##  <a name="a-namecopyfroma--ccomsafearraycopyfrom"></a><a name="copyfrom"></a>CComSafeArray::CopyFrom  
 **SAFEARRAY** 구조체의 내용을 `CComSafeArray` 개체에 복사합니다.  
  
```
HRESULT CopyFrom(LPSAFEARRAY* ppArray);
```  
  
### <a name="parameters"></a>매개 변수  
 `ppArray`  
 에 대 한 포인터는 **SAFEARRAY** 복사 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 콘텐츠를 복사 하는이 메서드는 **SAFEARRAY** 현재 `CComSafeArray` 개체입니다. 배열의 기존 내용은 대체 됩니다.  
  
##  <a name="a-namecopytoa--ccomsafearraycopyto"></a><a name="copyto"></a>CComSafeArray::CopyTo  
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
  
##  <a name="a-namecreatea--ccomsafearraycreate"></a><a name="create"></a>CComSafeArray::Create  
 
          `CComSafeArray`을 만듭니다.  
  
```
HRESULT Create(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
HRESULT Create(ULONG ulCount = 0, LONG lLBound = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `pBound`  
 에 대 한 포인터는 **SAFEARRAYBOUND** 개체입니다.  
  
 `uDims`  
 배열의 차원 수입니다.  
  
 `ulCount`  
 배열의 요소 수입니다.  
  
 `lLBound`  
 하 한 값입니다. 즉, 배열의 첫 번째 요소의 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 A `CComSafeArray` 기존 개체를 만들 수 있습니다 **SAFEARRAYBOUND** 구조와 차원, 또는 배열 및 하 한에서 요소 수를 지정 하 여 수 있습니다. 배열이 Visual c + +에서 액세스 해야 하는 0 이어야 합니다. 다른 언어 하 한 (예를 들어 Visual Basic 배열 지원-10 ~ 10 같은 범위를 요소와) 다른 값이 허용 될 수 있습니다.  
  
##  <a name="a-namedestroya--ccomsafearraydestroy"></a><a name="destroy"></a>CComSafeArray::Destroy  
 `CComSafeArray` 개체를 제거합니다.  
  
```
HRESULT Destroy();
```  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 기존 소멸 `CComSafeArray` 개체와 모든 포함 된 데이터입니다.  
  
##  <a name="a-namedetacha--ccomsafearraydetach"></a><a name="detach"></a>CComSafeArray::Detach  
 **SAFEARRAY** 를 `CComSafeArray` 개체에서 분리합니다.  
  
```
LPSAFEARRAY Detach();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터를 반환 합니다.는 **SAFEARRAY** 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 분리는 **SAFEARRAY** 에서 개체는 `CComSafeArray` 개체입니다.  
  
##  <a name="a-namegetata--ccomsafearraygetat"></a><a name="getat"></a>CComSafeArray::GetAt  
 1차원 배열에서 단일 요소를 검색합니다.  
  
```
T& GetAt(LONG lIndex) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `lIndex`  
 반환할 배열에 있는 값의 인덱스 번호입니다.  
  
### <a name="return-value"></a>반환 값  
 필요한 배열 요소에 대 한 참조를 반환합니다.  
  
##  <a name="a-namegetcounta--ccomsafearraygetcount"></a><a name="getcount"></a>CComSafeArray::GetCount  
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
 다차원 배열을 사용 하는 경우이 메서드는 특정 차원에서 요소의 수를 반환 합니다.  
  
##  <a name="a-namegetdimensionsa--ccomsafearraygetdimensions"></a><a name="getdimensions"></a>CComSafeArray::GetDimensions  
 배열의 차원 수를 반환합니다.  
  
```
UINT GetDimensions() const;
```  
  
### <a name="return-value"></a>반환 값  
 배열의 차원 수를 반환합니다.  
  
##  <a name="a-namegetlowerbounda--ccomsafearraygetlowerbound"></a><a name="getlowerbound"></a>CComSafeArray::GetLowerBound  
 배열의 지정된 차원에 대한 하한을 반환합니다.  
  
```
LONG GetLowerBound(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `uDim`  
 하 한을 가져올 배열 차원입니다. 생략 하면 기본값은 0입니다.  
  
### <a name="return-value"></a>반환 값  
 하 한을 반환합니다.  
  
### <a name="remarks"></a>주의  
 하 한이 0 이면 해당 첫 번째 요소는 요소 번호 0는 C 스타일 배열을 나타냅니다. 오류가 발생 하면 예를 들어 잘못 된 차원 인수에이 메서드는 호출 `AtlThrow` 오류를 설명 하는 hresult입니다.  
  
##  <a name="a-namegetsafearrayptra--ccomsafearraygetsafearrayptr"></a><a name="getsafearrayptr"></a>CComSafeArray::GetSafeArrayPtr  
 `m_psa` 데이터 멤버의 주소를 반환합니다.  
  
```
LPSAFEARRAY* GetSafeArrayPtr() throw();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터를 반환 된 [CComSafeArray::m_psa](#m_psa) 데이터 멤버입니다.  
  
##  <a name="a-namegettypea--ccomsafearraygettype"></a><a name="gettype"></a>CComSafeArray::GetType  
 배열에 저장된 데이터의 형식을 반환합니다.  
  
```
VARTYPE GetType() const;
```  
  
### <a name="return-value"></a>반환 값  
 다음 형식 중 하나가 될 수 있는 배열에 저장 된 데이터 형식을 반환 합니다.  
  
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
  
##  <a name="a-namegetupperbounda--ccomsafearraygetupperbound"></a><a name="getupperbound"></a>CComSafeArray::GetUpperBound  
 배열의 모든 차원에 대한 상한을 반환합니다.  
  
```
LONG GetUpperBound(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `uDim`  
 상한 값을 가져올 배열 차원입니다. 생략 하면 기본값은 0입니다.  
  
### <a name="return-value"></a>반환 값  
 상한 값을 반환합니다. 이 값은 포함이 차원에 대 한 유효한 최대 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 오류가 발생 하면 예를 들어 잘못 된 차원 인수에이 메서드는 호출 `AtlThrow` 오류를 설명 하는 hresult입니다.  
  
##  <a name="a-nameissizablea--ccomsafearrayissizable"></a><a name="issizable"></a>CComSafeArray::IsSizable  
 `CComSafeArray` 개체의 크기를 조정할 수 있는지 테스트합니다.  
  
```
bool IsSizable() const;
```  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 경우는 `CComSafeArray` 조정할 수 있는 **false** 불가능 한 경우.  
  
##  <a name="a-namempsaa--ccomsafearraympsa"></a><a name="m_psa"></a>CComSafeArray::m_psa  
 주소를 보유는 **SAFEARRAY** 구조에 액세스 합니다.  
  
```
LPSAFEARRAY m_psa;
```  
  
##  <a name="a-namemultidimgetata--ccomsafearraymultidimgetat"></a><a name="multidimgetat"></a>CComSafeArray::MultiDimGetAt  
 다차원 배열에서 단일 요소를 검색합니다.  
  
```
HRESULT MultiDimGetAt(const LONG* alIndex, T& t);
```  
  
### <a name="parameters"></a>매개 변수  
 `alIndex`  
 배열의 각 차원에 대 한 인덱스의 벡터에 대 한 포인터입니다. 맨 왼쪽 (최상위) 차원이 `alIndex`[0] *합니다.*  
  
 *t*  
 반환 된 데이터에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="a-namemultidimsetata--ccomsafearraymultidimsetat"></a><a name="multidimsetat"></a>CComSafeArray::MultiDimSetAt  
 다차원 배열의 요소 값을 설정합니다.  
  
```
HRESULT MultiDimSetAt(const LONG* alIndex, const T& t);
```  
  
### <a name="parameters"></a>매개 변수  
 `alIndex`  
 배열의 각 차원에 대 한 인덱스의 벡터에 대 한 포인터입니다. 맨 오른쪽 (최하위) 차원이 `alIndex`[0]입니다.  
  
 *T*  
 새 요소의 값을 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 이의 다차원 버전 [CComSafeArray::SetAt](#setat)합니다.  
  
##  <a name="a-nameoperatorata--ccomsafearrayoperator-"></a><a name="operator_at"></a>CComSafeArray::operator\[\]  
 배열에서 요소를 검색합니다.  
  
```
T& operator[](long lindex) const;
T& operator[]int nindex) const;
```  
  
### <a name="parameters"></a>매개 변수  
 *nIndex 색인입니다.*  
 인덱스 번호는 배열에 있는 필수 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 적절 한 배열 요소를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 비슷한 기능을 수행 [CComSafeArray::GetAt](#getat)있지만이 연산자&1; 차원 배열 에서만 작동 합니다.  
  
##  <a name="a-nameoperatoreqa--ccomsafearrayoperator-"></a><a name="operator_eq"></a>CComSafeArray::operator =  
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
  
##  <a name="a-nameoperatorlpsafearraya--ccomsafearrayoperator-lpsafearray"></a><a name="operator_lpsafearray"></a>CComSafeArray::operator LPSAFEARRAY  
 **SAFEARRAY** 포인터에 값을 캐스팅합니다.  
  
```
operator LPSAFEARRAY() const;
```  
  
### <a name="return-value"></a>반환 값  
 **SAFEARRAY** 포인터에 값을 캐스팅합니다.  
  
##  <a name="a-nameresizea--ccomsafearrayresize"></a><a name="resize"></a>CComSafeArray::Resize  
 `CComSafeArray` 개체의 크기를 조정합니다.  
  
```
HRESULT Resize(const SAFEARRAYBOUND* pBound);
HRESULT Resize(ULONG ulCount, LONG lLBound = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `pBound`  
 에 대 한 포인터는 **SAFEARRAYBOUND** 요소 수 및 배열의 하한값에 대 한 정보를 포함 하는 구조입니다.  
  
 `ulCount`  
 요청 된 크기가 조정 된 배열에 있는 개체 수입니다.  
  
 `lLBound`  
 하 한입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 오른쪽에 있는 차원만 조정합니다. 반환 하는 배열 크기가 조정 되지 것입니다 **IsResizable** 으로 **false**합니다.  
  
##  <a name="a-namesetata--ccomsafearraysetat"></a><a name="setat"></a>CComSafeArray::SetAt  
 1차원 배열의 요소 값을 설정합니다.  
  
```
HRESULT SetAt(LONG lIndex, const T& t, BOOL bCopy = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `lIndex`  
 설정 하 고 배열 요소의 인덱스 번호입니다.  
  
 *t*  
 지정한 요소의 새 값입니다.  
  
 `bCopy`  
 데이터의 복사본을 만들어야 하는지 여부를 나타냅니다. 기본값은 **TRUE**합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 `bCopy` 플래그 고려할 때 형식의 요소 `BSTR` 또는 **VARIANT** 배열에 추가 됩니다. 기본값 **TRUE** 배열에 요소를 추가할 때 데이터의 새 복사본이 생성 되 보장 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SAFEARRAY 데이터 형식](http://msdn.microsoft.com/en-us/9ec8025b-4763-4526-ab45-390c5d8b3b1e)   
 [CComSafeArray::Create](#create)   
 [CComSafeArray::Destroy](#destroy)   
 [클래스 개요](../../atl/atl-class-overview.md)

