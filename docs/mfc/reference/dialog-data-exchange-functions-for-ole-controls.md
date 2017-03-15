---
title: "OLE 컨트롤에 대 한 대화 상자 데이터 교환 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.data
dev_langs:
- C++
helpviewer_keywords:
- OLE controls, DDX functions
- DDX (dialog data exchange), OLE support
ms.assetid: 7ef1f288-ff65-40d4-aad2-5497bc00bb27
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
translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 0f8821051cd790d26d190c23db333ccebc9dc9d6
ms.lasthandoff: 02/24/2017

---
# <a name="dialog-data-exchange-functions-for-ole-controls"></a>OLE 컨트롤에 대한 대화 상자 데이터 교환 함수
이 항목 대화 상자, 폼 보기 또는 뷰 개체를 컨트롤에는 OLE 컨트롤의 속성 및 대화 상자, 폼 보기 또는 뷰 개체를 컨트롤의 데이터 멤버 간에 데이터를 교환 하는 데 사용 하는 DDX_OC 함수를 나열 합니다.  
  
### <a name="ddxoc-functions"></a>DDX_OC 함수  
  
|||  
|-|-|  
|[DDX_OCBool](#ddx_ocbool)|전송 프로세스를 관리 **BOOL** OLE 컨트롤의 속성 간에 데이터 및 **BOOL** 데이터 멤버입니다.|  
|[DDX_OCBoolRO](#ddx_ocboolro)|전송 프로세스를 관리 **BOOL** OLE 컨트롤의 읽기 전용 속성 간에 데이터 및 **BOOL** 데이터 멤버입니다.|  
|[DDX_OCColor](#ddx_occolor)|전송 프로세스를 관리 **OLE_COLOR** OLE 컨트롤의 속성 간에 데이터 및 **OLE_COLOR** 데이터 멤버입니다.|  
|[DDX_OCColorRO](#ddx_occolorro)|전송 프로세스를 관리 **OLE_COLOR** OLE 컨트롤의 읽기 전용 속성 간에 데이터 및 **OLE_COLOR** 데이터 멤버입니다.|  
|[DDX_OCFloat](#ddx_ocfloat)|전송 프로세스를 관리 **float** (또는 **double**) OLE 컨트롤의 속성 간에 데이터 및 **float** (또는 **이중**) 데이터 멤버입니다.|  
|[DDX_OCFloatRO](#ddx_ocfloatro)|전송 프로세스를 관리 **float** (또는 **double**) OLE 컨트롤의 읽기 전용 속성 간에 데이터 및 **float** (또는 **이중**) 데이터 멤버입니다.|  
|[DDX_OCInt](#ddx_ocint)|전송 프로세스를 관리 `int` (또는 **긴**)는 OLE 컨트롤의 속성 간에 데이터 및 `int` (또는 **긴**) 데이터 멤버입니다.|  
|[DDX_OCIntRO](#ddx_ocintro)|전송 프로세스를 관리 `int` (또는 **긴**) OLE 컨트롤의 읽기 전용 속성 간에 데이터 및 `int` (또는 **긴**) 데이터 멤버입니다.|  
|[DDX_OCShort](#ddx_ocshort)|전송 프로세스를 관리 **짧은** OLE 컨트롤의 속성 간에 데이터 및 **짧은** 데이터 멤버입니다.|  
|[DDX_OCShortRO](#ddx_ocshortro)|전송 프로세스를 관리 **짧은** OLE 컨트롤의 읽기 전용 속성 간에 데이터 및 **짧은** 데이터 멤버입니다.|  
|[DDX_OCText](#ddx_octext)|전송 프로세스를 관리 **CString** OLE 컨트롤의 속성 간에 데이터 및 **CString** 데이터 멤버입니다.|  
|[DDX_OCTextRO](#ddx_octextro)|전송 프로세스를 관리 **CString** OLE 컨트롤의 읽기 전용 속성 간에 데이터 및 **CString** 데이터 멤버입니다.|  
  
##  <a name="a-nameddxocboola--ddxocbool"></a><a name="ddx_ocbool"></a>DDX_OCBool  
 `DDX_OCBool` 함수 콘텐츠 전송을 관리 하며 **BOOL** 대화 상자에는 OLE 컨트롤의 속성 간에 데이터 보기 또는 컨트롤 뷰 개체의 형태로 및 **BOOL** 대화 상자, 폼 보기 또는 뷰 개체를 컨트롤의 데이터 멤버입니다.  
  
```   
void AFXAPI DDX_OCBool(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    BOOL& value);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.  
  
 `dispid`  
 컨트롤의 속성에 대한 디스패치 ID입니다.  
  
 *value*  
 데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.  
  
### <a name="remarks"></a>주의  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="a-nameddxocboolroa--ddxocboolro"></a><a name="ddx_ocboolro"></a>DDX_OCBoolRO  
 `DDX_OCBoolRO` 함수 콘텐츠 전송을 관리 하며 **BOOL** 대화 상자에는 OLE 컨트롤의 읽기 전용 속성 간의 데이터 보기 또는 컨트롤 뷰 개체의 형태로 및 **BOOL** 대화 상자, 폼 보기 또는 뷰 개체를 컨트롤의 데이터 멤버입니다.  
  
```   
void AFXAPI DDX_OCBoolRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    BOOL& value);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.  
  
 `dispid`  
 컨트롤의 속성에 대한 디스패치 ID입니다.  
  
 *value*  
 데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.  
  
### <a name="remarks"></a>주의  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="a-nameddxoccolora--ddxoccolor"></a><a name="ddx_occolor"></a>DDX_OCColor  
 `DDX_OCColor` 함수 콘텐츠 전송을 관리 하며 **OLE_COLOR** 대화 상자에는 OLE 컨트롤의 속성 간에 데이터 보기 또는 컨트롤 뷰 개체의 형태로 및 **OLE_COLOR** 대화 상자, 폼 보기 또는 뷰 개체를 컨트롤의 데이터 멤버입니다.  
  
```   
void AFXAPI DDX_OCColor(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    OLE_COLOR& value);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.  
  
 `dispid`  
 컨트롤의 속성에 대한 디스패치 ID입니다.  
  
 *value*  
 데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.  
  
### <a name="remarks"></a>주의  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="a-nameddxoccolorroa--ddxoccolorro"></a><a name="ddx_occolorro"></a>DDX_OCColorRO  
 `DDX_OCColorRO` 함수 콘텐츠 전송을 관리 하며 **OLE_COLOR** 대화 상자에는 OLE 컨트롤의 읽기 전용 속성 간의 데이터 보기 또는 컨트롤 뷰 개체의 형태로 및 **OLE_COLOR** 대화 상자, 폼 보기 또는 뷰 개체를 컨트롤의 데이터 멤버입니다.  
  
```   
void AFXAPI DDX_OCColorRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    OLE_COLOR& value);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.  
  
 `dispid`  
 컨트롤의 속성에 대한 디스패치 ID입니다.  
  
 *value*  
 데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.  
  
### <a name="remarks"></a>주의  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="a-nameddxocfloata--ddxocfloat"></a><a name="ddx_ocfloat"></a>DDX_OCFloat  
 `DDX_OCFloat` 함수의 전송을 관리 **float** (또는 **double**) 대화 상자에는 OLE 컨트롤의 속성 간에 데이터 보기 또는 컨트롤 뷰 개체의 형태로 및 **float** (또는 **이중**) 대화 상자, 폼 보기 또는 뷰 개체를 컨트롤의 데이터 멤버입니다.  
  
```   
void AFXAPI DDX_OCFloat(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    float& value);

void AFXAPI DDX_OCFloat(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    double& value);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.  
  
 `dispid`  
 컨트롤의 속성에 대한 디스패치 ID입니다.  
  
 *value*  
 데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.  
  
### <a name="remarks"></a>주의  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="a-nameddxocfloatroa--ddxocfloatro"></a><a name="ddx_ocfloatro"></a>DDX_OCFloatRO  
 `DDX_OCFloatRO` 함수의 전송을 관리 합니다 **float** (또는 **double**) 대화 상자에는 OLE 컨트롤의 읽기 전용 속성 간의 데이터 보기 또는 컨트롤 뷰 개체의 형태로 및 **float** (또는 **이중**) 대화 상자, 폼 보기 또는 뷰 개체를 컨트롤의 데이터 멤버입니다.  
  
```   
void AFXAPI DDX_OCFloatRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    float& value);

void AFXAPI DDX_OCFloatRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    double& value);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.  
  
 `dispid`  
 컨트롤의 속성에 대한 디스패치 ID입니다.  
  
 *value*  
 데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.  
  
### <a name="remarks"></a>주의  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="a-nameddxocinta--ddxocint"></a><a name="ddx_ocint"></a>DDX_OCInt  
 `DDX_OCInt` 함수 콘텐츠 전송을 관리 하며 `int` (또는 **긴**) 대화 상자에는 OLE 컨트롤의 속성 간에 데이터 보기 또는 컨트롤 뷰 개체의 형태로 및 `int` (또는 **긴**) 대화 상자, 폼 보기 또는 뷰 개체를 컨트롤의 데이터 멤버입니다.  
  
```   
void AFXAPI DDX_OCInt(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    int& value);

void AFXAPI DDX_OCInt(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    long& value);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.  
  
 `dispid`  
 컨트롤의 속성에 대한 디스패치 ID입니다.  
  
 *value*  
 데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.  
  
### <a name="remarks"></a>주의  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="a-nameddxocintroa--ddxocintro"></a><a name="ddx_ocintro"></a>DDX_OCIntRO  
 `DDX_OCIntRO` 함수 전송 프로세스를 관리 `int` (또는 **긴**) 대화 상자에는 OLE 컨트롤의 읽기 전용 속성 간의 데이터 보기 또는 컨트롤 뷰 개체의 형태로 및 `int` (또는 **긴**) 대화 상자, 폼 보기 또는 뷰 개체를 컨트롤의 데이터 멤버입니다.  
  
```   
void AFXAPI DDX_OCIntRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    int& value);

void AFXAPI DDX_OCIntRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    long& value);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.  
  
 `dispid`  
 컨트롤의 속성에 대한 디스패치 ID입니다.  
  
 *value*  
 데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.  
  
### <a name="remarks"></a>주의  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="a-nameddxocshorta--ddxocshort"></a><a name="ddx_ocshort"></a>DDX_OCShort  
 `DDX_OCShort` 함수는 대화 상자를 폼 보기에는 OLE 컨트롤의 속성 간에 간단한 데이터 전송 프로세스를 관리 또는 컨트롤 뷰 개체와 짧은 데이터 멤버 대화 상자, 폼 보기를 뷰 개체를 제어 합니다.  
  
```   
void AFXAPI DDX_OCShort(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    short& value);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.  
  
 `dispid`  
 컨트롤의 속성에 대한 디스패치 ID입니다.  
  
 *value*  
 데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.  
  
### <a name="remarks"></a>주의  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="a-nameddxocshortroa--ddxocshortro"></a><a name="ddx_ocshortro"></a>DDX_OCShortRO  
 `DDX_OCShortRO` 함수는 대화 상자를 폼 보기에는 OLE 컨트롤의 읽기 전용 속성 간의 짧은 데이터의 전송을 관리 또는 일부를 컨트롤 뷰 개체와 짧은 데이터 멤버 대화 상자, 폼 보기를 뷰 개체를 제어 합니다.  
  
```   
void AFXAPI DDX_OCShortRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    short& value);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.  
  
 `dispid`  
 컨트롤의 속성에 대한 디스패치 ID입니다.  
  
 *value*  
 데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.  
  
### <a name="remarks"></a>주의  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="a-nameddxoctexta--ddxoctext"></a><a name="ddx_octext"></a>DDX_OCText  
 **DDX_OCText** 함수 콘텐츠 전송을 관리 하며 **CString** 대화 상자에는 OLE 컨트롤의 속성 간에 데이터 보기 또는 컨트롤 뷰 개체의 형태로 및 **CString** 대화 상자, 폼 보기 또는 뷰 개체를 컨트롤의 데이터 멤버입니다.  
  
```   
void AFXAPI DDX_OCText(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    CString& value); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 **CDataExchange** 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.  
  
 `dispid`  
 컨트롤의 속성에 대한 디스패치 ID입니다.  
  
 *value*  
 데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.  
  
### <a name="remarks"></a>주의  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="a-nameddxoctextroa--ddxoctextro"></a><a name="ddx_octextro"></a>DDX_OCTextRO  
 `DDX_OCTextRO` 함수는 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체 내 OLE 컨트롤의 읽기 전용 속성과 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 `CString` 데이터 멤버 간 `CString` 데이터 전송을 관리합니다.  
  
```  
void AFXAPI DDX_OCTextRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    CString& value); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.  
  
 `dispid`  
 컨트롤의 속성에 대한 디스패치 ID입니다.  
  
 *value*  
 데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.  
  
### <a name="remarks"></a>주의  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  

### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h
    
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)

