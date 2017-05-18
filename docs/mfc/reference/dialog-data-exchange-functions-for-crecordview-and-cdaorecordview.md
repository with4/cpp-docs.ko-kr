---
title: "CRecordView 및 CDaoRecordView에 대 한 대화 상자 데이터 교환 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFXDAO/DDX_FieldCBIndex
- AFXDAO/DDX_FieldCBString
- AFXDAO/DDX_FieldCBStringExact
- AFXDAO/DDX_FieldCheck
- AFXDAO/DDX_FieldLBIndex
- AFXDAO/DDX_FieldLBString
- AFXDAO/DDX_FieldLBStringExact
- AFXDAO/DDX_FieldRadio
- AFXDAO/DDX_FieldScroll
- AFXDAO/DDX_FieldText
dev_langs:
- C++
helpviewer_keywords:
- DDX_Field functions
- ODBC [C++], dialog data exchange (DDX) support
- DDX (dialog data exchange) [C++], database support
- DDX (dialog data exchange) [C++], functions
- databases [C++], dialog data exchange (DDX) support
- DAO [C++], dialog data exchange (DDX) support
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
caps.latest.revision: 13
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: b943ef8dd652df061965fe81ecc9c08115636141
ms.openlocfilehash: c6256e6a510e3640bfdfd43cace5afbdec72b849
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="dialog-data-exchange-functions-for-crecordview-and-cdaorecordview"></a>CRecordView 및 CDaoRecordView에 대한 대화 상자 데이터 교환 함수
이 항목에서는 간에 데이터를 교환 하는 데 사용 DDX_Field 함수는 [CRecordset](../../mfc/reference/crecordset-class.md) 및 [CRecordView](../../mfc/reference/crecordview-class.md) 양식 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 폼입니다.  
  
> [!NOTE]
>  DDX_Field 함수 양식의 컨트롤을 사용 하 여 데이터를 교환 DDX 함수와 비슷합니다. 하지만 필드 자체 레코드 보기 대신 보기의 관련된 레코드 집합 개체의 필드를 사용 하 여 데이터를 교환 하기, DDX와 달리 합니다. 자세한 내용은 클래스를 참조 하십시오. `CRecordView` 및 `CDaoRecordView`합니다.  
  
### <a name="ddxfield-functions"></a>DDX_Field 함수  
  
|||  
|-|-|  
|[DDX_FieldCBIndex](#ddx_fieldcbindex)|레코드 집합 필드 데이터 멤버 및 콤보 상자에 현재 선택 항목의 인덱스 간에 정수 데이터를 전송는 [CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)합니다.|  
|[DDX_FieldCBString](#ddx_fieldcbstring)|전송 `CString` 레코드 집합 필드 데이터 멤버 및 콤보 편집 컨트롤 간의 데이터 상자에 `CRecordView` 또는 `CDaoRecordView`합니다. 데이터를 레코드 집합에서 컨트롤을 이동할 때는이 함수는 지정된 된 문자열에는 문자로 시작 하는 콤보 상자에서 항목을 선택 합니다.|  
|[DDX_FieldCBStringExact](#ddx_fieldcbstringexact)|전송 `CString` 레코드 집합 필드 데이터 멤버 및 콤보 편집 컨트롤 간의 데이터 상자에 `CRecordView` 또는 `CDaoRecordView`합니다. 데이터를 레코드 집합에서 컨트롤을 이동할 때는이 함수는 지정 된 문자열과 정확히 일치 하는 콤보 상자에서 항목을 선택 합니다.|  
|[DDX_FieldCheck](#ddx_fieldcheck)|레코드 집합 필드 데이터 멤버 및 확인란에 간에 부울 데이터를 전송는 `CRecordView` 또는 `CDaoRecordView`합니다.|  
|[DDX_FieldLBIndex](#ddx_fieldlbindex)|레코드 집합 필드 데이터 멤버와 목록 상자에서 현재 선택 항목의 인덱스 간의 정수 데이터를 전송는 `CRecordView` 또는 `CDaoRecordView`합니다.|  
|[DDX_FieldLBString](#ddx_fieldlbstring)|전송을 관리 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 목록 상자 컨트롤 및 레코드 집합의 필드 데이터 멤버 간에 데이터입니다. 컨트롤에는 레코드 집합에서 데이터를 이동,이 함수는 지정 된 문자열의 문자로 시작 하는 목록 상자에서 항목을 선택 합니다.|  
|[DDX_FieldLBStringExact](#ddx_fieldlbstringexact)|전송을 관리 `CString` 목록 상자 컨트롤 및 레코드 집합의 필드 데이터 멤버 간에 데이터입니다. 컨트롤에는 레코드 집합에서 데이터를 이동,이 함수는 지정 된 문자열과 정확히 일치 하는 첫 번째 항목을 선택 합니다.|  
|[DDX_FieldRadio](#ddx_fieldradio)|레코드 집합 필드 데이터 멤버와의 라디오 단추 그룹 간에 정수 데이터를 전송는 `CRecordView` 또는 `CDaoRecordView`합니다.|  
|[DDX_FieldScroll](#ddx_fieldscroll)|스크롤 막대 컨트롤의 스크롤 위치를 가져오거나 설정 합니다.는 `CRecordView` 또는 `CDaoRecordView`합니다. 호출 프로그램 [DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) 함수입니다.|  
|[DDX_FieldSlider](#ddx_fieldslider)|레코드 뷰에서의 슬라이더 컨트롤의 스크롤 상자 위치를 동기화 및 `int` 레코드 집합의 필드 데이터 멤버입니다. |
|[DDX_FieldText](#ddx_fieldtext)|오버 로드 된 버전을 전송 하는 데 사용할 수 `int`, **UINT**, **긴**, `DWORD`, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float**, **double**, **짧은**, [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), 및 [COleCurrency](../../mfc/reference/colecurrency-class.md) 레코드 집합 필드 데이터 멤버 및 편집 간에 데이터 상자에 `CRecordView` 또는 `CDaoRecordView`합니다.|  
  
##  <a name="ddx_fieldcbindex"></a>DDX_FieldCBIndex  
 `DDX_FieldCBIndex` 레코드 뷰에서의 콤보 상자 컨트롤의 목록 상자 컨트롤에서 선택한 항목의 인덱스를 동기화 하는 함수 및 `int` 레코드 보기와 연결 된 레코드 집합의 필드 데이터 멤버입니다.  
  
```  
void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 에 컨트롤의 ID는 [CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체입니다.  
  
 *인덱스*  
 연결 된 필드 데이터 멤버에 대 한 참조 `CRecordset` 또는 `CDaoRecordset` 개체입니다.  
  
 `pRecordset`  
 에 대 한 포인터는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체 데이터를 교환 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수에 지정 된 값에 따라 컨트롤에서 선택 항목을 설정 데이터를 레코드 집합에서 컨트롤을 이동할 때는 *인덱스*합니다. 전송 레코드 집합에서 컨트롤을 레코드 집합 필드는 Null, MFC 설정 된 인덱스의 값을 0으로 합니다. 레코드 집합에 컨트롤에서 전송, 컨트롤 비어 있거나 없는 항목을 선택 하는 경우 레코드 집합 필드를 0으로 설정 됩니다.  
  
 ODBC 기반 클래스를 사용 하는 경우에 첫 번째 버전을 사용 합니다. DAO 기반 클래스를 사용 하는 경우에 두 번째 버전을 사용 합니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다. 예제 및에 대 한 DDX에 대 한 자세한 내용은 [CRecordView](../../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 필드, 문서를 참조 하십시오. [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다.  
  
### <a name="example"></a>예제  
 참조 [DDX_FieldText](#ddx_fieldtext) 일반적인 DDX_Field 예제에 대 한 합니다. 이 예제에 대 한 유사 합니다 `DDX_FieldCBIndex`합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  

##  <a name="ddx_fieldcbstring"></a>DDX_FieldCBString  
 `DDX_FieldCBString` 함수의 전송을 관리 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 레코드 뷰에서의 콤보 상자 컨트롤의 편집 컨트롤 간에 데이터 및 `CString` 레코드 보기와 연결 된 레코드 집합의 필드 데이터 멤버입니다.  
  
```  
void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 에 컨트롤의 ID는 [CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체입니다.  
  
 *value*  
 연결 된 필드 데이터 멤버에 대 한 참조 `CRecordset` 또는 `CDaoRecordset` 개체입니다.  
  
 `pRecordset`  
 에 대 한 포인터는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체 데이터를 교환 합니다.  
  
### <a name="remarks"></a>주의  
 이 함수에 지정 된 문자열의 문자로 시작 하는 첫 번째 행에 콤보 상자에서 현재 선택 영역을 설정 데이터를 레코드 집합에서 컨트롤을 이동할 때는 *값*합니다. 레코드 집합에서 전송 하기 위해서는 컨트롤에서 레코드 집합 필드에 Null 인 경우 모든 선택 콤보 상자에서 제거 되 고 콤보 상자의 편집 컨트롤 설정 비어 있는 것으로 합니다. 레코드 집합에 컨트롤에서으로 전송에서 컨트롤 비어 있으면 레코드 집합 필드 Null로 설정 됩니다 필드에서 허용 하는 경우.  
  
 ODBC 기반 클래스를 사용 하는 경우에 첫 번째 버전을 사용 합니다. DAO 기반 클래스를 사용 하는 경우에 두 번째 버전을 사용 합니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다. 예제 및에 대 한 DDX에 대 한 자세한 내용은 [CRecordView](../../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 필드, 문서를 참조 하십시오. [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다.  
  
### <a name="example"></a>예제  
 참조 [DDX_FieldText](#ddx_fieldtext) 일반적인 DDX_Field 예제에 대 한 합니다. 예제에 대 한 호출에 포함 되어 `DDX_FieldCBString`합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdao.h  
  
## <a name="ddx_fieldcbstringexact"></a>DDX_FieldCBStringExact  
 `DDX_FieldCBStringExact` 함수의 전송을 관리 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 레코드 뷰에서의 콤보 상자 컨트롤의 편집 컨트롤 간에 데이터 및 `CString` 레코드 보기와 연결 된 레코드 집합의 필드 데이터 멤버입니다.  
  
```  
void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 에 컨트롤의 ID는 [CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체입니다.  
  
 *value*  
 연결 된 필드 데이터 멤버에 대 한 참조 `CRecordset` 또는 `CDaoRecordset` 개체입니다.  
  
 `pRecordset`  
 에 대 한 포인터는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체 데이터를 교환 합니다.  
  
### <a name="remarks"></a>주의  
 이 함수에 지정 된 문자열과 정확히 일치 하는 첫 번째 행에 콤보 상자에서 현재 선택 영역을 설정 데이터를 레코드 집합에서 컨트롤을 이동할 때는 *값*합니다. 레코드 집합에서 전송 하기 위해서는 컨트롤에서 레코드 집합 필드에 NULL 인 경우 모든 선택 콤보 상자에서 제거 되 고 콤보 상자의 편집 상자 설정 되어 비어 있는 것으로 합니다. 레코드 집합에 컨트롤에서으로 전송에서 컨트롤이 비어 레코드 집합 필드가 NULL로 설정 됩니다.  
  
 ODBC 기반 클래스를 사용 하는 경우에 첫 번째 버전을 사용 합니다. DAO 기반 클래스를 사용 하는 경우에 두 번째 버전을 사용 합니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다. 예제 및에 대 한 DDX에 대 한 자세한 내용은 [CRecordView](../../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 필드, 문서를 참조 하십시오. [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다.  
  
### <a name="example"></a>예제  
 참조 [DDX_FieldText](#ddx_fieldtext) 일반적인 DDX_Field 예제에 대 한 합니다. 에 대 한 호출이 `DDX_FieldCBStringExact` 유사 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdao.h  
  
##  <a name="ddx_fieldcheck"></a>DDX_FieldCheck  
 `DDX_FieldCheck` 함수의 전송을 관리 `int` 대화 상자에서 확인란 컨트롤 간의 데이터 폼 뷰 또는 컨트롤 뷰 개체 및 `int` 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 데이터 멤버입니다.  
  
```  
void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 컨트롤 속성에 연결 된 확인란 컨트롤의 리소스 ID입니다.  
  
 *value*  
 멤버 변수 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체 데이터를 교환에 대 한 참조입니다.  
  
 `pRecordset`  
 에 대 한 포인터는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체 데이터를 교환 합니다.  
  
### <a name="remarks"></a>주의  
 때 `DDX_FieldCheck` 호출 되 *값* 확인란 컨트롤의 현재 상태를 설정 하거나 컨트롤의 상태가 되도록 설정 되어 *값*전송의 방향에 따라 합니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdao.h  
  
##  <a name="ddx_fieldlbindex"></a>DDX_FieldLBIndex  
 `DDX_FieldLBIndex` 레코드 뷰에 목록 상자 컨트롤에서 선택한 항목의 인덱스를 동기화 하는 함수 및 `int` 레코드 보기와 연결 된 레코드 집합의 필드 데이터 멤버입니다.  
  
```  
void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 에 컨트롤의 ID는 [CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체입니다.  
  
 *인덱스*  
 연결 된 필드 데이터 멤버에 대 한 참조 `CRecordset` 또는 `CDaoRecordset` 개체입니다.  
  
 `pRecordset`  
 에 대 한 포인터는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체 데이터를 교환 합니다.  
  
### <a name="remarks"></a>주의  
 이 함수에 지정 된 값에 따라 컨트롤에서 선택 항목을 설정 데이터를 레코드 집합에서 컨트롤을 이동할 때는 *인덱스*합니다. 전송 레코드 집합에서 컨트롤을 레코드 집합 필드는 Null, MFC 설정 된 인덱스의 값을 0으로 합니다. 레코드 집합에 컨트롤에서 전송, 컨트롤 비어 있으면 레코드 집합 필드를 0으로 설정 됩니다.  
  
 ODBC 기반 클래스를 사용 하는 경우에 첫 번째 버전을 사용 합니다. DAO 기반 클래스를 사용 하는 경우에 두 번째 버전을 사용 합니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다. 예제 및에 대 한 DDX에 대 한 자세한 내용은 [CRecordView](../../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 필드, 문서를 참조 하십시오. [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다.  
  
### <a name="example"></a>예제  
 참조 [DDX_FieldText](#ddx_fieldtext) 일반적인 DDX_Field 예제에 대 한 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdao.h  
  
##  <a name="ddx_fieldlbstring"></a>DDX_FieldLBString  
 `DDX_FieldLBString` 레코드 뷰를 목록 상자 컨트롤의 현재 선택 영역 복사는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 레코드 보기와 연결 된 레코드 집합의 필드 데이터 멤버입니다.  
  
```  
void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 에 컨트롤의 ID는 [CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체입니다.  
  
 *value*  
 연결 된 필드 데이터 멤버에 대 한 참조 `CRecordset` 또는 `CDaoRecordset` 개체입니다.  
  
 `pRecordset`  
 에 대 한 포인터는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체 데이터를 교환 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수에서 지정 된 문자열의 문자로 시작 하는 첫 번째 행을 목록 상자에서 현재 선택 영역 설정 반대 방향에서 *값*합니다. 컨트롤에 레코드 집합에서으로 전송에서 레코드 집합 필드는 Null을 모든 선택 목록 상자에서 제거 됩니다. 레코드 집합에 컨트롤에서으로 전송에서 컨트롤이 비어 레코드 집합 필드가 Null로 설정 됩니다.  
  
 ODBC 기반 클래스를 사용 하는 경우에 첫 번째 버전을 사용 합니다. DAO 기반 클래스를 사용 하는 경우에 두 번째 버전을 사용 합니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다. 예제 및에 대 한 DDX에 대 한 자세한 내용은 [CRecordView](../../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 필드, 문서를 참조 하십시오. [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다.  
  
### <a name="example"></a>예제  
 참조 [DDX_FieldText](#ddx_fieldtext) 일반적인 DDX_Field 예제에 대 한 합니다. 에 대 한 호출이 `DDX_FieldLBString` 유사 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdao.h  
  
##  <a name="ddx_fieldlbstringexact"></a>DDX_FieldLBStringExact  
 `DDX_FieldLBStringExact` 함수를 레코드 뷰에 목록 상자 컨트롤의 현재 선택 영역 복사는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 레코드 보기와 연결 된 레코드 집합의 필드 데이터 멤버입니다.  
  
```  
void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 에 컨트롤의 ID는 [CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체입니다.  
  
 *value*  
 연결 된 필드 데이터 멤버에 대 한 참조 `CRecordset` 또는 `CDaoRecordset` 개체입니다.  
  
 `pRecordset`  
 에 대 한 포인터는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체 데이터를 교환 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수에 지정 된 문자열과 정확히 일치 하는 첫 번째 행에 있는 목록 상자에서 현재 선택 영역 설정 방향의 역방향 *값*합니다. 컨트롤에 레코드 집합에서으로 전송에서 레코드 집합 필드는 Null을 모든 선택 목록 상자에서 제거 됩니다. 레코드 집합에 컨트롤에서으로 전송에서 컨트롤이 비어 레코드 집합 필드가 Null로 설정 됩니다.  
  
 ODBC 기반 클래스를 사용 하는 경우에 첫 번째 버전을 사용 합니다. DAO 기반 클래스를 사용 하는 경우에 두 번째 버전을 사용 합니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다. 예제 및에 대 한 DDX에 대 한 자세한 내용은 [CRecordView](../../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 필드, 문서를 참조 하십시오. [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다.  
  
### <a name="example"></a>예제  
 참조 [DDX_FieldText](#ddx_fieldtext) 일반적인 DDX_Field 예제에 대 한 합니다. 에 대 한 호출이 `DDX_FieldLBStringExact` 유사 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdao.h  
  
##  <a name="ddx_fieldradio"></a>DDX_FieldRadio  
 `DDX_FieldRadio` 함수는 0부터 시작 연결 `int` 레코드 보기에서 라디오 단추 그룹에서 현재 선택 된 라디오 단추와 레코드 뷰의 레코드 집합의 멤버 변수입니다.  
  
```  
void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 첫 번째 ID 그룹의 (스타일으로 **WS_GROUP**) 인접 한 라디오 단추 컨트롤에 [CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체입니다.  
  
 *value*  
 연결 된 필드 데이터 멤버에 대 한 참조 `CRecordset` 또는 `CDaoRecordset` 개체입니다.  
  
 `pRecordset`  
 에 대 한 포인터는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체 데이터를 교환 합니다.  
  
### <a name="remarks"></a>주의  
 보기에서 레코드 집합 필드를 전송,이 함수를 설정의 *n 번째* (0부터 시작) 라디오 단추와 있는 단추를 해제 합니다. 반대 방향으로이 함수는 현재 (선택)에 있는 라디오 단추의 서 수를 레코드 집합 필드를 설정 합니다. 컨트롤에 레코드 집합에서으로 전송 레코드 집합 필드는 Null 인 경우 단추가 선택 되어 있습니다. 레코드 집합에 컨트롤에서으로 전송에서 없는 컨트롤을 선택 레코드 집합 필드는 Null로 설정 필드를 허용 하는 경우.  
  
 ODBC 기반 클래스를 사용 하는 경우에 첫 번째 버전을 사용 합니다. DAO 기반 클래스를 사용 하는 경우에 두 번째 버전을 사용 합니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다. 예제 및에 대 한 DDX에 대 한 자세한 내용은 [CRecordView](../../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 필드, 문서를 참조 하십시오. [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다.  
  
### <a name="example"></a>예제  
 참조 [DDX_FieldText](#ddx_fieldtext) 일반적인 DDX_Field 예제에 대 한 합니다. 에 대 한 호출이 `DDX_FieldRadio` 유사 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdao.h  
  
##  <a name="ddx_fieldscroll"></a>DDX_FieldScroll  
 `DDX_FieldScroll` 레코드 뷰에서의 스크롤 막대 컨트롤의 스크롤 위치를 동기화 하는 함수 및 `int` 레코드 뷰 (또는 매핑하도록 선택 하면 모든 정수 변수)과 관련 된 레코드 집합의 필드 데이터 멤버입니다.  
  
```  
void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 *nIDC\**  
 첫 번째 ID 그룹의 (스타일으로 **WS_GROUP**) 인접 한 라디오 단추 컨트롤에 [CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체입니다.  
  
 *value*  
 연결 된 필드 데이터 멤버에 대 한 참조 `CRecordset` 또는 `CDaoRecordset` 개체입니다.  
  
 `pRecordset`  
 에 대 한 포인터는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체 데이터를 교환 합니다.  
  
### <a name="remarks"></a>주의  
 이 함수에 지정 된 값에 스크롤 막대 컨트롤의 스크롤 위치를 설정 데이터를 레코드 집합에서 컨트롤을 이동할 때는 *값*합니다. 컨트롤에 레코드 집합에서으로 전송에서 레코드 집합 필드는 Null, 스크롤 막대 컨트롤을 0으로 설정 됩니다. 레코드 집합에 컨트롤에서으로 전송에서 컨트롤이 비어 레코드 집합 필드의 값은 0입니다.  
  
 ODBC 기반 클래스를 사용 하는 경우에 첫 번째 버전을 사용 합니다. DAO 기반 클래스를 사용 하는 경우에 두 번째 버전을 사용 합니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다. 예제 및에 대 한 DDX에 대 한 자세한 내용은 [CRecordView](../../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 필드, 문서를 참조 하십시오. [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다.  
  
### <a name="example"></a>예제  
 참조 [DDX_FieldText](#ddx_fieldtext) 일반적인 DDX_Field 예제에 대 한 합니다. 에 대 한 호출이 `DDX_FieldScroll` 유사 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdao.h  

  ## <a name="nameddxfieldslidera--ddxfieldslider"></a>name = "ddx_fieldslider" ></a> DDX_FieldSlider
`DDX_FieldSlider` 레코드 뷰에서의 슬라이더 컨트롤의 스크롤 상자 위치를 동기화 하는 함수 및 `int` 레코드 뷰 (또는 매핑하도록 선택 하면 모든 정수 변수)과 관련 된 레코드 집합의 필드 데이터 멤버입니다.  
   
### <a name="syntax"></a>구문  
  ```
   void AFXAPI DDX_FieldSlider(  
       CDataExchange* pDX,  
       int nIDC,  
       int& value,  
       CRecordset* pRecordset );  

void AFXAPI DDX_FieldSlider(  
     CDataExchange* pDX,  
     int nIDC,  
     int& value,  
     CDaoRecordset* pRecordset );  
```
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 [CDataExchange](cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 슬라이더 컨트롤의 리소스 ID입니다.  
  
 *value*  
 교환할 값에 대 한 참조입니다. 이 매개 변수를 보유 하거나 슬라이더 컨트롤의 현재 스크롤 상자 위치를 설정 하는 데 사용 됩니다.  
  
 `pRecordset`  
 연결 된에 대 한 포인터 `CRecordset` 또는 `CDaoRecordset` 개체 데이터를 교환 합니다.  
   
### <a name="remarks"></a>설명  
 이 함수에 지정 된 값으로 슬라이더의 위치를 설정 데이터를 레코드 집합에서 슬라이더를 이동할 때는 *값*합니다. 컨트롤에는 레코드 집합에서 전송, 레코드 집합 필드는 Null 인 경우 슬라이더 컨트롤의 위치를 0으로 설정 됩니다. 레코드 집합에 컨트롤에서으로 전송에서 컨트롤이 비어 레코드 집합 필드의 값은 0입니다.  
  
 `DDX_FieldSlider`위치 단순히 보다는 범위를 설정할 수 있는 슬라이더 컨트롤을 사용 하 여 범위 정보를 교환 하지 않습니다.  
  
 ODBC 기반 클래스를 사용 하는 경우 함수의 첫 번째 재정의 사용 합니다. DAO 기반 클래스와 두 번째 재정의 사용 합니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../dialog-data-exchange-and-validation.md)합니다. 예제 및에 대 한 DDX에 대 한 자세한 내용은 `CRecordView` 및 `CDaoRecordView` 필드 참조 [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다. 슬라이더 컨트롤에 대 한 정보를 참조 하십시오. [CSliderCtrl 사용 하 여](../using-csliderctrl.md)합니다.  
   
### <a name="example"></a>예제  
 참조 [DDX_FieldText](#ddx_fieldtext) 일반적인 DDX_Field 예제에 대 한 합니다. 에 대 한 호출이 `DDX_FieldSlider` 유사 합니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
   
### <a name="see-also"></a>참고 항목  
 [매크로 및 전역](mfc-macros-and-globals.md)   
  
##  <a name="ddx_fieldtext"></a>DDX_FieldText  
 `DDX_FieldText` 함수의 전송을 관리 `int`, **짧은**, **긴**, `DWORD`, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float**, **double**, **BOOL**, 또는 **바이트** 편집 상자 컨트롤 및 레코드 집합의 필드 데이터 멤버 간에 데이터입니다.  
  
```  
void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    BYTE& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    UINT& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    long& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    DWORD& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    float& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    double& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    short& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    BOOL& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    BYTE& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    long& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    DWORD& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    float& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    double& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    COleDateTime& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    COleCurrency& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 에 컨트롤의 ID는 [CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체입니다.  
  
 *value*  
 연결 된 필드 데이터 멤버에 대 한 참조 `CRecordset` 또는 `CDaoRecordset` 개체입니다. 값의 데이터 형식 중의 오버 로드 된 버전에 따라 달라 집니다 `DDX_FieldText` 사용 합니다.  
  
 `pRecordset`  
 에 대 한 포인터는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체 데이터를 교환 합니다. 이 포인터를 사용 하 `DDX_FieldText` 를 감지 하 여 Null 값을 설정 합니다.  
  
### <a name="remarks"></a>주의  
 에 대 한 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체 `DDX_FieldText` 전송도 관리 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), 및 [COleCurrency](../../mfc/reference/colecurrency-class.md) 값입니다. 빈 편집 상자 컨트롤에는 Null 값을 나타냅니다. 컨트롤에는 레코드 집합에서 전송, 레코드 집합 필드는 Null 인 경우 편집 상자 설정 비어 있는 것으로 합니다. 레코드 집합에 컨트롤에서으로 전송에서 컨트롤이 비어 레코드 집합 필드가 Null로 설정 됩니다.  
  
 버전을 사용 하 여 [CRecordset](../../mfc/reference/crecordset-class.md) 매개 변수는 ODBC 기반 클래스를 사용 하는 경우. 버전을 사용 하 여 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 매개 변수는 DAO 기반 클래스를 사용 하는 경우.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다. 예제 및에 대 한 DDX에 대 한 자세한 내용은 [CRecordView](../../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 필드, 문서를 참조 하십시오. [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다.  
  
### <a name="example"></a>예제  
 다음 `DoDataExchange` 에 대 한 함수는 [CRecordView](../../mfc/reference/crecordview-class.md) 포함 `DDX_FieldText` 세 개의 데이터 형식에 대 한 함수 호출: `IDC_COURSELIST` 은 콤보 상자; 다른 두 컨트롤은 편집 상자입니다. DAO 프로그래밍에 대 한는 *하기 위해* 매개 변수는에 대 한 포인터는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)합니다.  
  
 [!code-cpp[NVC_MFCDatabase # 43](../../mfc/codesnippet/cpp/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview_1.cpp)]  

  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdao.h  
    
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)

