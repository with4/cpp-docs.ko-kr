---
title: 속성 페이지 (MFC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- property page data transfer functions in MFC
- property pages [MFC], global MFC functions
ms.assetid: 734f88bc-c776-4136-9b0e-f45c761a45c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0895cd22870b3a4a266e9be12f0000fae7f7101a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376560"
---
# <a name="property-pages-mfc"></a>속성 페이지(MFC)
속성 페이지 보기 및 편집 대화 상자 데이터 교환 (DDX)를 기반으로 데이터 매핑 메커니즘을 지원 하 여 사용자 지정할 수 있는,이 그래픽 인터페이스의 특정 OLE 컨트롤 속성의 현재 값을 표시 합니다.  
  
 이 데이터 매핑 메커니즘의 OLE 컨트롤의 개별 속성을 속성 페이지 컨트롤을 매핑합니다. 컨트롤 속성 값의 상태 또는 속성 페이지 컨트롤의 콘텐츠를 반영합니다. 속성 페이지 컨트롤 및 속성 간의 매핑을 지정 **DDP_** 속성 페이지에서 함수 호출 `DoDataExchange` 멤버 함수입니다. 다음은 목록이 **DDP_** 컨트롤의 속성 페이지를 사용 하 여 입력 데이터를 교환 하는 기능:  
  
### <a name="property-page-data-transfer"></a>속성 페이지 데이터 전송  
  
|||  
|-|-|  
|[DDP_CBIndex](#ddp_cbindex)|콤보 상자 컨트롤의 속성에서에서 선택한 문자열의 인덱스를 연결합니다.|  
|[DDP_CBString](#ddp_cbstring)|콤보 상자 컨트롤의 속성에서에서 선택한 문자열을 연결합니다. 선택 된 문자열 속성의 값으로 동일한 문자로 시작할 수 하지만 완벽 하 게 일치 시킬 필요는 없습니다.|  
|[DDP_CBStringExact](#ddp_cbstringexact)|콤보 상자 컨트롤의 속성에서에서 선택한 문자열을 연결합니다. 선택한 문자열 및 속성의 문자열 값이 정확히 일치 해야 합니다.|  
|[DDP_Check](#ddp_check)|컨트롤의 속성으로 컨트롤의 속성 페이지에서 확인란을 연결합니다.|  
|[DDP_LBIndex](#ddp_lbindex)|컨트롤의 속성으로 목록 상자에서 선택한 문자열의 인덱스를 연결합니다.|  
|[DDP_LBString](#ddp_lbstring)|컨트롤의 속성으로 목록 상자에서 선택한 문자열을 연결합니다. 선택 된 문자열 속성의 값으로 동일한 문자로 시작할 수 있지만 완벽 하 게 일치 하지 않아도 합니다.|  
|[DDP_LBStringExact](#ddp_lbstringexact)|컨트롤의 속성으로 목록 상자에서 선택한 문자열을 연결합니다. 선택한 문자열 및 속성의 문자열 값이 정확히 일치 해야 합니다.|  
|[DDP_PostProcessing](#ddp_postprocessing)|컨트롤에서 속성 값의 전송을 완료 됩니다.|  
|[DDP_Radio](#ddp_radio)|컨트롤의 속성으로 컨트롤의 속성 페이지에서 라디오 단추 그룹 연결 되어 있습니다.|  
|[DDP_Text](#ddp_text)|컨트롤의 속성으로 컨트롤의 속성 페이지에서 컨트롤을 연결합니다. 이 함수는 몇 가지 유형의 속성을 같은 처리 **double**, **짧은**, `BSTR`, 및 **긴**합니다.|  
  
 에 대 한 자세한 내용은 `DoDataExchange` 함수 및 속성 페이지를 문서 참조 [ActiveX 컨트롤: 속성 페이지](../../mfc/mfc-activex-controls-property-pages.md)합니다.  
  
 다음은 만들고 OLE 컨트롤에 대 한 속성 페이지를 관리 하는 데 사용 되는 매크로의 목록입니다.  
  
### <a name="property-pages"></a>속성 페이지  
  
|||  
|-|-|  
|[BEGIN_PROPPAGEIDS](#begin_proppageids)|속성 페이지 Id 목록을 시작합니다.|  
|[END_PROPPAGEIDS](#end_proppageids)|속성 페이지 Id 목록을 종료합니다.|  
|[PROPPAGEID](#proppageid)|컨트롤 클래스의 속성 페이지를 선언합니다.|  
  
##  <a name="ddp_cbindex"></a>  DDP_CBIndex  
 속성 페이지의 `DoDataExchange` 함수에서 이 함수를 호출하여 정수 속성의 값을 속성 페이지의 콤보 상자에 있는 현재 선택 항목의 인덱스와 동기화합니다.  
  
```   
void AFXAPI DDP_CBIndex(
    CDataExchange* pDX,  
    int id,  
    int& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `id`  
 `pszPropName`에 의해 지정된 컨트롤 속성과 연결된 콤보 상자 컨트롤의 리소스 ID입니다.  
  
 `member`  
 `id`로 지정된 속성 페이지 컨트롤 및 `pszPropName`으로 지정된 속성과 연결된 멤버 변수입니다.  
  
 `pszPropName`  
 `id`로 지정된 콤보 상자 컨트롤과 교환할 컨트롤 속성의 속성 이름입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 해당 `DDX_CBIndex` 함수 호출 전에 호출되어야 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="ddp_cbstring"></a>  DDP_CBString  
 속성 페이지에서이 함수를 호출 `DoDataExchange` 속성 페이지의 콤보 상자에서 현재 선택한 항목을 문자열 속성의 값을 동기화 하는 함수입니다.  
  
```  
void AFXAPI DDP_CBString(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `id`  
 `pszPropName`에 의해 지정된 컨트롤 속성과 연결된 콤보 상자 컨트롤의 리소스 ID입니다.  
  
 `member`  
 `id`로 지정된 속성 페이지 컨트롤 및 `pszPropName`으로 지정된 속성과 연결된 멤버 변수입니다.  
  
 `pszPropName`  
 지정 된 콤보 상자 문자열와 교환할 컨트롤 속성의 속성 이름 `id`합니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 해당 `DDX_CBString` 함수 호출 전에 호출되어야 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="ddp_cbstringexact"></a>  DDP_CBStringExact  
 속성 페이지에서이 함수를 호출 `DoDataExchange` 속성 페이지의 콤보 상자에서 현재 선택한와 정확히 일치 하는 문자열 속성의 값을 동기화 하는 함수입니다.  
  
```  
void AFXAPI DDP_CBStringExact(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `id`  
 `pszPropName`에 의해 지정된 컨트롤 속성과 연결된 콤보 상자 컨트롤의 리소스 ID입니다.  
  
 `member`  
 `id`로 지정된 속성 페이지 컨트롤 및 `pszPropName`으로 지정된 속성과 연결된 멤버 변수입니다.  
  
 `pszPropName`  
 지정 된 콤보 상자 문자열와 교환할 컨트롤 속성의 속성 이름 `id`합니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 해당 `DDX_CBStringExact` 함수 호출 전에 호출되어야 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="ddp_check"></a>  DDP_Check  
 속성 페이지에서이 함수를 호출 `DoDataExchange` 연결된 속성 페이지 확인란 컨트롤과 속성의 값을 동기화 하는 함수입니다.  
  
```   
void AFXAPI DDP_Check(
    CDataExchange* pDX,  
    int id,  
    int & member,  
    LPCSTR pszPropName);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `id`  
 Check box 컨트롤의 리소스 ID로 지정 된 컨트롤 속성 연관 `pszPropName`합니다.  
  
 `member`  
 `id`로 지정된 속성 페이지 컨트롤 및 `pszPropName`으로 지정된 속성과 연결된 멤버 변수입니다.  
  
 `pszPropName`  
 로 지정 된 확인란 컨트롤와 교환할 컨트롤 속성의 속성 이름 `id`합니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 해당 `DDX_Check` 함수 호출 전에 호출되어야 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="ddp_lbindex"></a>  DDP_LBIndex  
 속성 페이지에서이 함수를 호출 `DoDataExchange` 속성 페이지에서 목록 상자에서 현재 선택 항목의 인덱스와 정수 속성의 값을 동기화 하는 함수입니다.  
  
```   
void AFXAPI DDP_LBIndex(
    CDataExchange* pDX,  
    int id,  
    int& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `id`  
 목록의 리소스 ID로 지정 된 컨트롤 속성과 연결 된 컨트롤 상자 `pszPropName`합니다.  
  
 `member`  
 `id`로 지정된 속성 페이지 컨트롤 및 `pszPropName`으로 지정된 속성과 연결된 멤버 변수입니다.  
  
 `pszPropName`  
 지정 된 목록 상자 문자열와 교환할 컨트롤 속성의 속성 이름 `id`합니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 해당 `DDX_LBIndex` 함수 호출 전에 호출되어야 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="ddp_lbstring"></a>  DDP_LBString  
 속성 페이지에서이 함수를 호출 `DoDataExchange` 속성 페이지에서 목록 상자에서 현재 선택한 항목을 문자열 속성의 값을 동기화 하는 함수입니다.  
  
```   
void AFXAPI DDP_LBString(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `id`  
 목록의 리소스 ID로 지정 된 컨트롤 속성과 연결 된 컨트롤 상자 `pszPropName`합니다.  
  
 `member`  
 `id`로 지정된 속성 페이지 컨트롤 및 `pszPropName`으로 지정된 속성과 연결된 멤버 변수입니다.  
  
 `pszPropName`  
 지정 된 목록 상자 문자열와 교환할 컨트롤 속성의 속성 이름 `id`합니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 해당 `DDX_LBString` 함수 호출 전에 호출되어야 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="ddp_lbstringexact"></a>  DDP_LBStringExact  
 속성 페이지에서이 함수를 호출 `DoDataExchange` 속성 페이지에서 목록 상자에서 현재 선택 영역을 정확 하 게 일치 하는 문자열 속성의 값을 동기화 하는 함수입니다.  
  
```   
void AFXAPI DDP_LBStringExact(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `id`  
 목록의 리소스 ID로 지정 된 컨트롤 속성과 연결 된 컨트롤 상자 `pszPropName`합니다.  
  
 `member`  
 `id`로 지정된 속성 페이지 컨트롤 및 `pszPropName`으로 지정된 속성과 연결된 멤버 변수입니다.  
  
 `pszPropName`  
 지정 된 목록 상자 문자열와 교환할 컨트롤 속성의 속성 이름 `id`합니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 해당 `DDX_LBStringExact` 함수 호출 전에 호출되어야 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="ddp_postprocessing"></a>  DDP_PostProcessing  
 속성 페이지에서이 함수를 호출 `DoDataExchange` 함수 속성 값을 저장 하는 경우 속성 페이지 컨트롤 속성 값의 전송을 완료 합니다.  
  
```   
void AFXAPI DDP_PostProcessing(CDataExchange * pDX);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
### <a name="remarks"></a>설명  
 모든 데이터 교환 함수를 완료 한 후이 함수를 호출 해야 합니다. 예를 들어:  
  
 [!code-cpp[NVC_MFCAxCtl#15](../../mfc/reference/codesnippet/cpp/property-pages-mfc_1.cpp)]  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="ddp_radio"></a>  DDP_Radio  
 컨트롤의이 함수를 호출 `DoPropExchange` 연결된 속성 페이지 라디오 단추 컨트롤 속성의 값을 동기화 하는 함수입니다.  
  
```   
void AFXAPI DDP_Radio(
    CDataExchange* pDX,  
    int id,  
    int & member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `id`  
 리소스 ID 라디오 단추 컨트롤이로 지정 된 컨트롤 속성과 관련 된 `pszPropName`합니다.  
  
 `member`  
 `id`로 지정된 속성 페이지 컨트롤 및 `pszPropName`으로 지정된 속성과 연결된 멤버 변수입니다.  
  
 `pszPropName`  
 로 지정 된 라디오 단추 컨트롤과 교환할 컨트롤 속성의 속성 이름 `id`합니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 해당 `DDX_Radio` 함수 호출 전에 호출되어야 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="ddp_text"></a>  DDP_Text  
 컨트롤의이 함수를 호출 `DoDataExchange` 연결된 속성 페이지 컨트롤 속성의 값을 동기화 하는 함수입니다.  
  
```   
void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    BYTE & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    int & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    UINT & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    long & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    DWORD & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    float & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    double & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    CString & member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `id`  
 리소스 ID로 지정 된 컨트롤 속성과 연결 된 컨트롤의 `pszPropName`합니다.  
  
 `member`  
 `id`로 지정된 속성 페이지 컨트롤 및 `pszPropName`으로 지정된 속성과 연결된 멤버 변수입니다.  
  
 `pszPropName`  
 로 지정 된 컨트롤과 교환할 컨트롤 속성의 속성 이름 `id`합니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 해당 `DDX_Text` 함수 호출 전에 호출되어야 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="begin_proppageids"></a>  BEGIN_PROPPAGEIDS  
 컨트롤의 목록은 속성 페이지 Id의 정의 시작합니다.  
  
```   
BEGIN_PROPPAGEIDS(class_name,  count)   
```  
  
### <a name="parameters"></a>매개 변수  
 *class_name*  
 속성에 대 한 페이지 지정 된 컨트롤 클래스의 이름입니다.  
  
 *count*  
 컨트롤 클래스에 의해 사용 되는 속성 페이지의 수입니다.  
  
### <a name="remarks"></a>설명  
 클래스 멤버 함수를 정의 하는 구현 (.cpp) 파일에서 사용 하 여 속성 페이지 목록 시작는 `BEGIN_PROPPAGEIDS` 매크로, 그런 다음 각 속성 페이지에 대해 매크로 항목을 추가 하 고 사용 하 여 속성 페이지 목록 완료는 `END_PROPPAGEIDS` 매크로입니다.  
  
 속성 페이지에 대 한 자세한 내용은 문서 참조 [ActiveX 컨트롤: 속성 페이지](../../mfc/mfc-activex-controls-property-pages.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="end_proppageids"></a>  END_PROPPAGEIDS  
 속성 페이지 ID 목록의 정의 종료합니다.  
  
```   
END_PROPPAGEIDS(class_name)   
```  
  
### <a name="parameters"></a>매개 변수  
 *class_name*  
 속성 페이지를 소유 하는 컨트롤 클래스의 이름입니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="proppageid"></a>  PROPPAGEID  
 OLE 컨트롤에서 사용 하기 위해 속성 페이지를 추가 합니다.  
  
```   
PROPPAGEID(clsid)   
```  
  
### <a name="parameters"></a>매개 변수  
 `clsid`  
 속성 페이지의 고유 클래스 ID입니다.  
  
### <a name="remarks"></a>설명  
 모든 `PROPPAGEID` 매크로 사이 배치 해야 합니다는 `BEGIN_PROPPAGEIDS` 및 `END_PROPPAGEIDS` 컨트롤의 구현 파일에는 매크로입니다.  

### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
    
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
