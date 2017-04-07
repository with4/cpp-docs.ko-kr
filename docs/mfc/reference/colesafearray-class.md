---
title: "COleSafeArray 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleSafeArray
- AFXDISP/COleSafeArray
- AFXDISP/COleSafeArray::COleSafeArray
- AFXDISP/COleSafeArray::AccessData
- AFXDISP/COleSafeArray::AllocData
- AFXDISP/COleSafeArray::AllocDescriptor
- AFXDISP/COleSafeArray::Attach
- AFXDISP/COleSafeArray::Clear
- AFXDISP/COleSafeArray::Copy
- AFXDISP/COleSafeArray::Create
- AFXDISP/COleSafeArray::CreateOneDim
- AFXDISP/COleSafeArray::Destroy
- AFXDISP/COleSafeArray::DestroyData
- AFXDISP/COleSafeArray::DestroyDescriptor
- AFXDISP/COleSafeArray::Detach
- AFXDISP/COleSafeArray::GetByteArray
- AFXDISP/COleSafeArray::GetDim
- AFXDISP/COleSafeArray::GetElement
- AFXDISP/COleSafeArray::GetElemSize
- AFXDISP/COleSafeArray::GetLBound
- AFXDISP/COleSafeArray::GetOneDimSize
- AFXDISP/COleSafeArray::GetUBound
- AFXDISP/COleSafeArray::Lock
- AFXDISP/COleSafeArray::PtrOfIndex
- AFXDISP/COleSafeArray::PutElement
- AFXDISP/COleSafeArray::Redim
- AFXDISP/COleSafeArray::ResizeOneDim
- AFXDISP/COleSafeArray::UnaccessData
- AFXDISP/COleSafeArray::Unlock
dev_langs:
- C++
helpviewer_keywords:
- COleSafeArray class
- arrays [C++], safe
- safe arrays
- ODBC, safe arrays
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 3cb6fa49e3adf7e14c34baf7feb64d12e54f2758
ms.lasthandoff: 02/24/2017

---
# <a name="colesafearray-class"></a>COleSafeArray 클래스
임의의 형식 및 차원 배열 작업용 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleSafeArray : public tagVARIANT  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleSafeArray::COleSafeArray](#colesafearray)|`COleSafeArray` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleSafeArray::AccessData](#accessdata)|배열 데이터에 대 한 포인터를 검색합니다.|  
|[COleSafeArray::AllocData](#allocdata)|배열에 대 한 메모리를 할당합니다.|  
|[COleSafeArray::AllocDescriptor](#allocdescriptor)|안전 배열 설명자에 대 한 메모리를 할당합니다.|  
|[COleSafeArray::Attach](#attach)|기존 제어할 **VARIANT** 배열을 `COleSafeArray` 개체입니다.|  
|[COleSafeArray::Clear](#clear)|모든 데이터 원본에 해제 **VARIANT**합니다.|  
|[COleSafeArray::Copy](#copy)|기존 배열의 복사본을 만듭니다.|  
|[COleSafeArray::Create](#create)|안전 배열을 만듭니다.|  
|[COleSafeArray::CreateOneDim](#createonedim)|1 차원 만듭니다 `COleSafeArray` 개체입니다.|  
|[COleSafeArray::Destroy](#destroy)|기존 배열 소멸 시킵니다.|  
|[COleSafeArray::DestroyData](#destroydata)|안전 배열에 데이터를 삭제합니다.|  
|[COleSafeArray::DestroyDescriptor](#destroydescriptor)|안전 배열의 설명자를 삭제합니다.|  
|[COleSafeArray::Detach](#detach)|분리 된 **VARIANT** 에서 배열는 `COleSafeArray` 개체 (데이터 해제 되지 것입니다).|  
|[COleSafeArray::GetByteArray](#getbytearray)|안전 배열의 내용을 복사는 [CByteArray](../../mfc/reference/cbytearray-class.md)합니다.|  
|[COleSafeArray::GetDim](#getdim)|배열의 차원 수를 반환합니다.|  
|[COleSafeArray::GetElement](#getelement)|안전 배열의 단일 요소를 검색합니다.|  
|[COleSafeArray::GetElemSize](#getelemsize)|안전 배열에 요소가 두 개를 바이트 단위로 크기를 반환 합니다.|  
|[COleSafeArray::GetLBound](#getlbound)|모든 차원 안전 배열의 하 한을 반환합니다.|  
|[COleSafeArray::GetOneDimSize](#getonedimsize)|1 차원 수의 요소를 반환 `COleSafeArray` 개체입니다.|  
|[COleSafeArray::GetUBound](#getubound)|안전 배열의 모든 차원에 대 한 상한 값을 반환합니다.|  
|[COleSafeArray::Lock](#lock)|배열의 잠금 수를 증가 하 고 배열 설명자에서 배열 데이터에 대 한 포인터를 배치 합니다.|  
|[COleSafeArray::PtrOfIndex](#ptrofindex)|인덱싱된 요소에 대 한 포인터를 반환합니다.|  
|[COleSafeArray::PutElement](#putelement)|단일 요소를 배열에 할당합니다.|  
|[COleSafeArray::Redim](#redim)|안전 배열의 최하위 오른쪽에 있는 범위를 변경합니다.|  
|[COleSafeArray::ResizeOneDim](#resizeonedim)|1 차원에 있는 요소의 수를 변경 `COleSafeArray` 개체입니다.|  
|[COleSafeArray::UnaccessData](#unaccessdata)|감소 잠금을 배열 계산과 검색 포인터를 무효화 `AccessData`합니다.|  
|[COleSafeArray::Unlock](#unlock)|잠금 횟수를 감소 배열 해제 하거나 크기를 조정할 수 있습니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[COleSafeArray::operator LPCVARIANT](#operator_lpcvariant)|기본 액세스 **VARIANT** 의 구조는 `COleSafeArray` 개체입니다.|  
|[COleSafeArray::operator LPVARIANT](#operator_lpvariant)|기본 액세스 **VARIANT** 의 구조는 `COleSafeArray` 개체입니다.|  
|[COleSafeArray::operator =](#operator_eq)|에 값을 복사 하는 `COleSafeArray` 개체 ( **SAFEARRAY**, **VARIANT**, `COleVariant`, 또는 `COleSafeArray` 배열)입니다.|  
|[COleSafeArray::operator = =](#operator_eq_eq)|Variant 두 배열을 비교 ( **SAFEARRAY**, **VARIANT**, `COleVariant`, 또는 `COleSafeArray` 배열)입니다.|  
|[COleSafeArray::operator&lt;&lt;](#operator_lt_lt)|내용을 출력 한 `COleSafeArray` 덤프 컨텍스트 개체입니다.|  
  
## <a name="remarks"></a>주의  
 `COleSafeArray`OLE에서 파생 되며 **VARIANT** 구조입니다. OLE **SAFEARRAY** 멤버 함수를 통해 사용할 수는 `COleSafeArray`도, 바이트의&1; 차원 배열을 위해 특별히 설계 된 멤버 함수의 집합으로 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `tagVARIANT`  
  
 `COleSafeArray`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h  
  
##  <a name="accessdata"></a>COleSafeArray::AccessData  
 배열 데이터에 대 한 포인터를 검색합니다.  
  
```  
void AccessData(void** ppvData);
```  
  
### <a name="parameters"></a>매개 변수  
 `ppvData`  
 배열 데이터에 대 한 포인터에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCOleContainer #&26;](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]  
  
##  <a name="allocdata"></a>COleSafeArray::AllocData  
 안전 배열에 대 한 메모리를 할당합니다.  
  
```  
void AllocData();
```  
  
### <a name="remarks"></a>주의  
 함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md)합니다.  
  
##  <a name="allocdescriptor"></a>COleSafeArray::AllocDescriptor  
 안전 배열의 설명자에 대 한 메모리를 할당합니다.  
  
```  
void AllocDescriptor(DWORD dwDims);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwDims`  
 안전 배열의 차원 수입니다.  
  
### <a name="remarks"></a>주의  
 함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md)합니다.  
  
##  <a name="attach"></a>COleSafeArray::Attach  
 기존에 있는 데이터의 제어할 **VARIANT** 배열을 `COleSafeArray` 개체입니다.  
  
```  
void Attach(VARIANT& varSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 *varSrc*  
 A **VARIANT** 개체입니다. *varSrc* 매개 변수는 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4)**VT_ARRAY**합니다.  
  
### <a name="remarks"></a>주의  
 소스 **VARIANT**의 유형이으로 설정 되어 `VT_EMPTY`합니다. 있는 경우이 함수는 현재 배열 데이터를 지웁니다.  
  
### <a name="example"></a>예제  
  예를 참조 [COleSafeArray::AccessData](#accessdata)합니다.  
  
##  <a name="clear"></a>COleSafeArray::Clear  
 안전 배열을 지웁니다.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>주의  
 함수는 안전 배열 설정 하 여 지웁니다는 `VARTYPE` 개체의 `VT_EMPTY`합니다. 현재 내용이 릴리스되고 배열 해제 됩니다.  
  
##  <a name="colesafearray"></a>COleSafeArray::COleSafeArray  
 `COleSafeArray` 개체를 생성합니다.  
  
```  
COleSafeArray();

 
COleSafeArray(
    const SAFEARRAY& saSrc,
    VARTYPE vtSrc);

 
COleSafeArray(
    LPCSAFEARRAY pSrc,
    VARTYPE vtSrc);  
  
COleSafeArray(const COleSafeArray& saSrc);  
COleSafeArray(const VARIANT& varSrc);  
  COleSafeArray(LPCVARIANT pSrc);  
COleSafeArray(const COleVariant& varSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 `saSrc`  
 기존 `COleSafeArray` 개체 또는 **SAFEARRAY** 새 개체로 복사할 `COleSafeArray` 개체입니다.  
  
 `vtSrc`  
 **VARTYPE** 새 `COleSafeArray` 개체입니다.  
  
 `psaSrc`  
 에 대 한 포인터는 **SAFEARRAY** 새 개체로 복사할 `COleSafeArray` 개체입니다.  
  
 *varSrc*  
 기존 **VARIANT** 또는 `COleVariant` 새 복사할 개체 `COleSafeArray` 개체입니다.  
  
 `pSrc`  
 에 대 한 포인터는 **VARIANT** 새 복사할 개체 `COleSafeArray` 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 생성자의 모든 새로 만들기 `COleSafeArray` 개체입니다. 매개 변수가 없거나, 빈 경우 `COleSafeArray` 개체가 생성 됩니다 ( `VT_EMPTY`). 경우는 `COleSafeArray` 에서 다른 복사 됩니다 갖는 배열 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) 암시적으로 알려져 (한 `COleSafeArray`, `COleVariant`, 또는 **VARIANT**), **VARTYPE** 원본 배열 보관 되 고 지정할 필요가 없습니다. 경우는 `COleSafeArray` 에서 다른 복사 갖는 배열 **VARTYPE** 알 수 없는 ( **SAFEARRAY**), **VARTYPE** 에 지정 해야는 `vtSrc` 매개 변수입니다.  
  
 함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md)합니다.  
  
##  <a name="copy"></a>COleSafeArray::Copy  
 기존 안전 배열의 복사본을 만듭니다.  
  
```  
void Copy(LPSAFEARRAY* ppsa);
```  
  
### <a name="parameters"></a>매개 변수  
 *ppsa*  
 새 배열 설명자를 반환 하는 위치에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md)합니다.  
  
##  <a name="create"></a>COleSafeArray::Create  
 할당 하 고 배열에 대 한 데이터를 초기화 합니다.  
  
```  
void Create(
    VARTYPE vtSrc,  
    DWORD dwDims,  
    DWORD* rgElements);

 
void Create(
    VARTYPE vtSrc,  
    DWORD dwDims,  
    SAFEARRAYBOUND* rgsabounds);
```  
  
### <a name="parameters"></a>매개 변수  
 `vtSrc`  
 배열의 기본 형식 (즉,는 **VARTYPE** 배열의 각 요소). **VARTYPE** variant 형식의 하위 집합으로 제한 됩니다. 모두는 **VT_ARRAY** 또는 **VT_BYREF** 플래그를 설정할 수 있습니다. `VT_EMPTY`및 **VT_NULL** 없는 배열에 대 한 유효한 기본 형식입니다. 다른 모든 형식은 올바릅니다.  
  
 `dwDims`  
 배열의 차원 수 있습니다. 이를 만든 후 변경할 수 있습니다 [Redim](#redim)합니다.  
  
 *rgElements*  
 배열의 각 차원에 대 한 요소 수의 배열에 대 한 포인터입니다.  
  
 *rgsabounds*  
 벡터의 범위 (각 차원에 대해 하나)에 대 한 포인터 배열에 할당할 수 있습니다.  
  
### <a name="remarks"></a>주의  
 필요한 경우이 함수는 현재 배열의 데이터를 지웁니다. 함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCOleContainer #&27;](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]  
  
##  <a name="createonedim"></a>COleSafeArray::CreateOneDim  
 에서는 새&1; 차원 `COleSafeArray` 개체입니다.  
  
```  
void CreateOneDim(
    VARTYPE vtSrc,  
    DWORD dwElements,  
    const void* pvSrcData = NULL,  
    long nLBound = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `vtSrc`  
 배열의 기본 형식 (즉,는 **VARTYPE** 배열의 각 요소).  
  
 `dwElements`  
 배열의 요소 수입니다. 이를 만든 후 변경할 수 있습니다 [ResizeOneDim](#resizeonedim)합니다.  
  
 `pvSrcData`  
 배열에 복사 하는 데이터에 대 한 포인터입니다.  
  
 *nLBound*  
 배열의 하 한입니다.  
  
### <a name="remarks"></a>주의  
 할당 하 고 하는 경우 지정된 된 데이터를 복사 하 여 배열에 대 한 데이터를 초기화 하는 함수 포인터 `pvSrcData` 없는 **NULL**합니다.  
  
 함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCOleContainer #&28;](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]  
  
##  <a name="destroy"></a>COleSafeArray::Destroy  
 기존 배열 설명자와 배열에 있는 모든 데이터를 삭제합니다.  
  
```  
void Destroy();
```  
  
### <a name="remarks"></a>주의  
 개체의 배열에 저장 되며, 각 개체 해제 됩니다. 함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md)합니다.  
  
##  <a name="destroydata"></a>COleSafeArray::DestroyData  
 안전 배열에 있는 모든 데이터를 삭제합니다.  
  
```  
void DestroyData();
```  
  
### <a name="remarks"></a>주의  
 개체의 배열에 저장 되며, 각 개체 해제 됩니다. 함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md)합니다.  
  
##  <a name="destroydescriptor"></a>COleSafeArray::DestroyDescriptor  
 안전 배열의 설명자를 삭제합니다.  
  
```  
void DestroyDescriptor();
```  
  
### <a name="remarks"></a>주의  
 함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md)합니다.  
  
##  <a name="detach"></a>COleSafeArray::Detach  
 분리 된 **VARIANT** 에서 데이터는 `COleSafeArray` 개체입니다.  
  
```  
VARIANT Detach();
```  
  
### <a name="return-value"></a>반환 값  
 내부 **VARIANT** 값은 `COleSafeArray` 개체입니다.  
  
### <a name="remarks"></a>주의  
 설정 하 여 안전 배열에 있는 데이터를 분리 하는 함수는 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) 개체의 `VT_EMPTY`합니다. Windows 함수를 호출 하 여 배열 해제 해야 하는 호출자의 [VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835)합니다.  
  
 함수에서 오류를 throw 한 [COleException](../../mfc/reference/coleexception-class.md)합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [COleSafeArray::PutElement](#putelement)합니다.  
  
##  <a name="getbytearray"></a>COleSafeArray::GetByteArray  
 안전 배열의 내용을 복사는 `CByteArray`합니다.  
  
```  
void GetByteArray(CByteArray& bytes);
```  
  
### <a name="parameters"></a>매개 변수  
 `bytes`  
 에 대 한 참조는 [CByteArray](../../mfc/reference/cbytearray-class.md) 개체입니다.  
  
##  <a name="getdim"></a>COleSafeArray::GetDim  
 차원 수를 반환 합니다.는 `COleSafeArray` 개체입니다.  
  
```  
DWORD GetDim();
```  
  
### <a name="return-value"></a>반환 값  
 안전 배열의 차원 수를 지정 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCOleContainer #&27;](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]  
  
##  <a name="getelement"></a>COleSafeArray::GetElement  
 안전 배열의 단일 요소를 검색합니다.  
  
```  
void GetElement(
    long* rgIndices,  
    void* pvData);
```  
  
### <a name="parameters"></a>매개 변수  
 `rgIndices`  
 각 배열 차원의 인덱스 배열에 대한 포인터입니다.  
  
 `pvData`  
 배열의 요소를 배치 하는 위치에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 자동으로 windows 함수 호출 `SafeArrayLock` 및 `SafeArrayUnlock` 전과 후의 요소를 검색 합니다. 문자열, 개체 또는 variant 데이터 요소가 있으면 올바른 방법으로 요소를 복사 하는 함수입니다. 매개 변수 `pvData` 가리켜야 하는 큰 요소를 포함 하도록 충분 한 버퍼입니다.  
  
 함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCOleContainer #&29;](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]  
  
##  <a name="getelemsize"></a>COleSafeArray::GetElemSize  
 에 있는 요소의 크기를 검색 한 `COleSafeArray` 개체입니다.  
  
```  
DWORD GetElemSize();
```  
  
### <a name="return-value"></a>반환 값  
 안전 배열 요소를 바이트 단위로 크기입니다.  
  
##  <a name="getlbound"></a>COleSafeArray::GetLBound  
 모든 차원에 대 한 하 한을 반환 된 `COleSafeArray` 개체입니다.  
  
```  
void GetLBound(
    DWORD dwDim,  
    long* pLBound);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwDim`  
 하 한을 가져올 배열 차원입니다.  
  
 *pLBound*  
 하 한을 반환 하는 위치에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 함수에서 오류를 throw 한 [COleException](../../mfc/reference/coleexception-class.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCOleContainer #&30;](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]  
  
##  <a name="getonedimsize"></a>COleSafeArray::GetOneDimSize  
 1 차원 수의 요소를 반환 `COleSafeArray` 개체입니다.  
  
```  
DWORD GetOneDimSize();
```  
  
### <a name="return-value"></a>반환 값  
 안전&1; 차원 배열에 있는 요소의 수입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [COleSafeArray::CreateOneDim](#createonedim)합니다.  
  
##  <a name="getubound"></a>COleSafeArray::GetUBound  
 안전 배열의 모든 차원에 대 한 상한 값을 반환합니다.  
  
```  
void GetUBound(
    DWORD dwDim,  
    long* pUBound);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwDim`  
 상한 값을 가져올 배열 차원입니다.  
  
 *pUBound*  
 상한 값을 반환 하는 위치에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 함수에서 오류를 throw 한 [COleException](../../mfc/reference/coleexception-class.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCOleContainer #&31;](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]  
  
##  <a name="lock"></a>COleSafeArray::Lock  
 배열 및 배열 설명자에서 배열 데이터에 대 한 포인터 위치의 잠금 수를 증가 시킵니다.  
  
```  
void Lock();
```  
  
### <a name="remarks"></a>주의  
 오류 시 발생 한 [COleException](../../mfc/reference/coleexception-class.md)합니다.  
  
 배열 설명자에 대 한 포인터가 유효 기간 `Unlock` 호출 됩니다. 에 대 한 호출이 `Lock` 중첩 될 수 있습니다; 동일한 수에 대 한 호출의 `Unlock` 필요 합니다.  
  
 잠겨 있는 동안에 배열을 삭제할 수 없습니다.  
  
##  <a name="operator_lpcvariant"></a>COleSafeArray::operator LPCVARIANT  
 기본 액세스 하려면이 캐스팅 연산자 호출 **VARIANT** 이 대 한 구조 `COleSafeArray` 개체입니다.  
  
```  
operator LPCVARIANT() const;  
```  
  
##  <a name="operator_lpvariant"></a>COleSafeArray::operator LPVARIANT  
 기본 액세스 하려면이 캐스팅 연산자 호출 **VARIANT** 이 대 한 구조 `COleSafeArray` 개체입니다.  
  
```  
operator LPVARIANT();
```   
  
### <a name="remarks"></a>주의  
 값을 변경의 **VARIANT** 이 함수에 의해 반환 된 포인터에 액세스 하는 구조는이 값을 변경 합니다 `COleSafeArray` 개체입니다.  
  
##  <a name="operator_eq"></a>COleSafeArray::operator =  
 이러한 오버 로드 된 대입 연산자 복사할 원본 값이 `COleSafeArray` 개체입니다.  
  
```  
COleSafeArray& operator=(const COleSafeArray& saSrc);  
COleSafeArray& operator=(const VARIANT& varSrc);  
  COleSafeArray& operator=(LPCVARIANT pSrc);  
COleSafeArray& operator=(const COleVariant& varSrc);
```  
  
### <a name="remarks"></a>주의  
 각 연산자에 대 한 간략 한 설명은 다음과 같습니다.  
  
- **operator = (** *saSrc* **)** 기존 복사 `COleSafeArray` 개체로이 개체입니다.  
  
- **operator = (** *varSrc***)** 기존 복사 **VARIANT** 또는 `COleVariant` 배열에이 개체입니다.  
  
- **연산자 = (** `pSrc` **)** 복사본은 **VARIANT** 배열 개체에서 액세스할 `pSrc` 이 개체에 있습니다.  
  
##  <a name="operator_eq_eq"></a>COleSafeArray::operator = =  
 이 연산자는 두 배열을 비교 ( **SAFEARRAY**, **VARIANT**, `COleVariant`, 또는 `COleSafeArray` 배열); 그렇지 않으면 0 경우 0이 아닌 반환 합니다.  
  
```  
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;  
   
BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;  
   
BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;  ```  
  
### Remarks  
 Two arrays are equal if they have an equal number of dimensions, equal size in each dimension, and equal element values.  
  
##  <a name="operator_lt_lt"></a>  COleSafeArray::operator &lt;&lt;  
 The `COleSafeArray` insertion (<<) operator supports diagnostic dumping and storing of a `COleSafeArray` object to an archive.  
  
```  
/ / AFXAPI CDumpContext 연산자<( CDumpContext& dc, cdumpcontext&=""></( CDumpContext& dc,>  
    COleSafeArray / saSrc);
```  
  
##  <a name="ptrofindex"></a>  COleSafeArray::PtrOfIndex  
 Returns a pointer to the element specified by the index values.  
  
```  
PtrOfIndex void (긴* rgIndices void** ppvData);
```  
  
### Parameters  
 `rgIndices`  
 An array of index values that identify an element of the array. All indexes for the element must be specified.  
  
 `ppvData`  
 On return, pointer to the element identified by the values in `rgIndices`.  
  
##  <a name="putelement"></a>  COleSafeArray::PutElement  
 Assigns a single element into the array.  
  
```  
PutElement void (긴* rgIndices void* pvData);
```  
  
### Parameters  
 `rgIndices`  
 Pointer to an array of indexes for each dimension of the array.  
  
 `pvData`  
 Pointer to the data to assign to the array. **VT_DISPATCH**, **VT_UNKNOWN**, and `VT_BSTR` variant types are pointers and do not require another level of indirection.  
  
### Remarks  
 This function automatically calls the Windows functions [SafeArrayLock](https://msdn.microsoft.com/library/windows/desktop/ms221492.aspx) and [SafeArrayUnlock](https://msdn.microsoft.com/library/windows/desktop/ms221246.aspx) before and after assigning the element. If the data element is a string, object, or variant, the function copies it correctly, and if the existing element is a string, object, or variant, it is cleared correctly.  
  
 Note that you can have multiple locks on an array, so you can put elements into an array while the array is locked by other operations.  
  
 On error, the function throws a [CMemoryException](../../mfc/reference/cmemoryexception-class.md) or [COleException](../../mfc/reference/coleexception-class.md).  
  
### Example  
 [!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]  
  
##  <a name="redim"></a>  COleSafeArray::Redim  
 Changes the least significant (rightmost) bound of a safe array.  
  
```  
void Redim (SAFEARRAYBOUND * psaboundNew);
```  
  
### Parameters  
 *psaboundNew*  
 Pointer to a new safe array bound structure containing the new array bound. Only the least significant dimension of an array may be changed.  
  
### Remarks  
 On error, the function throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="resizeonedim"></a>  COleSafeArray::ResizeOneDim  
 Changes the number of elements in a one-dimensional `COleSafeArray` object.  
  
```  
void ResizeOneDim (DWORD dwElements);
```  
  
### Parameters  
 `dwElements`  
 Number of elements in the one-dimensional safe array.  
  
### Remarks  
 On error, the function throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
### Example  
  See the example for [COleSafeArray::CreateOneDim](#createonedim).  
  
##  <a name="unaccessdata"></a>  COleSafeArray::UnaccessData  
 Decrements the lock count of an array and invalidates the pointer retrieved by `AccessData`.  
  
```  
void UnaccessData();
```  
  
### Remarks  
 On error, the function throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
### Example  
  See the example for [COleSafeArray::AccessData](#accessdata).  
  
##  <a name="unlock"></a>  COleSafeArray::Unlock  
 Decrements the lock count of an array so it can be freed or resized.  
  
```  
void Unlock();
```  
  
### Remarks  
 This function is called after access to the data in an array is finished. On error, it throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
## See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [COleVariant Class](../../mfc/reference/colevariant-class.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)

