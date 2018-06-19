---
title: CPrintDialogEx 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPrintDialogEx
- AFXDLGS/CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CreatePrinterDC
- AFXDLGS/CPrintDialogEx::DoModal
- AFXDLGS/CPrintDialogEx::GetCopies
- AFXDLGS/CPrintDialogEx::GetDefaults
- AFXDLGS/CPrintDialogEx::GetDeviceName
- AFXDLGS/CPrintDialogEx::GetDevMode
- AFXDLGS/CPrintDialogEx::GetDriverName
- AFXDLGS/CPrintDialogEx::GetPortName
- AFXDLGS/CPrintDialogEx::GetPrinterDC
- AFXDLGS/CPrintDialogEx::PrintAll
- AFXDLGS/CPrintDialogEx::PrintCollate
- AFXDLGS/CPrintDialogEx::PrintCurrentPage
- AFXDLGS/CPrintDialogEx::PrintRange
- AFXDLGS/CPrintDialogEx::PrintSelection
- AFXDLGS/CPrintDialogEx::m_pdex
dev_langs:
- C++
helpviewer_keywords:
- CPrintDialogEx [MFC], CPrintDialogEx
- CPrintDialogEx [MFC], CreatePrinterDC
- CPrintDialogEx [MFC], DoModal
- CPrintDialogEx [MFC], GetCopies
- CPrintDialogEx [MFC], GetDefaults
- CPrintDialogEx [MFC], GetDeviceName
- CPrintDialogEx [MFC], GetDevMode
- CPrintDialogEx [MFC], GetDriverName
- CPrintDialogEx [MFC], GetPortName
- CPrintDialogEx [MFC], GetPrinterDC
- CPrintDialogEx [MFC], PrintAll
- CPrintDialogEx [MFC], PrintCollate
- CPrintDialogEx [MFC], PrintCurrentPage
- CPrintDialogEx [MFC], PrintRange
- CPrintDialogEx [MFC], PrintSelection
- CPrintDialogEx [MFC], m_pdex
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7f511eb1414a5cd5e22b9a3e05f81caef15b908e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376648"
---
# <a name="cprintdialogex-class"></a>CPrintDialogEx 클래스
Windows의 인쇄 속성 시트에서 제공 하는 서비스를 캡슐화 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CPrintDialogEx : public CCommonDialog  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CPrintDialogEx::CPrintDialogEx](#cprintdialogex)|`CPrintDialogEx` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|인쇄 대화 상자를 표시 하지 않고 프린터 장치 컨텍스트를 만듭니다.|  
|[CPrintDialogEx::DoModal](#domodal)|대화 상자를 표시 및 선택할 수 있습니다.|  
|[CPrintDialogEx::GetCopies](#getcopies)|요청 된 복사본 수를 검색 합니다.|  
|[CPrintDialogEx::GetDefaults](#getdefaults)|대화 상자를 표시 하지 않고 장치 기본값을 검색 합니다.|  
|[CPrintDialogEx::GetDeviceName](#getdevicename)|현재 선택 된 프린터 장치 이름을 검색합니다.|  
|[CPrintDialogEx::GetDevMode](#getdevmode)|검색 된 `DEVMODE` 구조입니다.|  
|[CPrintDialogEx::GetDriverName](#getdrivername)|시스템에서 정의 된 프린터 장치 드라이버의 이름을 검색합니다.|  
|[CPrintDialogEx::GetPortName](#getportname)|현재 선택 된 프린터 포트의 이름을 검색합니다.|  
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|프린터 장치 컨텍스트에 대 한 핸들을 검색합니다.|  
|[CPrintDialogEx::PrintAll](#printall)|문서의 모든 페이지가 인쇄를 결정 합니다.|  
|[CPrintDialogEx::PrintCollate](#printcollate)|복사 요청 된 데이터 정렬 된 여부를 확인 합니다.|  
|[CPrintDialogEx::PrintCurrentPage](#printcurrentpage)|문서의 현재 페이지 인쇄할지 여부를 결정 합니다.|  
|[CPrintDialogEx::PrintRange](#printrange)|지정된 된 범위의 페이지 인쇄할지 여부를 결정 합니다.|  
|[CPrintDialogEx::PrintSelection](#printselection)|현재 선택한 항목에만 인쇄할지 여부를 결정 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CPrintDialogEx::m_pdex](#m_pdex)|사용자 지정 하는 데 사용 되는 구조는 `CPrintDialogEx` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 응용 프로그램에 대 한 인쇄 프로세스의 여러 측면을 처리 하기 위해 프레임 워크에 사용할 수 있습니다. 프레임 워크를 사용 하 여 인쇄 작업을 처리 하는 방법에 대 한 자세한 내용은 문서 참조 [인쇄](../../mfc/printing.md)합니다.  
  
 프레임 워크의 개입 없이도 인쇄를 처리 하도록 응용 프로그램을 원하는 경우 사용할 수 있습니다는 `CPrintDialogEx` "있는 그대로" 제공, 생성자 또는 사용자 고유의 대화 상자 클래스에서 파생 시킬 수 있습니다 `CPrintDialogEx` 필요에 따라 생성자 작성 하 고 있습니다. 어떤 경우 든 이러한 대화 상자는 처럼 동작 표준 MFC 대화 상자 클래스에서 파생 되기 때문에 `CCommonDialog`합니다.  
  
 사용 하는 `CPrintDialogEx` 개체를 사용 하 여 개체를 만들려면 먼저는 `CPrintDialogEx` 생성자입니다. 대화 상자를 생성 되 면이 설정 하거나의 모든 값을 수정할 수 있습니다는 [m_pdex](#m_pdex) 대화 상자의 컨트롤의 값을 초기화 하는 구조입니다. `m_pdex` 형식의 구조는 [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844)합니다. 이 구조에 대 한 자세한 내용은 Windows SDK를 참조 하십시오.  
  
 핸들의 제공 하지 않으면 `m_pdex` 에 대 한는 **hDevMode** 및 **hDevNames** 멤버를 Windows 함수를 호출 해야 **작업** 이러한 핸들에 대 한 완료 한 경우 대화 상자와 합니다.  
  
 대화 상자 컨트롤을 초기화 한 다음 호출에서 `DoModal` 대화 상자를 표시 하 고 사용자가 인쇄 옵션을 선택 하도록 허용 하려면 멤버 함수입니다. 때 `DoModal` 사용자 확인, 적용 또는 취소 단추를 선택 하는지 여부를 확인할 수 있습니다를 반환 합니다.  
  
 사용자가 확인을 사용 하 여 `CPrintDialogEx`의 사용자가 입력 정보를 검색 하는 멤버 함수입니다.  
  
 `CPrintDialogEx::GetDefaults` 멤버 함수는 대화 상자를 표시 하지 않고 현재 프린터 기본값을 검색 하는 데 유용 합니다. 이 메서드는 사용자 개입이 필요합니다.  
  
 Windows를 사용할 수 있습니다 **CommDlgExtendedError** 함수는 오류에 대 한 자세한 내용을 보려면 및 대화 상자를 초기화 하는 동안 오류가 발생 한 것인지 확인 합니다. 이 함수에 대 한 자세한 내용은 Windows SDK를 참조 하십시오.  
  
 사용 하 여 대 한 자세한 내용은 `CPrintDialogEx`, 참조 [일반 대화 상자 클래스](../../mfc/common-dialog-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `IObjectWithSite`  
  
 `IPrintDialogCallback`  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPrintDialogEx`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdlgs.h  
  
##  <a name="cprintdialogex"></a>  CPrintDialogEx::CPrintDialogEx  
 Windows 인쇄 속성 시트를 생성합니다.  
  
```  
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwFlags`  
 하나 이상의 플래그 비트 OR 연산자를 사용 하 여 결합 대화 상자에서 설정을 사용자 지정 하는 데 사용할 수 있습니다. 예를 들어는 **PD_ALLPAGES** 플래그의 기본 인쇄 범위는 문서의 모든 페이지를 설정 합니다. 참조는 [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) 이러한 플래그에 대 한 자세한 내용은 Windows SDK에는 구조입니다.  
  
 `pParentWnd`  
 대화 상자의 부모 또는 소유자 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는만 개체를 생성 합니다. 사용 된 `DoModal` 멤버 함수 대화 상자를 표시 합니다.  
  
##  <a name="createprinterdc"></a>  CPrintDialogEx::CreatePrinterDC  
 프린터 장치 컨텍스트 (DC)를 만듭니다.는 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) 및 [DEVNAMES](../../mfc/reference/devnames-structure.md) 구조입니다.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>반환 값  
 새로 만든된 프린터 장치 컨텍스트에 대 한 핸들입니다.  
  
### <a name="remarks"></a>설명  
 반환 된 DC에 저장 되어는 **hDC** 소속 [m_pdex](#m_pdex)합니다.  
  
 이 DC는 DC를 현재 프린터 하 프린터 Dc를 삭제 해야 다른 모든 이전에 가져온. 이 함수를 호출 하 고 현재까지 인쇄 대화 상자를 표시 하지 않고 결과 DC를 사용 합니다.  
  
##  <a name="domodal"></a>  CPrintDialogEx::DoModal  
 Windows의 인쇄 속성 시트를 표시 하 고 사용자 페이지 범위를 사본 수 등의 다양 한 인쇄 옵션을 선택 하도록 허용 하려면이 함수 호출 및 복사본 대조해 야 해야 하는지 여부.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>반환 값  
 INT_PTR 반환 값은 실제로 HRESULT입니다. 반환 값 섹션을 참조 [PrintDlgEx](http://msdn.microsoft.com/library/windows/desktop/ms646942) Windows sdk에서입니다.  
  
### <a name="remarks"></a>설명  
 멤버를 설정 하 여 다양 한 인쇄 대화 상자 옵션을 초기화 하려는 경우는 `m_pdex` 구조를 호출 하기 전에이 작업을 수행 해야 `DoModal`, 대화 상자 개체를 생성 한 후 하지만 합니다.  
  
 호출한 후 `DoModal`, 다른 멤버를 설정 또는 사용자가 정보 입력 대화 상자에 검색 함수를 호출할 수 있습니다.  
  
 경우는 **PD_RETURNDC** 플래그 호출할 때 사용 되 `DoModal`, 프린터 DC에 반환 됩니다는 **hDC** 소속 [m_pdex](#m_pdex)합니다. 이 DC에 대 한 호출으로 해제 해야 [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) 호출자에 의해 `CPrintDialogEx`합니다.  
  
##  <a name="getcopies"></a>  CPrintDialogEx::GetCopies  
 이 함수를 호출한 후 호출 `DoModal` 를 요청한 복사본 수를 검색 합니다.  
  
```  
int GetCopies() const;  
```  
  
### <a name="return-value"></a>반환 값  
 요청한 복사본 수입니다.  
  
##  <a name="getdefaults"></a>  CPrintDialogEx::GetDefaults  
 대화 상자를 표시 하지 않고 기본 프린터의 장치 기본값을 검색 하려면이 함수를 호출 합니다.  
  
```  
BOOL GetDefaults();
```  
  
### <a name="return-value"></a>반환 값  
 **TRUE** 성공 하 고, 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 프린터 장치 컨텍스트 (DC)를 만듭니다.는 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) 및 [DEVNAMES](../../mfc/reference/devnames-structure.md) 구조입니다.  
  
 `GetDefaults` 인쇄 속성 시트를 표시 하지 않습니다. 대신, 설정는 **hDevNames** 및 **hDevMode** 의 멤버 [m_pdex](#m_pdex) 에 대 한 핸들에는 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) 및 [DEVNAMES ](../../mfc/reference/devnames-structure.md) 시스템 기본 프린터에 대해 초기화 되는 구조입니다. 둘 다 **hDevNames** 및 **hDevMode** null, 또는 `GetDefaults` 실패 합니다.  
  
 경우는 **PD_RETURNDC** 플래그가 설정 되 면이 반환 되지 것입니다만 **hDevNames** 및 **hDevMode** (에 **m_pdex.hDevNames** 및 **m_pdex.hDevMode**) 호출자에 게에 있는 프린터 DC도 반환 하지만 **m_pdex.hDC**합니다. 호출자가 프린터 DC를 삭제 하 고 Windows를 호출 하는 작업은 [작업](http://msdn.microsoft.com/library/windows/desktop/aa366579) 작업이 종료 된 경우 핸들에 대해 함수는 `CPrintDialogEx` 개체입니다.  
  
##  <a name="getdevicename"></a>  CPrintDialogEx::GetDeviceName  
 이 함수를 호출한 후 호출 [DoModal](#domodal) 를 호출한 후 또는 현재 선택 된 프린터의 이름 검색 [GetDefaults](#getdefaults) 기본 프린터의 이름을 검색 하 합니다.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 선택 된 프린터의 이름입니다.  
  
### <a name="remarks"></a>설명  
 에 대 한 포인터를 사용 하 여는 `CString` 에서 반환 된 개체 `GetDeviceName` 의 값으로 `lpszDeviceName` 호출에서 [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)합니다.  
  
##  <a name="getdevmode"></a>  CPrintDialogEx::GetDevMode  
 이 함수를 호출한 후 호출 [DoModal](#domodal) 또는 [GetDefaults](#getdefaults) 인쇄 장치에 대 한 정보를 검색 합니다.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) 장치 초기화 및 인쇄 드라이버의 환경에 대 한 정보가 포함 된 데이터 구조입니다. Windows 사용 하 여이 구조에서 사용 되는 메모리의 잠금을 해제 해야 [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) 함수는 Windows SDK에 설명 되어 있습니다.  
  
##  <a name="getdrivername"></a>  CPrintDialogEx::GetDriverName  
 이 함수를 호출한 후 호출 [DoModal](#domodal) 또는 [GetDefaults](#getdefaults) 시스템에서 정의 된 프린터 장치 드라이버의 이름을 검색할 수 있습니다.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A `CString` 드라이버 시스템 정의 이름을 지정 합니다.  
  
### <a name="remarks"></a>설명  
 에 대 한 포인터를 사용 하 여는 `CString` 에서 반환 된 개체 `GetDriverName` 의 값으로 `lpszDriverName` 호출에서 [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)합니다.  
  
##  <a name="getportname"></a>  CPrintDialogEx::GetPortName  
 이 함수를 호출한 후 호출 [DoModal](#domodal) 또는 [GetDefaults](#getdefaults) 를 현재 선택 된 프린터 포트의 이름을 검색 합니다.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 선택 된 프린터 포트의 이름입니다.  
  
##  <a name="getprinterdc"></a>  CPrintDialogEx::GetPrinterDC  
 프린터 장치 컨텍스트에 대 한 핸들을 반환합니다.  
  
```  
HDC GetPrinterDC() const;  
```  
  
### <a name="return-value"></a>반환 값  
 프린터 장치 컨텍스트 핸들입니다.  
  
### <a name="remarks"></a>설명  
 Windows를 호출 해야 [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) 완료 되 면 장치 컨텍스트를 삭제 하는 함수 사용 합니다.  
  
##  <a name="m_pdex"></a>  CPrintDialogEx::m_pdex  
 대화 상자 개체의 특성을 저장 하는 멤버가 PRINTDLGEX 구조입니다.  
  
```  
PRINTDLGEX m_pdex;  
```  
  
### <a name="remarks"></a>설명  
 생성 한 후 한 `CPrintDialogEx` 개체를 사용할 수 있습니다 `m_pdex` 호출 하기 전에 대화 상자의 다양 한 측면을 설정 하는 [DoModal](#domodal) 멤버 함수입니다. 대 한 자세한 내용은 `m_pdex` 구조, 참조 [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) Windows SDK에서 합니다.  
  
 수정 하는 경우는 `m_pdex` 데이터 멤버를 직접 모든 기본 동작을 재정의 하 합니다.  
  
##  <a name="printall"></a>  CPrintDialogEx::PrintAll  
 이 함수를 호출한 후 호출 `DoModal` 인쇄 된 문서의 모든 페이지를 여부를 결정 합니다.  
  
```  
BOOL PrintAll() const;  
```  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 문서의 모든 페이지가 인쇄 필요가 없으면 경우 **FALSE**합니다.  
  
##  <a name="printcollate"></a>  CPrintDialogEx::PrintCollate  
 이 함수를 호출한 후 호출 `DoModal` 프린터 모든 인쇄 된 문서의 복사본을 병합 해야 하는지 여부를 확인 하려면.  
  
```  
BOOL PrintCollate() const;  
```  
  
### <a name="return-value"></a>반환 값  
 **TRUE** 사용자가 대화 상자의; collate 확인란을 선택 하지 않으면 **FALSE**합니다.  
  
##  <a name="printcurrentpage"></a>  CPrintDialogEx::PrintCurrentPage  
 이 함수를 호출한 후 호출 `DoModal` 문서의 현재 페이지를 인쇄 하려면 여부를 결정 합니다.  
  
```  
BOOL PrintCurrentPage() const;  
```  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 경우 **현재 페이지 인쇄** 인쇄 대화 상자에서 선택 하지 않으면 **FALSE**합니다.  
  
##  <a name="printrange"></a>  CPrintDialogEx::PrintRange  
 이 함수를 호출한 후 호출 `DoModal` 범위는 문서에서 페이지를 인쇄 여부를 결정 합니다.  
  
```  
BOOL PrintRange() const;  
```  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 하는 경우에 문서에서 페이지 범위 인쇄 필요가 없으면 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 지정 된 페이지 범위에서 확인할 수 있는 [m_pdex](#m_pdex) (참조 **nPageRanges**, **nMaxPageRanges**, 및 **lpPageRanges** 는 에서[ PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) Windows SDK의 구조).  
  
##  <a name="printselection"></a>  CPrintDialogEx::PrintSelection  
 이 함수를 호출한 후 호출 `DoModal` 현재 선택한 항목만 인쇄 여부를 결정 합니다.  
  
```  
BOOL PrintSelection() const;  
```  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 만 인쇄 필요가 없으면 선택한 항목이 없으면 **FALSE**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CCommonDialog 클래스](../../mfc/reference/ccommondialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CPrintInfo 구조체](../../mfc/reference/cprintinfo-structure.md)
