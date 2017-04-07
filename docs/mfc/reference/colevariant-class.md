---
title: "COleVariant 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleVariant
- AFXDISP/COleVariant
- AFXDISP/COleVariant::COleVariant
- AFXDISP/COleVariant::Attach
- AFXDISP/COleVariant::ChangeType
- AFXDISP/COleVariant::Clear
- AFXDISP/COleVariant::Detach
- AFXDISP/COleVariant::GetByteArrayFromVariantArray
- AFXDISP/COleVariant::SetString
dev_langs:
- C++
helpviewer_keywords:
- Automation, parameter types
- COleVariant class
- VARIANT data type
ms.assetid: e1b5cd4a-b066-4b9b-b48b-6215ed52d998
caps.latest.revision: 24
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
ms.openlocfilehash: 753566adc5fc8e48ad31da52c2bb3f04c9e21727
ms.lasthandoff: 02/24/2017

---
# <a name="colevariant-class"></a>COleVariant 클래스
캡슐화 된 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) 데이터 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleVariant : public tagVARIANT  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleVariant::COleVariant](#colevariant)|`COleVariant` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleVariant::Attach](#attach)|연결 된 **VARIANT** 에 `COleVariant`합니다.|  
|[COleVariant::ChangeType](#changetype)|이 작업의 variant 형식을 변경 하는 `COleVariant` 개체입니다.|  
|[COleVariant::Clear](#clear)|이 지우고 `COleVariant` 개체입니다.|  
|[COleVariant::Detach](#detach)|분리는 **VARIANT** 에서 `COleVariant` 하 고 반환 된 **VARIANT**합니다.|  
|[COleVariant::GetByteArrayFromVariantArray](#getbytearrayfromvariantarray)|기존 variant 배열에서 바이트 배열을 검색합니다.|  
|[COleVariant::SetString](#setstring)|특정 형식에 일반적으로 ANSI 문자열을 설정 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[COleVariant::operator LPCVARIANT](#operator_lpcvariant)|변환 된 `COleVariant` 값에 `LPCVARIANT`합니다.|  
|[COleVariant::operator LPVARIANT](#operator_lpvariant)|변환 된 `COleVariant` 개체는 `LPVARIANT`합니다.|  
|[COleVariant::operator =](#operator_eq)|복사본을 `COleVariant` 값입니다.|  
|[COleVariant::operator = =](#operator_eq_eq)|두 `COleVariant` 값입니다.|  
|[COleVariant::operator &lt; &lt;,&gt;&gt;](#operator_lt_lt__gt_gt)|출력을 `COleVariant` 값을 `CArchive` 또는 `CDumpContext` 입력 하 고는 `COleVariant` 에서 개체 `CArchive`합니다.|  
  
## <a name="remarks"></a>주의  
 이 데이터 형식은 OLE 자동화에 사용 됩니다. 구체적으로 [면 DISPPARAMS](http://msdn.microsoft.com/en-us/a16e5a21-766e-4287-b039-13429aa78f8b) 구조에 대 한 포인터의 배열에 포함 된 **VARIANT** 구조입니다. A **면 DISPPARAMS** 구조는 매개 변수를 전달 하는 데 사용 됩니다 [idispatch:: Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d)합니다.  
  
> [!NOTE]
>  이 클래스에서 파생 되는 **VARIANT** 구조입니다. 즉, 전달할 수 있습니다는 `COleVariant` 에 대 한 호출 하는 매개 변수에서는 **VARIANT** 하의 데이터 멤버는 **VARIANT** 구조 액세스할 수 있는 데이터의 멤버인 `COleVariant`합니다.  
  
 두 개의 관련 MFC 클래스 [COleCurrency](../../mfc/reference/colecurrency-class.md) 및 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) variant 데이터 형식을 캡슐화 **통화** ( `VT_CY`) 및 **날짜** ( `VT_DATE`). `COleVariant` 클래스 DAO 클래스에서 광범위 하 게 사용 됩니다; 예를 들어이 클래스의 일반적인 사용에 대 한 이러한 클래스를 참조 하십시오 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) 및 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)합니다.  
  
 자세한 내용은 참조는 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118), [통화](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e), [면 DISPPARAMS](http://msdn.microsoft.com/en-us/a16e5a21-766e-4287-b039-13429aa78f8b), 및 [idispatch:: Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d) 항목에는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 대 한 자세한 내용은 `COleVariant` 클래스 및 해당 OLE 자동화 사용 문서에 "전달 매개 변수에서 OLE 자동화"를 참조 하십시오. [자동화](../../mfc/automation.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `tagVARIANT`  
  
 `COleVariant`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h  
  
##  <a name="attach"></a>COleVariant::Attach  
 연결 하려면이 함수를 호출 하는 지정 된 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) 개체를 현재 `COleVariant` 개체입니다.  
  
```  
void Attach(VARIANT& varSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 *varSrc*  
 기존 **VARIANT** 개체에 현재 연결 수 `COleVariant` 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 설정의 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) 의 *varSrc* 를 `VT_EMPTY`합니다.  
  
 자세한 내용은 참조는 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) 및 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) 항목에는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="colevariant"></a>COleVariant::COleVariant  
 `COleVariant` 개체를 생성합니다.  
  
```  
COleVariant(); 
COleVariant(const VARIANT& varSrc); 
COleVariant(const COleVariant& varSrc); 
COleVariant(LPCVARIANT pSrc); 
COleVariant(LPCTSTR lpszSrc); 
COleVariant(LPCTSTR lpszSrc, VARTYPE vtSrc); 
COleVariant(CString& strSrc); 
COleVariant(BYTE nSrc); 
COleVariant(short nSrc, VARTYPE vtSrc = VT_I2); 
COleVariant(long lSrc,VARTYPE vtSrc = VT_I4); 
COleVariant(const COleCurrency& curSrc); 
COleVariant(float fltSrc); 
COleVariant(double dblSrc); 
COleVariant(const COleDateTime& timeSrc); 
COleVariant(const CByteArray& arrSrc); 
COleVariant(const CLongBinary& lbSrc); 
COleVariant(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>매개 변수  
 *varSrc*  
 기존 `COleVariant` 또는 **VARIANT** 새 복사할 개체 `COleVariant` 개체입니다.  
  
 `pSrc`  
 에 대 한 포인터는 **VARIANT** 새 복사 될 개체 `COleVariant` 개체입니다.  
  
 `lpszSrc`  
 Null로 끝나는 문자열을 복사할 새 `COleVariant` 개체입니다.  
  
 `vtSrc`  
 `VARTYPE` 새 `COleVariant` 개체입니다.  
  
 `strSrc`  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 새 복사할 개체 `COleVariant` 개체입니다.  
  
 `nSrc`, `lSrc`  
 새 `COleVariant` 개체에 복사될 숫자 값입니다.  
  
 `vtSrc`  
 `VARTYPE` 새 `COleVariant` 개체입니다.  
  
 `curSrc`  
 A [COleCurrency](../../mfc/reference/colecurrency-class.md) 새 복사할 개체 `COleVariant` 개체입니다.  
  
 `fltSrc`, `dblSrc`  
 새 `COleVariant` 개체에 복사될 숫자 값입니다.  
  
 `timeSrc`  
 A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 새 복사할 개체 `COleVariant` 개체입니다.  
  
 `arrSrc`  
 A [CByteArray](../../mfc/reference/cbytearray-class.md) 새 복사할 개체 `COleVariant` 개체입니다.  
  
 `lbSrc`  
 A [CLongBinary](../../mfc/reference/clongbinary-class.md) 새 복사할 개체 `COleVariant` 개체입니다.  
  
 `pidl`  
 에 대 한 포인터는 [ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321) 구조를 복사할 새 `COleVariant` 개체입니다.  
  
### <a name="remarks"></a>주의  
 이러한 모든 생성자는 새로 만들기 `COleVariant` 개체를 지정된 된 값으로 초기화 합니다. 각각이 생성자의 간략 한 설명은 다음과 같습니다.  
  
- **COleVariant ()** 빈 만듭니다 `COleVariant` 개체 `VT_EMPTY`합니다.  
  
- **COleVariant (** *varSrc* **)** 기존 복사 **VARIANT** 또는 `COleVariant` 개체입니다. 변형 형식이 유지됩니다.  
  
- **COleVariant (** `pSrc` **)** 기존 복사 **VARIANT** 또는 `COleVariant` 개체입니다. 변형 형식이 유지됩니다.  
  
- **COleVariant (** `lpszSrc` **)** 새 개체에 문자열을 복사 `VT_BSTR` (유니코드).  
  
- **COleVariant (** `lpszSrc` **,** `vtSrc` **)** 새 개체에 문자열을 복사 합니다. 매개 변수 `vtSrc` 해야 `VT_BSTR` (유니코드) 또는 `VT_BSTRT` (ANSI)입니다.  
  
- **COleVariant (** `strSrc` **)** 새 개체에 문자열을 복사 **VT_BSTR** (유니코드).  
  
- **COleVariant (** `nSrc` **)** 새 개체에는 8 비트 정수를 복사 `VT_UI1`합니다.  
  
- **COleVariant (** `nSrc` **,** `vtSrc` **)** 새 개체에는 16 비트 정수 또는 부울 값을 복사 합니다. 매개 변수 `vtSrc` 해야 `VT_I2` 또는 `VT_BOOL`합니다.  
  
- **COleVariant (** `lSrc` **,** `vtSrc` **)** 복사 하는 32 비트 정수 (또는 `SCODE` 값) 새 개체에 있습니다. 매개 변수 `vtSrc` 해야 `VT_I4`, `VT_ERROR`, 또는 `VT_BOOL`합니다.  
  
- **COleVariant (** `curSrc` **)** 복사본을 **COleCurrency** 새 개체에 값 `VT_CY`합니다.  
  
- **COleVariant (** `fltSrc` **)** 32 비트 부동 소수점 값이 새 개체에 복사 `VT_R4`합니다.  
  
- **COleVariant (** `dblSrc` **)** 64 비트 부동 소수점 값이 새 개체에 복사 `VT_R8`합니다.  
  
- **COleVariant (** `timeSrc` **)** 복사본을 `COleDateTime` 새 개체에 값 `VT_DATE`합니다.  
  
- **COleVariant (** `arrSrc` **)** 복사본을 `CByteArray` 개체로 새 개체 `VT_EMPTY`합니다.  
  
- **COleVariant (** `lbSrc` **)** 복사본을 `CLongBinary` 개체로 새 개체 `VT_EMPTY`합니다.  
  
 대 한 자세한 내용은 `SCODE`, 참조 [COM 오류 코드 구조](http://msdn.microsoft.com/library/windows/desktop/ms690088) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="changetype"></a>COleVariant::ChangeType  
 이 variant 값의 형식을 변환 `COleVariant` 개체입니다.  
  
```  
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `vartype`  
 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) 이 `COleVariant` 개체입니다.  
  
 `pSrc`  
 에 대 한 포인터는 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) 변환 될 개체입니다. 이 값이 **NULL**,이 `COleVariant` 개체 변환에는 원본으로 사용 됩니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조는 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118), [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4), 및 [VariantChangeType](http://msdn.microsoft.com/en-us/48a51e32-95d7-4eeb-8106-f5043ffa2fd1) 항목에는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="clear"></a>COleVariant::Clear  
 지웁니다는 **VARIANT**합니다.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>주의  
 이 설정의 **VARTYPE** 하기 위해이 개체에 대 한 `VT_EMPTY`합니다. `COleVariant` 소멸자가이 함수를 호출 합니다.  
  
 자세한 내용은 참조는 `VARIANT`, `VARTYPE`, 및 `VariantClear` 항목에는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="detach"></a>COleVariant::Detach  
 기본 분리 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) 개체에서이 `COleVariant` 개체입니다.  
  
```  
VARIANT Detach();
```  
  
### <a name="remarks"></a>주의  
 이 함수는 설정의 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) 이 `COleVariant` 개체를 `VT_EMPTY`합니다.  
  
> [!NOTE]
>  호출한 후 **분리**를 호출 해야 하는 호출자의 **VariantClear** 결과에 **VARIANT** 구조입니다.  
  
 자세한 내용은 참조는 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118), [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4), 및 [VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835) 항목에는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getbytearrayfromvariantarray"></a>COleVariant::GetByteArrayFromVariantArray  
 기존 variant 배열에서 바이트 배열을 검색합니다  
  
```  
void GetByteArrayFromVariantArray(CByteArray& bytes);
```  
  
### <a name="parameters"></a>매개 변수  
 `bytes`  
 기존에 대 한 참조 [CByteArray](../../mfc/reference/cbytearray-class.md) 개체입니다.  
  
##  <a name="operator_lpcvariant"></a>COleVariant::operator LPCVARIANT  
 이 캐스팅 연산자를 반환는 `VARIANT` 값이 복사 됩니다 구조 `COleVariant` 개체입니다.  
  
```  
operator LPCVARIANT() const; 
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="operator_lpvariant"></a>COleVariant::operator LPVARIANT  
 기본 액세스 하려면이 캐스팅 연산자 호출 `VARIANT` 이 대 한 구조 `COleVariant` 개체입니다.  
  
```  
operator LPVARIANT();
```   
  
### <a name="remarks"></a>주의  
  
> [!CAUTION]
>  값을 변경의 **VARIANT** 이 함수에 의해 반환 된 포인터에 액세스 하는 구조는이 값을 변경 합니다 `COleVariant` 개체입니다.  
  
##  <a name="operator_eq"></a>COleVariant::operator =  
 이러한 오버 로드 된 대입 연산자 복사할 원본 값이 `COleVariant` 개체입니다.  
  
```  
const COleVariant& operator=(const VARIANT& varSrc); 
const COleVariant& operator=(LPCVARIANT pSrc); 
const COleVariant& operator=(const COleVariant& varSrc); 
const COleVariant& operator=(const LPCTSTR lpszSrc);
const COleVariant& operator=(const CString& strSrc); 
const COleVariant& operator=(BYTE nSrc); 
const COleVariant& operator=(short nSrc); 
const COleVariant& operator=(long lSrc); 
const COleVariant& operator=(const COleCurrency& curSrc); 
const COleVariant& operator=(float fltSrc); 
const COleVariant& operator=(double dblSrc); 
const COleVariant& operator=(const COleDateTime& dateSrc); 
const COleVariant& operator=(const CByteArray& arrSrc); 
const COleVariant& operator=(const CLongBinary& lbSrc);
```  
  
### <a name="remarks"></a>주의  
 각 연산자에 대 한 간략 한 설명은 다음과 같습니다.  
  
- **operator = (** *varSrc***)** 기존 복사 **VARIANT** 또는 `COleVariant` 개체로이 개체입니다.  
  
- **operator = (** `pSrc` **)** 복사본은 **VARIANT** 액세스 한 개체가 `pSrc` 이 개체에 있습니다.  
  
- **연산자 = (** `lpszSrc` **)** 이 개체에 null로 끝나는 문자열을 복사 하 고 설정 하는 **VARTYPE** 를 `VT_BSTR`합니다.  
  
- **연산자 = (** `strSrc` **)** 복사본을 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체를이 개체 및 설정에는 **VARTYPE** 를 `VT_BSTR`합니다.  
  
- **operator = (** `nSrc` **)** 8 또는 16 비트 정수 값이이 개체에 복사 합니다. 경우 `nSrc` 는 8 비트 값의 **VARTYPE** 로 설정 되어이 `VT_UI1`합니다. 경우 `nSrc` 는 16 비트 값 및 **VARTYPE** 이 `VT_BOOL`, 유지 하 고, 그렇지 않으면로 설정 된 `VT_I2`합니다.  
  
- **operator = (** `lSrc` **)** 32 비트 정수 값이이 개체에 복사 합니다. 하는 경우는 **VARTYPE** 이 `VT_ERROR`, 유지 하 고, 그렇지 않으면로 설정 된 `VT_I4`합니다.  
  
- **연산자 = (** `curSrc` **)** 복사본을 [COleCurrency](../../mfc/reference/colecurrency-class.md) 개체를이 개체 및 설정에는 **VARTYPE** 를 `VT_CY`합니다.  
  
- **연산자 = (** `fltSrc` **)** 이 개체에는 32 비트 부동 소수점 값을 복사 하 고 설정 하는 **VARTYPE** 를 `VT_R4`합니다.  
  
- **연산자 = (** `dblSrc` **)** 이 개체에는 64 비트 부동 소수점 값을 복사 하 고 설정 하는 **VARTYPE** 를 `VT_R8`합니다.  
  
- **연산자 = (** `dateSrc` **)** 복사본을 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체를이 개체 및 설정에는 **VARTYPE** 를 `VT_DATE`합니다.  
  
- **operator = (** `arrSrc` **)** 복사본은 [CByteArray](../../mfc/reference/cbytearray-class.md) 여기에 개체 `COleVariant` 개체입니다.  
  
- **operator = (** `lbSrc` **)** 복사본은 [CLongBinary](../../mfc/reference/clongbinary-class.md) 여기에 개체 `COleVariant` 개체입니다.  
  
 자세한 내용은 참조는 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) 및 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) 항목에는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="operator_eq_eq"></a>COleVariant::operator = =  
 이 연산자는 두 variant 값을 비교 하 고 같으면; 0이 아닌 반환 그렇지 않으면 0입니다.  
  
```  
BOOL operator==(const VARIANT& varSrc) const; 
BOOL operator==(LPCVARIANT pSrc) const;
```  
  
##  <a name="operator_lt_lt__gt_gt"></a>COleVariant::operator &lt; &lt;,&gt;&gt;  
 출력을 `COleVariant` 값을 `CArchive` 또는 **CdumpContext** 입력 하 고는 `COleVariant` 에서 개체 `CArchive`합니다.  
  
```  
friend CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,  
    OleVariant varSrc);
 
friend CArchive& AFXAPI operator<<(
    CArchive& ar,  
    COleVariant varSrc);
 
friend CArchive& AFXAPI operator>>(
    CArchive& ar,  
    COleVariant& varSrc);
```  
  
### <a name="remarks"></a>주의  
 `COleVariant` 삽입 ( ** < \< **) 연산자를 지원 진단 덤프 및 보관 파일에 저장 합니다. 추출 ( ** >> **) 연산자는 보관 파일에서 로드를 지원 합니다.  
  
##  <a name="setstring"></a>COleVariant::SetString  
 특정 형식에는 문자열을 설정합니다.  
  
```  
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszSrc`  
 Null로 끝나는 문자열을 복사할 새 `COleVariant` 개체입니다.  
  
 *VtSrc*  
 **VARTYPE** 새 `COleVariant` 개체입니다.  
  
### <a name="remarks"></a>주의  
 매개 변수 `vtSrc` 해야 `VT_BSTR` (유니코드) 또는 `VT_BSTRT` (ANSI)입니다. `SetString`일반적으로 ANSI 문자열에 대 한 기본 설정 사용는 [COleVariant::COleVariant](#colevariant) 생성자는 문자열이 나 문자열 포인터 매개 변수 및 no와 **VARTYPE** 은 유니코드입니다.  
  
 DAO 레코드 집합 유니코드가 아닌 빌드에는 문자열을 ANSI 필요 합니다. 따라서 DAO를 사용 하는 함수 `COleVariant` 사용 해야 개체를 유니코드 레코드 집합을 만들지 않는 경우는 **COleVariant::COleVariant (** `lpszSrc` **,** `vtSrc` **)** 형태의 생성자와 `vtSrc` 로 설정 `VT_BSTRT` (ANSI) 하거나 사용 하 여 `SetString` 와 `vtSrc` 로 설정 `VT_BSTRT` ANSI 문자열 수 있도록 합니다. 예를 들어는 `CDaoRecordset` 함수 [CDaoRecordset::Seek](../../mfc/reference/cdaorecordset-class.md#seek) 및 [CDaoRecordset::SetFieldValue](../../mfc/reference/cdaorecordset-class.md#setfieldvalue) 사용 `COleVariant` 개체를 매개 변수로 합니다. 이러한 개체는 DAO 레코드 집합은 유니코드가 아닙니다 하는 경우 ANSI 여야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)




