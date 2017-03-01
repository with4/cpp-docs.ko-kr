---
title: "CPrintDialogEx 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPrintDialogEx
dev_langs:
- C++
helpviewer_keywords:
- Print Setup dialog box
- CPrintDialogEx class
- Print dialog box
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
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
ms.openlocfilehash: 8dc8f01eef42b54af18ed07520d547768c931748
ms.lasthandoff: 02/24/2017

---
# <a name="cprintdialogex-class"></a>CPrintDialogEx 클래스
Windows 2000 인쇄 속성 시트에서 제공하는 서비스를 캡슐화합니다.  
  
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
|[CPrintDialogEx::DoModal](#domodal)|대화 상자를 표시 하 고 선택할 수 있습니다.|  
|[CPrintDialogEx::GetCopies](#getcopies)|요청 된 복사본 수를 검색 합니다.|  
|[CPrintDialogEx::GetDefaults](#getdefaults)|대화 상자를 표시 하지 않고 장치 기본값을 검색 합니다.|  
|[CPrintDialogEx::GetDeviceName](#getdevicename)|현재 선택 된 프린터 장치의 이름을 검색합니다.|  
|[CPrintDialogEx::GetDevMode](#getdevmode)|검색 된 `DEVMODE` 구조입니다.|  
|[CPrintDialogEx::GetDriverName](#getdrivername)|시스템에서 정의 된 프린터 장치 드라이버의 이름을 검색합니다.|  
|[CPrintDialogEx::GetPortName](#getportname)|현재 선택 된 프린터 포트의 이름을 검색합니다.|  
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|프린터 장치 컨텍스트에 대 한 핸들을 검색합니다.|  
|[CPrintDialogEx::PrintAll](#printall)|문서 인쇄를 결정 합니다.|  
|[CPrintDialogEx::PrintCollate](#printcollate)|복사본 요청 된 데이터가 정렬 여부를 확인 합니다.|  
|[CPrintDialogEx::PrintCurrentPage](#printcurrentpage)|현재 페이지 문서 인쇄를 결정 합니다.|  
|[CPrintDialogEx::PrintRange](#printrange)|지정된 된 범위의 페이지 인쇄할지 여부를 결정 합니다.|  
|[CPrintDialogEx::PrintSelection](#printselection)|현재 선택한 항목만 인쇄 여부를 결정 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CPrintDialogEx::m_pdex](#m_pdex)|사용자 지정 하는 데 사용 되는 구조는 `CPrintDialogEx` 개체입니다.|  
  
## <a name="remarks"></a>주의  
 응용 프로그램에 대 한 인쇄 프로세스의 여러 측면을 처리 하는 프레임 워크에 사용할 수 있습니다. 프레임 워크를 사용 하 여 인쇄 작업을 처리 하는 방법에 대 한 자세한 내용은 문서를 참조 하십시오. [인쇄](../../mfc/printing.md)합니다.  
  
 프레임 워크의 개입 없이도 인쇄를 처리 하도록 응용 프로그램을 원하는 경우 사용할 수 있습니다는 `CPrintDialogEx` "있는 그대로" 제공, 생성자 또는에서 고유한 대화 상자 클래스를 파생 시킬 수 있습니다 `CPrintDialogEx` 요구 사항에 맞게 생성자 작성 하 고 있습니다. 두 경우 모두 이러한 대화 상자는 처럼 동작 표준 MFC 대화 상자 클래스에서 파생 되므로 `CCommonDialog`합니다.  
  
 사용 하는 `CPrintDialogEx` 개체를 사용 하 여 개체를 만들려면 먼저는 `CPrintDialogEx` 생성자입니다. 대화 상자를 생성 한 후이 설정 하거나 모든 값을 수정할 수 있습니다는 [m_pdex](#m_pdex) 대화 상자의 컨트롤의 값을 초기화 하는 구조입니다. `m_pdex` 형식의 구조는 [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844)합니다. 이 구조에 대 한 자세한 내용은 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 고유한 핸들을 제공 하지 않는 경우 `m_pdex` 에 대 한는 **hDevMode** 및 **hDevNames** 멤버 Windows 함수를 호출 해야 **GlobalFree** 대화 상자에서 완료 되 면 이러한 핸들에 대 한 합니다.  
  
 대화 상자 컨트롤을 초기화 한 후 호출 하는 `DoModal` 멤버 함수를 대화 상자를 표시 하 고 인쇄 옵션을 선택 하는 데 사용할 수 있습니다. 때 `DoModal` 반환, 사용자 확인, 적용 또는 취소 단추를 선택 하는지 여부를 확인할 수 있습니다.  
  
 사용자가 확인을 사용 하면 `CPrintDialogEx`의 사용자가 입력 한 정보를 검색 하는 멤버 함수입니다.  
  
 `CPrintDialogEx::GetDefaults` 멤버 함수는 대화 상자를 표시 하지 않고 현재 프린터 기본값을 검색 하는 데 유용 합니다. 이 메서드는 사용자 개입이 필요합니다.  
  
 창을 사용 하 여 **CommDlgExtendedError** 대화 상자의 초기화 하는 동안 오류가 발생 했는지 여부를 확인 하 고 오류에 대 한 자세한 내용을 보려면 함수입니다. 이 함수에 대 한 자세한 내용은 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
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
  
##  <a name="a-namecprintdialogexa--cprintdialogexcprintdialogex"></a><a name="cprintdialogex"></a>CPrintDialogEx::CPrintDialogEx  
 Windows 2000 인쇄 속성 시트를 생성합니다.  
  
```  
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwFlags`  
 하나 이상의 플래그 비트 OR 연산자를 사용 하 여 결합 대화 상자에서 설정을 사용자 지정 하는 데 사용할 수 있습니다. 예를 들어는 **PD_ALLPAGES** 문서의 모든 페이지에 기본 인쇄 범위를 설정 하는 플래그입니다. 참조는 [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 이러한 플래그에 대 한 자세한 내용은 합니다.  
  
 `pParentWnd`  
 이 대화 상자의 부모 또는 소유자 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는만 개체를 생성 합니다. 사용 된 `DoModal` 멤버 함수는 대화 상자를 표시 합니다.  
  
##  <a name="a-namecreateprinterdca--cprintdialogexcreateprinterdc"></a><a name="createprinterdc"></a>CPrintDialogEx::CreatePrinterDC  
 프린터 장치 컨텍스트 (DC)에서 만듭니다는 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) 및 [DEVNAMES](../../mfc/reference/devnames-structure.md) 구조입니다.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>반환 값  
 새로 만든된 프린터 장치 컨텍스트에 대 한 핸들입니다.  
  
### <a name="remarks"></a>주의  
 반환 된 DC에 저장 되어는 **hDC** 소속 [m_pdex](#m_pdex)합니다.  
  
 이 DC 현재 프린터 DC로 간주 됩니다 및 다른 모든 Dc를 삭제 해야 하는 프린터를 이전에 구현 합니다. 이 함수를 호출 하 고 적 인쇄 대화 상자를 표시 하지 않고 결과 DC를 사용 합니다.  
  
##  <a name="a-namedomodala--cprintdialogexdomodal"></a><a name="domodal"></a>CPrintDialogEx::DoModal  
 Windows 2000 공통 인쇄 속성 시트를 표시 하 고 사용자 페이지 범위 복사본의 수와 같은 다양 한 인쇄 옵션을 선택할 수 있도록 하려면이 함수를 호출 및 복사본 데이터가 정렬 되어야 합니다.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>반환 값  
 INT_PTR 값은 실제로 HRESULT를 반환 합니다. 반환 값 섹션을 참조 [PrintDlgEx](http://msdn.microsoft.com/library/windows/desktop/ms646942) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 멤버를 설정 하 여 다양 한 인쇄 대화 상자 옵션을 초기화 하려는 경우는 `m_pdex` 구조를 호출 하기 전에이 작업을 수행 해야 `DoModal`, 대화 상자 개체를 생성 한 후 하지만 합니다.  
  
 호출한 후 `DoModal`, 다른 멤버 대화 상자에 설정 또는 사용자가 입력 한 정보를 검색 하는 함수를 호출할 수 있습니다.  
  
 경우는 **PD_RETURNDC** 플래그 호출할 때 사용 되 `DoModal`, 프린터 DC에 반환 되는 **hDC** 소속 [m_pdex](#m_pdex). 이 DC에 대 한 호출으로 해제 해야 [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) 호출자에 의해 `CPrintDialogEx`합니다.  
  
##  <a name="a-namegetcopiesa--cprintdialogexgetcopies"></a><a name="getcopies"></a>CPrintDialogEx::GetCopies  
 이 함수를 호출한 후 호출 `DoModal` 요청한 복사본 수를 검색할 수 있습니다.  
  
```  
int GetCopies() const;  
```  
  
### <a name="return-value"></a>반환 값  
 요청 된 복사본의 수입니다.  
  
##  <a name="a-namegetdefaultsa--cprintdialogexgetdefaults"></a><a name="getdefaults"></a>CPrintDialogEx::GetDefaults  
 대화 상자를 표시 하지 않고 기본 프린터의 장치 기본값을 검색 하려면이 함수를 호출 합니다.  
  
```  
BOOL GetDefaults();
```  
  
### <a name="return-value"></a>반환 값  
 **TRUE** 성공 하 고, 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 프린터 장치 컨텍스트 (DC)에서 만듭니다는 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) 및 [DEVNAMES](../../mfc/reference/devnames-structure.md) 구조입니다.  
  
 `GetDefaults`인쇄 속성 시트를 표시 하지 않습니다. 대신, 설정의 **hDevNames** 및 **hDevMode** 의 멤버 [m_pdex](#m_pdex) 에 대 한 핸들을는 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) 및 [DEVNAMES](../../mfc/reference/devnames-structure.md) 시스템 기본 프린터에 대해 초기화 하는 구조입니다. 둘 다 **hDevNames** 및 **hDevMode** null, 또는 `GetDefaults` 실패 합니다.  
  
 하는 경우는 **PD_RETURNDC** 플래그가 설정 되 면이 반환 되지 것입니다만 **hDevNames** 및 **hDevMode** (에 **m_pdex.hDevNames** 및 **m_pdex.hDevMode**) 호출자에 게 프린터 DC에도 반환 하지만 **m_pdex.hDC**합니다. DC 프린터를 삭제 하 고 Windows를 호출 하려면 호출자의 책임 [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579) 완료 된 경우 핸들에 대해 함수는 `CPrintDialogEx` 개체입니다.  
  
##  <a name="a-namegetdevicenamea--cprintdialogexgetdevicename"></a><a name="getdevicename"></a>CPrintDialogEx::GetDeviceName  
 이 함수를 호출한 후 호출 [DoModal](#domodal) 호출한 후 또는 현재 선택 된 프린터의 이름을 검색 하 [GetDefaults](#getdefaults) 기본 프린터의 이름을 검색할 수 있습니다.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 선택 된 프린터의 이름입니다.  
  
### <a name="remarks"></a>주의  
 에 대 한 포인터를 사용 하 여는 `CString` 에서 반환 된 개체 `GetDeviceName` 의 값으로 `lpszDeviceName` 에 대 한 호출에서 [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)합니다.  
  
##  <a name="a-namegetdevmodea--cprintdialogexgetdevmode"></a><a name="getdevmode"></a>CPrintDialogEx::GetDevMode  
 이 함수를 호출한 후 호출 [DoModal](#domodal) 또는 [GetDefaults](#getdefaults) 인쇄 장치에 대 한 정보를 검색 합니다.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) 장치 초기화 및 인쇄 드라이버의 환경에 대 한 정보가 포함 된 데이터 구조입니다. 이 구조는 windows에서 사용 되는 메모리를 잠금 해제 해야 [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) 에 설명 된 함수는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetdrivernamea--cprintdialogexgetdrivername"></a><a name="getdrivername"></a>CPrintDialogEx::GetDriverName  
 이 함수를 호출한 후 호출 [DoModal](#domodal) 또는 [GetDefaults](#getdefaults) 시스템에서 정의 된 프린터 장치 드라이버의 이름을 검색할 수 있습니다.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A `CString` 드라이버 시스템 정의 이름을 지정 합니다.  
  
### <a name="remarks"></a>주의  
 에 대 한 포인터를 사용 하 여는 `CString` 에서 반환 된 개체 `GetDriverName` 의 값으로 `lpszDriverName` 에 대 한 호출에서 [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)합니다.  
  
##  <a name="a-namegetportnamea--cprintdialogexgetportname"></a><a name="getportname"></a>CPrintDialogEx::GetPortName  
 이 함수를 호출한 후 호출 [DoModal](#domodal) 또는 [GetDefaults](#getdefaults) 현재 선택 된 프린터 포트의 이름을 검색할 수 있습니다.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 선택 된 프린터 포트의 이름입니다.  
  
##  <a name="a-namegetprinterdca--cprintdialogexgetprinterdc"></a><a name="getprinterdc"></a>CPrintDialogEx::GetPrinterDC  
 프린터 장치 컨텍스트에 대 한 핸들을 반환합니다.  
  
```  
HDC GetPrinterDC() const;  
```  
  
### <a name="return-value"></a>반환 값  
 프린터 장치 컨텍스트의 핸들입니다.  
  
### <a name="remarks"></a>주의  
 Windows를 호출 해야 [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) 완료 되 면 장치 컨텍스트를 삭제 하려면 함수를 사용 합니다.  
  
##  <a name="a-namempdexa--cprintdialogexmpdex"></a><a name="m_pdex"></a>CPrintDialogEx::m_pdex  
 대화 상자 개체의 특성을 저장 하는 구성원으로 포함 하는 PRINTDLGEX 구조입니다.  
  
```  
PRINTDLGEX m_pdex;  
```  
  
### <a name="remarks"></a>주의  
 생성 한 후 한 `CPrintDialogEx` 개체를 사용할 수 있습니다 `m_pdex` 호출 하기 전에 대화 상자의 다양 한 측면을 설정 하는 [DoModal](#domodal) 멤버 함수입니다. 대 한 자세한 내용은 `m_pdex` 구조체를 참조 하십시오. [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 수정 하는 경우는 `m_pdex` 데이터 멤버를 직접 모든 기본 동작을 재정의 하 합니다.  
  
##  <a name="a-nameprintalla--cprintdialogexprintall"></a><a name="printall"></a>CPrintDialogEx::PrintAll  
 이 함수를 호출한 후 호출 `DoModal` 문서에서 모든 페이지를 인쇄 하려면 여부를 결정 합니다.  
  
```  
BOOL PrintAll() const;  
```  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 문서의 모든 페이지가 인쇄 되 고, 그렇지 않으면 되 면 **FALSE**합니다.  
  
##  <a name="a-nameprintcollatea--cprintdialogexprintcollate"></a><a name="printcollate"></a>CPrintDialogEx::PrintCollate  
 이 함수를 호출한 후 호출 `DoModal` 프린터 문서의 모든 인쇄 된 복사본 collate 해야 하는지 여부를 확인 하려면.  
  
```  
BOOL PrintCollate() const;  
```  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 사용자가 대화 상자에서 collate 확인란을 선택 하는 경우 그렇지 않으면 **FALSE**합니다.  
  
##  <a name="a-nameprintcurrentpagea--cprintdialogexprintcurrentpage"></a><a name="printcurrentpage"></a>CPrintDialogEx::PrintCurrentPage  
 이 함수를 호출한 후 호출 `DoModal` 문서에서 현재 페이지를 인쇄할 여부를 결정 합니다.  
  
```  
BOOL PrintCurrentPage() const;  
```  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 경우 **현재 페이지 인쇄** 인쇄 대화 상자에서 선택 하 고, 그렇지 않으면 **FALSE**합니다.  
  
##  <a name="a-nameprintrangea--cprintdialogexprintrange"></a><a name="printrange"></a>CPrintDialogEx::PrintRange  
 이 함수를 호출한 후 호출 `DoModal` 만 문서에는 페이지 범위 인쇄 여부를 결정 합니다.  
  
```  
BOOL PrintRange() const;  
```  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 문서에서 페이지 범위 인쇄 하 고 그렇지 않으면만 경우 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 지정한 페이지 범위를 확인할 수 있는 [m_pdex](#m_pdex) (참조 **nPageRanges**, **nMaxPageRanges**, 및 **lpPageRanges** 에 [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]).  
  
##  <a name="a-nameprintselectiona--cprintdialogexprintselection"></a><a name="printselection"></a>CPrintDialogEx::PrintSelection  
 이 함수를 호출한 후 호출 `DoModal` 현재 선택한 항목만 인쇄 여부를 결정 합니다.  
  
```  
BOOL PrintSelection() const;  
```  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 인쇄 하 고 그렇지 않으면에서 선택한 항목은 하나만 **FALSE**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CCommonDialog 클래스](../../mfc/reference/ccommondialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CPrintInfo 구조체](../../mfc/reference/cprintinfo-structure.md)

