---
title: 표준 대화 상자 데이터 교환 루틴 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- standard dialog, data exchange routines
ms.assetid: c6adb7f3-f9af-4cc5-a9ea-315c5b60ad1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f6c79a96439605bcf9ab670c1f75dda2d50169f6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377657"
---
# <a name="standard-dialog-data-exchange-routines"></a>표준 대화 상자 데이터 교환 루틴
이 항목에서는 일반적인 MFC 대화 상자 컨트롤에 사용 되는 표준 대화 상자 데이터 교환 (DDX) 루틴을 나열 합니다.  
  
> [!NOTE]
>  표준 대화 상자 데이터 교환 루틴은 헤더 파일 afxdd_.h에 정의 됩니다. 그러나 응용 프로그램에는 afxwin.h를 포함 되어야 합니다.  
  
### <a name="ddx-functions"></a>DDX 함수  
  
|||  
|-|-|  
|[DDX_CBIndex](#ddx_cbindex)|초기화 하거나 현재 선택 된 콤보 상자 컨트롤의 인덱스를 검색 합니다.|  
|[DDX_CBString](#ddx_cbstring)|초기화 하거나 콤보 상자 컨트롤의 편집 필드의 현재 콘텐츠를 검색 합니다.|  
|[DDX_CBStringExact](#ddx_cbstringexact)|초기화 하거나 콤보 상자 컨트롤의 편집 필드의 현재 콘텐츠를 검색 합니다.|  
|[DDX_Check](#ddx_check)|초기화 하거나 확인란 컨트롤의 현재 상태를 검색 합니다.|  
|[DDX_Control](#ddx_control)|하위 클래스는 대화 상자 내에서 지정 된 컨트롤입니다.|  
|[DDX_DateTimeCtrl](#ddx_datetimectrl)|초기화 하거나 날짜 및 시간 선택 컨트롤의 날짜 / 시간 데이터를 검색 합니다.|  
|[DDX_IPAddress](#ddx_ipaddress)|초기화 하거나 IP 주소 컨트롤의 현재 값을 검색 합니다.|  
|[DDX_LBIndex](#ddx_lbindex)|초기화 하거나 현재 선택 된 목록 상자 컨트롤의 인덱스를 검색 합니다.|  
|[DDX_LBString](#ddx_lbstring)|초기화 하거나 목록 상자 컨트롤 내에서 현재 선택 영역을 검색 합니다.|  
|[DDX_LBStringExact](#ddx_lbstringexact)|초기화 하거나 목록 상자 컨트롤 내에서 현재 선택 영역을 검색 합니다.|
|[DDX_ManagedControl](#ddx_managedcontrol)|컨트롤의 리소스 id입니다. 일치 하는.NET 컨트롤을 만듭니다.|  
|[DDX_MonthCalCtrl](#ddx_monthcalctrl)|초기화 하거나 달력 컨트롤의 현재 값을 검색 합니다.|  
|[DDX_Radio](#ddx_radio)|초기화 하거나 라디오 컨트롤 그룹 내에서 현재 확인란이 라디오 컨트롤이의 0 기반 인덱스를 검색 합니다.|  
|[DDX_Scroll](#ddx_scroll)|초기화 하거나 스크롤 컨트롤의 위치 조정 컨트롤의 현재 위치를 검색 합니다.|  
|[DDX_Slider](#ddx_slider)|초기화 하거나 슬라이더 컨트롤의 위치 조정 컨트롤의 현재 위치를 검색 합니다.|  
|[DDX_Text](#ddx_text)|초기화 하거나 편집 컨트롤의 현재 값을 검색 합니다.|  
  
##  <a name="ddx_cbindex"></a>  DDX_CBIndex  
 `DDX_CBIndex` 함수의 전송을 관리 `int` 대화 상자에서 콤보 상자 컨트롤 간의 데이터 폼 뷰 또는 컨트롤 뷰 개체 및 `int` 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 데이터 멤버입니다.  
  
```  
void AFXAPI DDX_CBIndex(
    CDataExchange* pDX,  
    int nIDC,  
    int& index);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 콤보 상자 컨트롤에 연결 된 컨트롤 속성의 리소스 ID입니다.  
  
 *index*  
 멤버 변수 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체 데이터를 교환에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 때 `DDX_CBIndex` 호출 *인덱스* 현재 콤보 상자의 선택 항목의 인덱스에 설정 됩니다. 선택 된 항목이 경우 *인덱스* 0으로 설정 됩니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="ddx_cbstring"></a>  DDX_CBString  
 `DDX_CBString` 함수의 전송을 관리 `CString` 대화 상자에서 콤보 상자 컨트롤의 편집 컨트롤 간의 데이터 폼 뷰 또는 컨트롤 뷰 개체 및 `CString` 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 데이터 멤버입니다.  
  
```  
void AFXAPI DDX_CBString(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 콤보 상자 컨트롤에 연결 된 컨트롤 속성의 리소스 ID입니다.  
  
 *값*  
 멤버 변수 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체 데이터를 교환에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 때 `DDX_CBString` 호출 *값* 현재 콤보 상자의 선택 항목으로 설정 됩니다. 선택 된 항목이 경우 *값* 길이가 0 인 문자열로 설정 됩니다.  
  
> [!NOTE]
>  콤보 상자의 드롭다운 목록 상자 이면 교환 값은 255 자로 제한 됩니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="ddx_cbstringexact"></a>  DDX_CBStringExact  
 `DDX_CBStringExact` 함수의 전송을 관리 `CString` 대화 상자에서 콤보 상자 컨트롤의 편집 컨트롤 간의 데이터 폼 뷰 또는 컨트롤 뷰 개체 및 `CString` 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 데이터 멤버입니다.  
  
```  
void AFXAPI DDX_CBStringExact(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 콤보 상자 컨트롤에 연결 된 컨트롤 속성의 리소스 ID입니다.  
  
 *값*  
 멤버 변수 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체 데이터를 교환에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 때 `DDX_CBStringExact` 호출 *값* 현재 콤보 상자의 선택 항목으로 설정 됩니다. 선택 된 항목이 경우 *값* 길이가 0 인 문자열로 설정 됩니다.  
  
> [!NOTE]
>  콤보 상자의 드롭다운 목록 상자 이면 교환 값은 255 자로 제한 됩니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="ddx_check"></a>  DDX_Check  
 `DDX_Check` 함수의 전송을 관리 `int` 대화 상자에서 확인란 컨트롤 간의 데이터 폼 뷰 또는 컨트롤 뷰 개체 및 `int` 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 데이터 멤버입니다.  
  
```  
void AFXAPI DDX_Check(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 컨트롤 속성에 연결 된 확인란 컨트롤의 리소스 ID입니다.  
  
 *값*  
 멤버 변수 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체 데이터를 교환에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 때 `DDX_Check` 호출 *값* 확인란 컨트롤의 현재 상태로 설정 됩니다. 가능한 상태 값의 목록에 대 한 참조 [BM_GETCHECK](http://msdn.microsoft.com/library/windows/desktop/bb775986) Windows sdk에서입니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="ddx_control"></a>  DDX_Control  
 `DDX_Control` 로 지정 된 컨트롤을 서브 클래스 함수 `nIDC`, 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체입니다.  
  
```  
void AFXAPI DDX_Control(
    CDataExchange* pDX,  
    int nIDC,  
    CWnd& rControl);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다.  
  
 `nIDC`  
 서브클래싱 할 컨트롤의 리소스 ID입니다.  
  
 *rControl*  
 대화 상자, 폼 뷰 또는 지정된 된 컨트롤에 관련 된 컨트롤 뷰 개체의 멤버 변수를 가리킵니다.  
  
### <a name="remarks"></a>설명  
 `pDX` 개체를 프레임 워크에서 제공 하는 경우는 `DoDataExchange` 함수를 호출 합니다. 따라서 `DDX_Control` 재정의가 내 에서만 호출 되어야 `DoDataExchange`합니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="ddx_datetimectrl"></a>  DDX_DateTimeCtrl  
 `DDX_DateTimeCtrl` 함수는 날짜 및 시간 선택 컨트롤 간의 날짜 및/또는 시간 데이터의 전송을 관리 ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) 대화 상자 또는 폼 뷰 개체 및 중 하나는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 또는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 대화 상자나 폼 뷰 개체의 데이터 멤버입니다.  
  
```  
void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    CTime& value);

void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    COleDateTime& value);

void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다. 이 개체를 삭제할 필요가 없습니다.  
  
 `nIDC`  
 멤버 변수와 연결 된 날짜 및 시간 선택 컨트롤의 리소스 ID입니다.  
  
 *값*  
 처음 두 버전에 대 한 참조는 `CTime` 또는 `COleDateTime` 멤버 변수, 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체 데이터를 교환 합니다. 세 번째 버전에 대 한 참조에는 `CString` 데이터 멤버 컨트롤 뷰 개체입니다.  
  
### <a name="remarks"></a>설명  
 때 `DDX_DateTimeCtrl` 호출 되 *값* 현재로 설정 된 날짜 및 시간 선택 컨트롤 또는 컨트롤의 상태 설정 되어 *값*exchange의 방향에 따라 합니다.  
  
 위의 세 번째 버전에서 `DDX_DateTimeCtrl` 의 전송을 관리 `CString` 데이터 날짜 간의 시간 컨트롤 및 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 컨트롤 뷰 개체의 데이터 멤버입니다. 문자열의 날짜 및 시간 형식 지정에 대 한 현재 로캘을 규칙을 사용 하 여 지정 합니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  

   

 
## <a name="ddx_managedcontrol"></a>  DDX_ManagedControl
컨트롤의 리소스 id입니다. 일치 하는.NET 컨트롤을 만듭니다.  
   
### <a name="syntax"></a>구문  
  ```  
template <typename T>  
void DDX_ManagedControl(  
     CDataExchange* pDX,   
     int nIDC,   
     CWinFormsControl<T>& control );  
```
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 [CDataExchange 클래스](cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 컨트롤 속성에 연결 된 컨트롤의 리소스 ID입니다.  
  
 `control`  
 에 대 한 참조는 [CWinFormsControl 클래스](cwinformscontrol-class.md) 개체입니다.  
   
### <a name="remarks"></a>설명  
 `DDX_ManagedControl` 호출 [CWinFormsControl::CreateManagedControl](cwinformscontrol-class.md#createmanagedcontrol) 리소스 컨트롤 id입니다. 일치 하는 컨트롤을 만들려면 사용 하 여 `DDX_ManagedControl` 컨트롤에 리소스 Id 중에서 만들려는 [CDialog::OnInitDialog](cdialog-class.md#oninitdialog)합니다. 데이터 교환에 대 한 Windows Forms 컨트롤에서 DDX/DDV 함수를 사용할 필요가 없습니다.  
  
 자세한 내용은 참조 [하는 방법: Windows Forms에서 DDX/DDV 데이터 바인딩 수행](../../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)합니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxwinforms.h  
   
### <a name="see-also"></a>참고 항목  
 [CWinFormsControl::CreateManagedControl](cwinformscontrol-class.md#createmanagedcontrol)   
 [CDialog::OnInitDialog](cdialog-class.md#oninitdialog)
 

  
##  <a name="ddx_ipaddress"></a>  DDX_IPAddress  
 `DDX_IPAddress` 함수 IP 주소 컨트롤 및 컨트롤 뷰 개체의 데이터 멤버 간의 데이터 전송을 관리 합니다.  
  
```  
void AFXAPI DDX_IPAddress(
    CDataExchange* pDX,  
    int nIDC,  
    DWORD& value);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 컨트롤 속성에 연결 된 IP 주소 컨트롤의 리소스 ID입니다.  
  
 *값*  
 에 대 한 참조는 `DWORD` IP 주소 컨트롤의 네 필드 값이 포함 됩니다. 필드는 채워져 있거나 다음과 같아야 합니다.  
  
|필드|필드 값을 포함 하는 비트|  
|-----------|-------------------------------------|  
|3|0 ~ 7|  
|2|8 ~ 15|  
|1|부터 23까지 16|  
|0|-31 24|  
  
 Win32를 사용 하 여 [IPM_GETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761378) 값을 읽거나 사용 [IPM_SETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761380) 을 값을 채웁니다. 이러한 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="remarks"></a>설명  
 때 `DDX_IPAddress` 호출 *값* 하거나 IP 주소 컨트롤에서 읽혀집니다 또는 *값* exchange의 방향에 따라 컨트롤에 기록 됩니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="ddx_lbindex"></a>  DDX_LBIndex  
 `DDX_LBIndex` 함수의 전송을 관리 `int` 대화 상자에서 목록 상자 컨트롤 간의 데이터 폼 뷰 또는 컨트롤 뷰 개체 및 `int` 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 데이터 멤버입니다.  
  
```  
void AFXAPI DDX_LBIndex(
    CDataExchange* pDX,  
    int nIDC,  
    int& index);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 목록 상자 컨트롤에 연결 된 컨트롤 속성의 리소스 ID입니다.  
  
 *index*  
 멤버 변수 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체 데이터를 교환에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 때 `DDX_LBIndex` 호출 *인덱스* 현재 목록 상자 선택의 인덱스에 설정 됩니다. 선택 된 항목이 경우 *인덱스* -1로 설정 합니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="ddx_lbstring"></a>  DDX_LBString  
 `DDX_LBString` 함수의 전송을 관리 `CString` 대화 상자에서 목록 상자 컨트롤 간의 데이터 폼 뷰 또는 컨트롤 뷰 개체 및 `CString` 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 데이터 멤버입니다.  
  
```  
void AFXAPI DDX_LBString(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 목록 상자 컨트롤에 연결 된 컨트롤 속성의 리소스 ID입니다.  
  
 *값*  
 멤버 변수 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체 데이터를 교환에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 때 `DDX_LBString` 시작 부분이 일치 하는 컨트롤의 첫 번째 항목 목록 상자 컨트롤에 데이터를 전송 하기 위해 호출 *값* 을 선택 합니다. (접두사만 하지 않고 전체 항목 일치를 사용 하 여 [DDX_LBStringExact](#ddx_lbstringexact).) 일치 하는 항목이 있으면 항목이 선택 됩니다. 일치 하는 것은 대/소문자 구분 합니다.  
  
 때 `DDX_LBString` 목록 상자 컨트롤에서 데이터를 전송 하기 위해 호출 *값* 현재 목록 상자 선택으로 설정 됩니다. 선택 된 항목이 경우 *값* 길이가 0 인 문자열로 설정 됩니다.  
  
> [!NOTE]
>  목록 상자는 드롭다운 목록 상자 인 경우 교환 값은 255 자로 제한 됩니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="ddx_lbstringexact"></a>  DDX_LBStringExact  
 `DDX_CBStringExact` 함수의 전송을 관리 `CString` 대화 상자에서 목록 상자 컨트롤의 편집 컨트롤 간의 데이터 폼 뷰 또는 컨트롤 뷰 개체 및 `CString` 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 데이터 멤버입니다.  
  
```  
void AFXAPI DDX_LBStringExact(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 목록 상자 컨트롤에 연결 된 컨트롤 속성의 리소스 ID입니다.  
  
 *값*  
 멤버 변수 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체 데이터를 교환에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 때 `DDX_LBStringExact` 일치 하는 컨트롤의 첫 번째 항목 목록 상자 컨트롤에 데이터를 전송 하기 위해 호출 *값* 을 선택 합니다. (전체 항목 보다는 방금 접두사 일치를 사용 하 여 [DDX_LBString](#ddx_lbstring).) 일치 하는 항목이 있으면 항목이 선택 됩니다. 일치 하는 것은 대/소문자 구분 합니다.  
  
 때 `DDX_CBStringExact` 목록 상자 컨트롤에서 데이터를 전송 하기 위해 호출 *값* 현재 목록 상자 선택으로 설정 됩니다. 선택 된 항목이 경우 *값* 길이가 0 인 문자열로 설정 됩니다.  
  
> [!NOTE]
>  목록 상자는 드롭다운 목록 상자 인 경우 교환 값은 255 자로 제한 됩니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="ddx_monthcalctrl"></a>  DDX_MonthCalCtrl  
 `DDX_MonthCalCtrl` 함수 month calendar 컨트롤 간의 날짜 데이터의 전송을 관리 ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체 및 중 하나에 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 또는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 데이터 멤버입니다.  
  
```  
void AFXAPI DDX_MonthCalCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    CTime& value);

void AFXAPI DDX_MonthCalCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    COleDateTime& value);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다. 이 개체를 삭제할 필요가 없습니다.  
  
 `nIDC`  
 멤버 변수 연관 된 month calendar 컨트롤의 리소스 ID입니다.  
  
 *값*  
 에 대 한 참조는 `CTime` 또는 `COleDateTime` 멤버 변수 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체 데이터를 교환 합니다.  
  
### <a name="remarks"></a>설명  
  
> [!NOTE]
>  컨트롤에는 날짜 값만 관리합니다. 컨트롤 창의 생성 시간을 반영 하도록 세트나 만큼의 시간에 대 한 호출을 사용 하 여 컨트롤에 설정 된 시간 개체의 시간 필드는 `CMonthCalCtrl::SetCurSel`합니다.  
  
 때 `DDX_MonthCalCtrl` 호출 *값* month calendar 컨트롤의 현재 상태로 설정 됩니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="ddx_radio"></a>  DDX_Radio  
 `DDX_Radio` 함수의 전송을 관리 `int` 대화 상자에 라디오 컨트롤 그룹 간에 데이터 폼 뷰 또는 컨트롤 뷰 개체 및 `int` 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 데이터 멤버입니다. 값은 `int` 데이터 멤버는 그룹 내에서 단추를 선택 된 라디오 단추가 따라 결정 됩니다.  
  
```  
void AFXAPI DDX_Radio(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 그룹의 첫 번째 라디오 컨트롤의 리소스 ID입니다.  
  
 *값*  
 멤버 변수 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체 데이터를 교환에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 때 `DDX_Radio` 호출 *값* 라디오 컨트롤 그룹의 현재 상태로 설정 됩니다. 현재 체크 라디오 컨트롤이의 0 기반 인덱스와 값이 설정 또는 라디오 컨트롤이 없는 경우-1 확인 됩니다.  
  
 첫 번째 라디오 단추 그룹에 있는 경우에 예를 들어 (WS_GROUP 스타일이 적용 된 단추)의 값을 검사는 `int` 등 구성원은 0입니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="ddx_scroll"></a>  DDX_Scroll  
 `DDX_Scroll` 함수의 전송을 관리 `int` 대화 상자에서 스크롤 막대 컨트롤 간의 데이터 폼 뷰 또는 컨트롤 뷰 개체 및 `int` 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 데이터 멤버입니다.  
  
```  
void AFXAPI DDX_Scroll(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 스크롤 막대 컨트롤에 연결 된 컨트롤 속성의 리소스 ID입니다.  
  
 *값*  
 데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.  
  
### <a name="remarks"></a>설명  
 때 `DDX_Scroll` 호출 *값* 컨트롤의 위치 조정 컨트롤의 현재 위치를 설정 합니다. 컨트롤의 위치 조정 컨트롤의 현재 위치와 관련 된 값에 대 한 자세한 내용은 참조 하십시오. [GetScrollPos](http://msdn.microsoft.com/library/windows/desktop/bb787585) Windows sdk에서입니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="ddx_slider"></a>  DDX_Slider  
 `DDX_Slider` 함수의 전송을 관리 `int` 대화 상자나 폼 보기에서 슬라이더 컨트롤 간에 데이터 및 `int` 대화 상자나 폼 뷰 개체의 데이터 멤버입니다.  
  
```  
void AFXAPI DDX_Slider(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 슬라이더 컨트롤의 리소스 ID입니다.  
  
 *값*  
 교환할 값에 대 한 참조입니다. 이 매개 변수를 보유 하거나 슬라이더 컨트롤의 현재 위치를 설정 합니다.  
  
### <a name="remarks"></a>설명  
 때 `DDX_Slider` 호출 *값* 컨트롤의 스크롤 상자의 현재 위치를 설정 또는 값 수신한 교환의 방향에 따라 위치 합니다.  
  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다. 슬라이더 컨트롤에 대 한 정보를 참조 하십시오. [CSliderCtrl 사용 하 여](../../mfc/using-csliderctrl.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="ddx_text"></a>  DDX_Text  
 `DDX_Text` 함수의 전송을 관리 `int`, **UINT**, **긴**, `DWORD`, `CString`, **float**, 또는  **이중** 대화 상자에서 편집 컨트롤 간의 데이터 폼 보기, 또는 컨트롤 뷰 및 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 데이터 멤버입니다.  
  
```  
void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    BYTE& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    short& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    UINT& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    long& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    DWORD& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    float& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    double& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    COleCurrency& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    COleDateTime& value);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 `nIDC`  
 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체에 있는 편집 컨트롤의 ID입니다.  
  
 *값*  
 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 데이터 멤버에 대 한 참조입니다. 데이터 형식이 *값* 는 오버 로드 된 버전에 따라 달라 집니다 `DDX_Text` 사용 합니다.  
  
### <a name="remarks"></a>설명  
 DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  

### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  

## <a name="see-also"></a>참고 항목  
 [표준 대화 상자 데이터 유효성 검사 루틴](../../mfc/reference/standard-dialog-data-validation-routines.md)   
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
