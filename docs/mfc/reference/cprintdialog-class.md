---
title: CPrintDialog 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPrintDialog
- AFXDLGS/CPrintDialog
- AFXDLGS/CPrintDialog::CPrintDialog
- AFXDLGS/CPrintDialog::CreatePrinterDC
- AFXDLGS/CPrintDialog::DoModal
- AFXDLGS/CPrintDialog::GetCopies
- AFXDLGS/CPrintDialog::GetDefaults
- AFXDLGS/CPrintDialog::GetDeviceName
- AFXDLGS/CPrintDialog::GetDevMode
- AFXDLGS/CPrintDialog::GetDriverName
- AFXDLGS/CPrintDialog::GetFromPage
- AFXDLGS/CPrintDialog::GetPortName
- AFXDLGS/CPrintDialog::GetPrinterDC
- AFXDLGS/CPrintDialog::GetToPage
- AFXDLGS/CPrintDialog::PrintAll
- AFXDLGS/CPrintDialog::PrintCollate
- AFXDLGS/CPrintDialog::PrintRange
- AFXDLGS/CPrintDialog::PrintSelection
- AFXDLGS/CPrintDialog::m_pd
dev_langs:
- C++
helpviewer_keywords:
- CPrintDialog [MFC], CPrintDialog
- CPrintDialog [MFC], CreatePrinterDC
- CPrintDialog [MFC], DoModal
- CPrintDialog [MFC], GetCopies
- CPrintDialog [MFC], GetDefaults
- CPrintDialog [MFC], GetDeviceName
- CPrintDialog [MFC], GetDevMode
- CPrintDialog [MFC], GetDriverName
- CPrintDialog [MFC], GetFromPage
- CPrintDialog [MFC], GetPortName
- CPrintDialog [MFC], GetPrinterDC
- CPrintDialog [MFC], GetToPage
- CPrintDialog [MFC], PrintAll
- CPrintDialog [MFC], PrintCollate
- CPrintDialog [MFC], PrintRange
- CPrintDialog [MFC], PrintSelection
- CPrintDialog [MFC], m_pd
ms.assetid: 5bdb2424-adf8-433d-a97c-df11a83bc4e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 842565b460ff88ae70d108bc1b1db71b22674eb2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cprintdialog-class"></a>CPrintDialog 클래스
Windows 공용 대화 상자에서 인쇄용으로 제공하는 서비스를 캡슐화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CPrintDialog : public CCommonDialog  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CPrintDialog::CPrintDialog](#cprintdialog)|`CPrintDialog` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CPrintDialog::CreatePrinterDC](#createprinterdc)|인쇄 대화 상자를 표시 하지 않고 프린터 장치 컨텍스트를 만듭니다.|  
|[CPrintDialog::DoModal](#domodal)|대화 상자를 표시 하 고 사용자는 선택할 수 있습니다.|  
|[CPrintDialog::GetCopies](#getcopies)|요청 된 복사본 수를 검색 합니다.|  
|[CPrintDialog::GetDefaults](#getdefaults)|대화 상자를 표시 하지 않고 장치 기본값을 검색 합니다.|  
|[CPrintDialog::GetDeviceName](#getdevicename)|현재 선택 된 프린터 장치 이름을 검색합니다.|  
|[CPrintDialog::GetDevMode](#getdevmode)|검색 된 `DEVMODE` 구조입니다.|  
|[CPrintDialog::GetDriverName](#getdrivername)|현재 선택 된 프린터 드라이버의 이름을 검색합니다.|  
|[CPrintDialog::GetFromPage](#getfrompage)|인쇄 범위의 시작 페이지를 검색합니다.|  
|[CPrintDialog::GetPortName](#getportname)|현재 선택 된 프린터 포트의 이름을 검색합니다.|  
|[CPrintDialog::GetPrinterDC](#getprinterdc)|프린터 장치 컨텍스트에 대 한 핸들을 검색합니다.|  
|[CPrintDialog::GetToPage](#gettopage)|인쇄 범위의 끝 페이지를 검색합니다.|  
|[CPrintDialog::PrintAll](#printall)|문서의 모든 페이지가 인쇄를 결정 합니다.|  
|[CPrintDialog::PrintCollate](#printcollate)|복사 요청 된 데이터 정렬 된 여부를 확인 합니다.|  
|[CPrintDialog::PrintRange](#printrange)|지정된 된 범위의 페이지 인쇄할지 여부를 결정 합니다.|  
|[CPrintDialog::PrintSelection](#printselection)|현재 선택한 항목에만 인쇄할지 여부를 결정 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CPrintDialog::m_pd](#m_pd)|사용자 지정 하는 데 사용 되는 구조는 `CPrintDialog` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 일반 인쇄 대화 상자에는 Windows 표준와 동일한 방식으로 인쇄 및 인쇄 설정 대화 상자를 구현 하는 쉬운 방법을 제공 합니다.  
  
> [!NOTE]
>  `CPrintDialogEx` 클래스는 Windows 인쇄 속성 시트에서 제공 하는 서비스를 캡슐화 합니다. 자세한 내용은 참조는 [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md) 개요입니다.  
  
 `CPrintDialog`기능에 따라 대체는 [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md), 둘 다 인쇄 설정 및 페이지 설정에 대 한 일반 대화 상자 제공 하도록 디자인 된 합니다.  
  
 응용 프로그램에 대 한 인쇄 프로세스의 여러 측면을 처리 하기 위해 프레임 워크에 사용할 수 있습니다. 이 경우 프레임 워크에는 인쇄를 위한 Windows 공용 대화 상자를 자동으로 표시 됩니다. 응용 프로그램에 대 한 인쇄 프레임 워크 핸들이 하지만 직접 인쇄 대화 상자와 일반 인쇄 대화 상자를 재정의할 수 있습니다. 프레임 워크를 사용 하 여 인쇄 작업을 처리 하는 방법에 대 한 자세한 내용은 문서 참조 [인쇄](../../mfc/printing.md)합니다.  
  
 프레임 워크의 개입 없이도 인쇄를 처리 하도록 응용 프로그램을 원하는 경우 사용할 수 있습니다는 `CPrintDialog` "있는 그대로" 제공, 생성자 또는 사용자 고유의 대화 상자 클래스에서 파생 시킬 수 있습니다 `CPrintDialog` 필요에 따라 생성자 작성 하 고 있습니다. 어떤 경우 든 이러한 대화 상자는 처럼 동작 표준 MFC 대화 상자 클래스에서 파생 되기 때문에 `CCommonDialog`합니다.  
  
 사용 하는 `CPrintDialog` 개체를 사용 하 여 개체를 만들려면 먼저는 `CPrintDialog` 생성자입니다. 대화 상자를 생성 되 면이 설정 하거나의 모든 값을 수정할 수 있습니다는 [m_pd](#m_pd) 대화 상자의 컨트롤의 값을 초기화 하는 구조입니다. `m_pd` 형식의 구조는 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843)합니다. 이 구조에 대 한 자세한 내용은 Windows SDK를 참조 하십시오.  
  
 핸들의 제공 하지 않으면 `m_pd` 에 대 한는 **hDevMode** 및 **hDevNames** 멤버를 Windows 함수를 호출 해야 **작업** 이러한 핸들에 대 한 완료 한 경우 대화 상자와 합니다. 제공 하는 프레임 워크의 인쇄 설정 구현을 사용 하는 경우 `CWinApp::OnFilePrintSetup`, 이러한 핸들을 해제 해야 합니다. 핸들에서 유지 관리 `CWinApp` 에서 해제 되 고 `CWinApp`의 소멸자입니다. 사용 하는 경우 이러한 핸들을 해제 해야 하는 `CPrintDialog` 독립 실행형 합니다.  
  
 대화 상자 컨트롤을 초기화 한 다음 호출에서 `DoModal` 대화 상자를 표시 하 고 사용자가 인쇄 옵션을 선택 하도록 허용 하려면 멤버 함수입니다. `DoModal` 사용자는 확인 선택 여부를 반환 합니다 ( **IDOK**) 또는 취소 ( **IDCANCEL**) 단추입니다.  
  
 경우 `DoModal` 반환 **IDOK**, 중 하나를 사용 `CPrintDialog`의 사용자가 입력 정보를 검색 하는 멤버 함수입니다.  
  
 `CPrintDialog::GetDefaults` 멤버 함수는 대화 상자를 표시 하지 않고 현재 프린터 기본값을 검색 하는 데 유용 합니다. 이 멤버 함수는 사용자 개입이 필요합니다.  
  
 Windows를 사용할 수 있습니다 **CommDlgExtendedError** 함수는 오류에 대 한 자세한 내용을 보려면 및 대화 상자를 초기화 하는 동안 오류가 발생 한 것인지 확인 합니다. 이 함수에 대 한 자세한 내용은 Windows SDK를 참조 하십시오.  
  
 `CPrintDialog` COMMDLG에 의존합니다. Windows 버전 3.1 이상와 함께 제공 되는 DLL 파일입니다.  
  
 대화 상자를 사용자 지정 하려면 클래스를 파생 `CPrintDialog`, 사용자 지정 대화 상자 템플릿을 제공 하 고 확장 된 컨트롤에서 알림 메시지를 처리 한 메시지 맵을 추가 합니다. 처리 되지 않은 모든 메시지는 기본 클래스 전달 되어야 합니다. 후크 함수를 사용자 지정 필요 하지 않습니다.  
  
 인쇄 또는 인쇄 설정 대화 상자가 표시 되는 인지에 따라 다르게 동일한 메시지를 처리 하려면 각 대화 상자에 대 한 클래스를 파생 해야 합니다. Windows 재정의 해야 **AttachOnSetup** 인쇄 대화 상자 내에서 인쇄 설정 단추를 선택 하면 새 대화 상자가의 생성을 처리 하는 함수입니다.  
  
 사용 하 여 대 한 자세한 내용은 `CPrintDialog`, 참조 [일반 대화 상자 클래스](../../mfc/common-dialog-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPrintDialog`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdlgs.h  
  
##  <a name="cprintdialog"></a>  CPrintDialog::CPrintDialog  
 Windows 인쇄 또는 인쇄 설정 대화 상자 개체를 생성합니다.  
  
```  
CPrintDialog(
    BOOL bPrintSetupOnly,  
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS | PD_HIDEPRINTTOFILE | PD_NOSELECTION,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `bPrintSetupOnly`  
 표준 Windows 인쇄 대화 상자 또는 인쇄 설정 대화 상자 표시 되는지 여부를 지정 합니다. 이 매개 변수를 설정 **TRUE** 표준 Windows 인쇄 설정 대화 상자를 표시 합니다. 로 설정 **FALSE** Windows 인쇄 대화 상자를 표시 합니다. 경우 `bPrintSetupOnly` 은 **FALSE**, 인쇄 설정 옵션 단추는 인쇄 대화 상자에 계속 표시 됩니다.  
  
 `dwFlags`  
 하나 이상의 플래그 비트 OR 연산자를 사용 하 여 결합 대화 상자에서 설정을 사용자 지정 하는 데 사용할 수 있습니다. 예를 들어는 **PD_ALLPAGES** 플래그의 기본 인쇄 범위는 문서의 모든 페이지를 설정 합니다. 참조는 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) 이러한 플래그에 대 한 자세한 내용은 Windows SDK에는 구조입니다.  
  
 `pParentWnd`  
 대화 상자의 부모 또는 소유자 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는만 개체를 생성 합니다. 사용 된 `DoModal` 멤버 함수 대화 상자를 표시 합니다.  
  
 로 생성자를 호출할 때 `bPrintSetupOnly` 로 설정 **FALSE**, **PD_RETURNDC** 플래그 자동으로 사용 됩니다. 호출한 후 `DoModal`, `GetDefaults`, 또는 `GetPrinterDC`, 프린터 DC에서 반환할 `m_pd.hDC`합니다. 이 DC에 대 한 호출으로 해제 해야 [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) 호출자에 의해 `CPrintDialog`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#174](../../mfc/codesnippet/cpp/cprintdialog-class_1.cpp)]  
  
##  <a name="createprinterdc"></a>  CPrintDialog::CreatePrinterDC  
 프린터 장치 컨텍스트 (DC)를 만듭니다.는 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) 및 [DEVNAMES](../../mfc/reference/devnames-structure.md) 구조입니다.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>반환 값  
 새로 만든된 프린터 장치 컨텍스트에 대 한 핸들입니다.  
  
### <a name="remarks"></a>설명  
 이 DC는 DC를 현재 프린터 하 프린터 Dc 사용자가 삭제 해야 다른 모든 이전에 가져온. 이 함수를 호출 하 고 현재까지 인쇄 대화 상자를 표시 하지 않고 결과 DC를 사용 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#106](../../mfc/codesnippet/cpp/cprintdialog-class_2.cpp)]  
  
##  <a name="domodal"></a>  CPrintDialog::DoModal  
 Windows 일반 인쇄 대화 상자를 표시 하 고 페이지 범위를 사본 수와 같은 다양 한 인쇄 옵션을 선택할 수 있도록 복사본 대조해 야 해야 하는지 여부 및 합니다.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>반환 값  
 **IDOK** 또는 **IDCANCEL**합니다. 경우 **IDCANCEL** 은 Windows 호출 반환 [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) 함수 오류가 발생 한 것인지 확인 합니다.  
  
 **IDOK** 및 **IDCANCEL** 는 사용자 확인 또는 취소 단추를 선택 하는지 여부를 나타내는 상수입니다.  
  
### <a name="remarks"></a>설명  
 멤버를 설정 하 여 다양 한 인쇄 대화 상자 옵션을 초기화 하려는 경우는 `m_pd` 구조를 호출 하기 전에이 작업을 수행 해야 `DoModal`, 대화 상자 개체를 생성 한 후 하지만 합니다.  
  
 호출한 후 `DoModal`, 다른 멤버를 설정 또는 사용자가 정보 입력 대화 상자에 검색 함수를 호출할 수 있습니다.  
  
 로 생성자를 호출할 때 `bPrintSetupOnly` 로 설정 **FALSE**, **PD_RETURNDC** 플래그 자동으로 사용 됩니다. 호출한 후 `DoModal`, `GetDefaults`, 또는 `GetPrinterDC`, 프린터 DC에서 반환할 `m_pd.hDC`합니다. 이 DC에 대 한 호출으로 해제 해야 [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) 호출자에 의해 `CPrintDialog`합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CPrintDialog::CreatePrinterDC](#createprinterdc)합니다.  
  
##  <a name="getcopies"></a>  CPrintDialog::GetCopies  
 요청 된 복사본 수를 검색 합니다.  
  
```  
int GetCopies() const;  
```  
  
### <a name="return-value"></a>반환 값  
 요청한 복사본 수입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 호출한 후 호출 `DoModal` 를 요청한 복사본 수를 검색 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CPrintDialog::PrintCollate](#printcollate)합니다.  
  
##  <a name="getdefaults"></a>  CPrintDialog::GetDefaults  
 대화 상자를 표시 하지 않고 기본 프린터의 장치 기본값을 검색 합니다.  
  
```  
BOOL GetDefaults();
```  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 검색 된 값이에 포함 된 `m_pd` 구조입니다.  
  
 일부 경우에서는이 함수에 대 한 호출 호출는 [생성자](#cprintdialog) 에 대 한 `CPrintDialog` 와 `bPrintSetupOnly` 로 설정 **FALSE**합니다. 이러한 경우 프린터 DC 및 **hDevNames** 및 **hDevMode** (두 개의 핸들에 있는 `m_pd` 데이터 멤버) 자동으로 할당 되 합니다.  
  
 경우에 대 한 생성자 `CPrintDialog` 로 호출 했습니다 `bPrintSetupOnly` 로 설정 **FALSE**,이 함수는만 반환 되지 **hDevNames** 및 **hDevMode** (위치: **m_pd.hDevNames** 및 **m_pd.hDevMode**) 호출자에 게에 있는 프린터 DC도 반환 하지만 **m_pd.hDC**합니다. 호출자가 프린터 DC를 삭제 하 고 Windows를 호출 하는 작업은 [작업](http://msdn.microsoft.com/library/windows/desktop/aa366579) 작업이 종료 된 경우 핸들에 대해 함수는 `CPrintDialog` 개체입니다.  
  
### <a name="example"></a>예제  
 이 코드 조각은 기본 프린터 장치 컨텍스트를 가져오고 인치당 도트 수 프린터 해상도 사용자에 게 보고 합니다. (프린터의 기능의이 특성은 라고도 DPI입니다.)  
  
 [!code-cpp[NVC_MFCDocView#107](../../mfc/codesnippet/cpp/cprintdialog-class_3.cpp)]  
  
##  <a name="getdevicename"></a>  CPrintDialog::GetDeviceName  
 현재 선택 된 프린터 장치 이름을 검색합니다.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 선택 된 프린터의 이름입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 호출한 후 호출 [DoModal](#domodal) 호출한 후 또는 현재 선택 된 프린터의 이름을 검색 하지 [GetDefaults](#getdefaults) 를 기본 프린터의 현재 장치 기본값을 검색 합니다. 에 대 한 포인터를 사용 하 여는 `CString` 에서 반환 된 개체 `GetDeviceName` 의 값으로 `lpszDeviceName` 호출에서 [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)합니다.  
  
### <a name="example"></a>예제  
 이 코드 조각은 사용자의 기본 프린터 이름 및 프린터를 사용 하 여 스풀러 이름과 함께, 연결 된 포트를 보여 줍니다. 코드 라고 표시 하는 메시지 상자가 표시 될 수 있습니다 "기본 프린터는 HP LaserJet IIIP \\\server\share winspool.를 사용 하 여" 예.  
  
 [!code-cpp[NVC_MFCDocView#108](../../mfc/codesnippet/cpp/cprintdialog-class_4.cpp)]  
  
##  <a name="getdevmode"></a>  CPrintDialog::GetDevMode  
 검색 된 `DEVMODE` 구조입니다.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) 장치 초기화 및 인쇄 드라이버의 환경에 대 한 정보가 포함 된 데이터 구조입니다. Windows 사용 하 여이 구조에서 사용 되는 메모리의 잠금을 해제 해야 [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) 함수는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 호출한 후 호출 [DoModal](#domodal) 또는 [GetDefaults](#getdefaults) 인쇄 장치에 대 한 정보를 검색 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CPrintDialog::PrintCollate](#printcollate)합니다.  
  
##  <a name="getdrivername"></a>  CPrintDialog::GetDriverName  
 현재 선택 된 프린터 드라이버의 이름을 검색합니다.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A `CString` 드라이버 시스템 정의 이름을 지정 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 호출한 후 호출 [DoModal](#domodal) 또는 [GetDefaults](#getdefaults) 시스템에서 정의 된 프린터 장치 드라이버의 이름을 검색할 수 있습니다. 에 대 한 포인터를 사용 하 여는 `CString` 에서 반환 된 개체 `GetDriverName` 의 값으로 `lpszDriverName` 호출에서 [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CPrintDialog::GetDeviceName](#getdevicename)합니다.  
  
##  <a name="getfrompage"></a>  CPrintDialog::GetFromPage  
 인쇄 범위의 시작 페이지를 검색합니다.  
  
```  
int GetFromPage() const;  
```  
  
### <a name="return-value"></a>반환 값  
 시작 페이지 범위에 페이지 수가 크기로 인쇄 됩니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 호출한 후 호출 `DoModal` 를 인쇄할 페이지 범위에 시작 페이지 번호를 검색 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CPrintDialog::m_pd](#m_pd)합니다.  
  
##  <a name="getportname"></a>  CPrintDialog::GetPortName  
 현재 선택 된 프린터 포트의 이름을 검색합니다.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 선택 된 프린터 포트의 이름입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 호출한 후 호출 [DoModal](#domodal) 또는 [GetDefaults](#getdefaults) 를 현재 선택 된 프린터 포트의 이름을 검색 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CPrintDialog::GetDeviceName](#getdevicename)합니다.  
  
##  <a name="getprinterdc"></a>  CPrintDialog::GetPrinterDC  
 프린터 장치 컨텍스트에 대 한 핸들을 검색합니다.  
  
```  
HDC GetPrinterDC() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 프린터 장치 컨텍스트에 대 한 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 경우는 `bPrintSetupOnly` 의 매개 변수는 `CPrintDialog` 생성자가 **FALSE** (인쇄 대화 상자가 표시 되는지를 나타내는), 다음 `GetPrinterDC` 프린터 장치 컨텍스트에 대 한 핸들을 반환 합니다. Windows를 호출 해야 [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) 완료 되 면 장치 컨텍스트를 삭제 하는 함수 사용 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#109](../../mfc/codesnippet/cpp/cprintdialog-class_5.cpp)]  
  
##  <a name="gettopage"></a>  CPrintDialog::GetToPage  
 인쇄 범위의 끝 페이지를 검색합니다.  
  
```  
int GetToPage() const;  
```  
  
### <a name="return-value"></a>반환 값  
 끝의 페이지 번호 범위에 인쇄할 페이지입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 호출한 후 호출 `DoModal` 를 인쇄할 페이지 범위에서 끝 페이지 번호를 검색 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CPrintDialog::m_pd](#m_pd)합니다.  
  
##  <a name="m_pd"></a>  CPrintDialog::m_pd  
 해당 멤버가 대화 상자 개체의 특성을 저장 하는 구조입니다.  
  
```  
PRINTDLG& m_pd;  
```  
  
### <a name="remarks"></a>설명  
 생성 한 후 한 `CPrintDialog` 개체를 사용할 수 있습니다 `m_pd` 호출 하기 전에 대화 상자의 다양 한 측면을 설정 하는 [DoModal](#domodal) 멤버 함수입니다. 대 한 자세한 내용은 `m_pd` 구조, 참조 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) Windows SDK에서 합니다.  
  
 수정 하는 경우는 `m_pd` 데이터 멤버를 직접 모든 기본 동작을 재정의 하 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#111](../../mfc/codesnippet/cpp/cprintdialog-class_6.cpp)]  
  
##  <a name="printall"></a>  CPrintDialog::PrintAll  
 문서의 모든 페이지가 인쇄를 결정 합니다.  
  
```  
BOOL PrintAll() const;  
```  
  
### <a name="return-value"></a>반환 값  
 문서에서 모든 경우에 0이 아닌 페이지는 크기로 인쇄 됩니다. 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 호출한 후 호출 `DoModal` 인쇄 된 문서의 모든 페이지를 여부를 결정 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CPrintDialog::m_pd](#m_pd)합니다.  
  
##  <a name="printcollate"></a>  CPrintDialog::PrintCollate  
 복사 요청 된 데이터 정렬 된 여부를 확인 합니다.  
  
```  
BOOL PrintCollate() const;  
```  
  
### <a name="return-value"></a>반환 값  
 사용자가 대화 상자의 collate 확인란을 선택 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 호출한 후 호출 `DoModal` 프린터 모든 인쇄 된 문서의 복사본을 병합 해야 하는지 여부를 확인 하려면.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#110](../../mfc/codesnippet/cpp/cprintdialog-class_7.cpp)]  
  
##  <a name="printrange"></a>  CPrintDialog::PrintRange  
 지정된 된 범위의 페이지 인쇄할지 여부를 결정 합니다.  
  
```  
BOOL PrintRange() const;  
```  
  
### <a name="return-value"></a>반환 값  
 경우에 문서에서 페이지 범위 인쇄; 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 호출한 후 호출 `DoModal` 범위는 문서에서 페이지를 인쇄 여부를 결정 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CPrintDialog::m_pd](#m_pd)합니다.  
  
##  <a name="printselection"></a>  CPrintDialog::PrintSelection  
 현재 선택한 항목에만 인쇄할지 여부를 결정 합니다.  
  
```  
BOOL PrintSelection() const;  
```  
  
### <a name="return-value"></a>반환 값  
 인쇄할;에서 선택한 항목은 경우에 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 호출한 후 호출 `DoModal` 현재 선택한 항목만 인쇄 여부를 결정 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CPrintDialog::m_pd](#m_pd)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 DIBLOOK](../../visual-cpp-samples.md)   
 [CCommonDialog 클래스](../../mfc/reference/ccommondialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CPrintInfo 구조체](../../mfc/reference/cprintinfo-structure.md)
