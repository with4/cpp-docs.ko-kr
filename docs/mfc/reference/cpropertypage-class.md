---
title: CPropertyPage 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPropertyPage
- AFXDLGS/CPropertyPage
- AFXDLGS/CPropertyPage::CPropertyPage
- AFXDLGS/CPropertyPage::CancelToClose
- AFXDLGS/CPropertyPage::Construct
- AFXDLGS/CPropertyPage::GetPSP
- AFXDLGS/CPropertyPage::OnApply
- AFXDLGS/CPropertyPage::OnCancel
- AFXDLGS/CPropertyPage::OnKillActive
- AFXDLGS/CPropertyPage::OnOK
- AFXDLGS/CPropertyPage::OnQueryCancel
- AFXDLGS/CPropertyPage::OnReset
- AFXDLGS/CPropertyPage::OnSetActive
- AFXDLGS/CPropertyPage::OnWizardBack
- AFXDLGS/CPropertyPage::OnWizardFinish
- AFXDLGS/CPropertyPage::OnWizardNext
- AFXDLGS/CPropertyPage::QuerySiblings
- AFXDLGS/CPropertyPage::SetModified
- AFXDLGS/CPropertyPage::m_psp
dev_langs:
- C++
helpviewer_keywords:
- CPropertyPage [MFC], CPropertyPage
- CPropertyPage [MFC], CancelToClose
- CPropertyPage [MFC], Construct
- CPropertyPage [MFC], GetPSP
- CPropertyPage [MFC], OnApply
- CPropertyPage [MFC], OnCancel
- CPropertyPage [MFC], OnKillActive
- CPropertyPage [MFC], OnOK
- CPropertyPage [MFC], OnQueryCancel
- CPropertyPage [MFC], OnReset
- CPropertyPage [MFC], OnSetActive
- CPropertyPage [MFC], OnWizardBack
- CPropertyPage [MFC], OnWizardFinish
- CPropertyPage [MFC], OnWizardNext
- CPropertyPage [MFC], QuerySiblings
- CPropertyPage [MFC], SetModified
- CPropertyPage [MFC], m_psp
ms.assetid: d9000a21-aa81-4530-85d9-f43432afb4dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 434a0b428199b7c2298815523517097aeee2ab47
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cpropertypage-class"></a>CPropertyPage 클래스
속성 시트(탭 대화 상자라고도 함)의 개별 페이지를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CPropertyPage : public CDialog  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CPropertyPage::CPropertyPage](#cpropertypage)|`CPropertyPage` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CPropertyPage::CancelToClose](#canceltoclose)|확인 단추를 닫고 읽기를 변경 하 고 모달 속성 시트의 페이지에서 복구할 수 없는 변경 이후 취소 단추를 사용 하지 않도록 설정 합니다.|  
|[CPropertyPage::Construct](#construct)|`CPropertyPage` 개체를 생성합니다. 사용 하 여 `Construct` 실행 시 매개 변수를 지정 하려는 경우 또는 배열을 사용 하는 경우.|  
|[CPropertyPage::GetPSP](#getpsp)|Windows 검색 [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) 와 연결 된 구조는 `CPropertyPage` 개체입니다.|  
|[CPropertyPage::OnApply](#onapply)|지금 적용 단추를 클릭할 때 프레임 워크에서 호출 됩니다.|  
|[CPropertyPage::OnCancel](#oncancel)|취소 단추를 클릭할 때 프레임 워크에서 호출 됩니다.|  
|[CPropertyPage::OnKillActive](#onkillactive)|현재 페이지가 더 이상 활성 페이지가 있을 때 프레임 워크에서 호출 됩니다. 여기에 데이터 유효성 검사를 수행 합니다.|  
|[CPropertyPage::OnOK](#onok)|확인, 지금 적용 또는 [닫기] 단추를 클릭할 때 프레임 워크에서 호출 됩니다.|  
|[CPropertyPage::OnQueryCancel](#onquerycancel)|취소 단추를 클릭할 때 그리고는 취소 작업이 수행 되기 전에 프레임 워크에서 호출 됩니다.|  
|[CPropertyPage::OnReset](#onreset)|취소 단추를 클릭할 때 프레임 워크에서 호출 됩니다.|  
|[CPropertyPage::OnSetActive](#onsetactive)|페이지가 활성 페이지 만들어질 때 프레임 워크에서 호출 됩니다.|  
|[CPropertyPage::OnWizardBack](#onwizardback)|마법사 형식의 속성 시트를 사용 하는 동안 [뒤로] 단추를 클릭할 때 프레임 워크에서 호출 됩니다.|  
|[CPropertyPage::OnWizardFinish](#onwizardfinish)|마법사 형식의 속성 시트를 사용 하는 동안 "마침" 단추를 클릭할 때 프레임 워크에서 호출 됩니다.|  
|[CPropertyPage::OnWizardNext](#onwizardnext)|마법사 형식의 속성 시트를 사용 하는 동안 다음 단추를 클릭할 때 프레임 워크에서 호출 합니다.|  
|[CPropertyPage::QuerySiblings](#querysiblings)|속성 시트의 각 페이지에 메시지를 전달합니다.|  
|[CPropertyPage::SetModified](#setmodified)|호출을 활성화 또는 비활성화 지금 적용 단추입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CPropertyPage::m_psp](#m_psp)|Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) 구조입니다. 기본 속성 페이지 매개 변수에 대 한 액세스를 제공합니다.|  
  
## <a name="remarks"></a>설명  
 표준 대화 상자에서 클래스를 파생 하는 대로 `CPropertyPage` 속성 시트의 각 페이지에 대 한 합니다. 사용 하도록 `CPropertyPage`-파생된 개체를 먼저 만듭니다는 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md) 개체, 한 다음 속성 시트에서 이동 하는 각 페이지에 대 한 개체를 만듭니다. 호출 [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage) 각 시트의 페이지 하 고 호출 하 여 속성 시트를 표시 한 다음 [CPropertySheet::DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) 모달 속성 시트에 대 한 또는 [CPropertySheet:: 만들](../../mfc/reference/cpropertysheet-class.md#create) 모덜리스 속성 시트에 대 한 합니다.  
  
 속성 시트의 사용자는 장치를 설정 또는 뉴스레터 만드는 등의 작업 단계를 안내 하는 속성 페이지의 순서와 구성 되는 마법사를 호출 하는 대화 상자의 탭의 형식을 만들 수 있습니다. 마법사 형식의 탭 대화 상자에서 속성 페이지 탭을 사용 하지 않은 하 고 한 번에 하나의 속성 페이지가 표시 됩니다. 또한, 확인 및 지금 적용 단추 대신 마법사 종류 탭 대화 상자에 뒤로 단추, 다음 또는 마침 단추 및 "취소" 단추가 있습니다.  
  
 속성 시트 마법사로 설정에 대 한 자세한 내용은 참조 하십시오. [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)합니다. 사용 하 여 대 한 자세한 내용은 `CPropertyPage` 개체, 문서를 참조 하십시오. [속성 시트 및 속성 페이지](../../mfc/property-sheets-and-property-pages-in-mfc.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CPropertyPage`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdlgs.h  
  
##  <a name="canceltoclose"></a>  CPropertyPage::CancelToClose  
 모달 속성 시트의 페이지의 데이터를 복구할 수 없는 변경 수행 된 후이 함수를 호출 합니다.  
  
```  
void CancelToClose();
```  
  
### <a name="remarks"></a>설명  
 이 함수는 close 확인 단추를 변경 하 고 취소 단추를 사용 하지 않도록 설정 합니다. 이렇게 하면 변경 알림을 영구적 및 수정 내용을 변경이 하다 사용자를 취소할 수 없습니다.  
  
 `CancelToClose` 멤버 함수는 아무 작업도 수행 모덜리스 속성 시트에서 모덜리스 속성 시트를 기본적으로 "취소" 단추가 없기 때문입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CPropertyPage::QuerySiblings](#querysiblings)합니다.  
  
##  <a name="construct"></a>  CPropertyPage::Construct  
 생성 하려면이 멤버 함수 호출을 `CPropertyPage` 개체입니다.  
  
```  
void Construct(
    UINT nIDTemplate,  
    UINT nIDCaption = 0);

 
void Construct(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption = 0);

 
void Construct(
    UINT nIDTemplate,  
    UINT nIDCaption,  
    UINT nIDHeaderTitle,  
    UINT nIDHeaderSubTitle = 0);

 
void Construct(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption,  
    UINT nIDHeaderTitle,  
    UINT nIDHeaderSubTitle = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIDTemplate`  
 이 페이지에 사용 되는 서식 파일의 ID입니다.  
  
 `nIDCaption`  
 이 페이지에 대 한 탭에 배치 될 ID 이름입니다. 0 인 경우,이 페이지에 대 한 대화 상자 템플릿에서 이름이 연결 됩니다.  
  
 `lpszTemplateName`  
 템플릿 리소스의 이름에 해당 하는 null로 끝나는 문자열을 포함 합니다.  
  
 `nIDHeaderTitle`  
 속성 페이지 머리글의 제목 위치에 배치 될 ID 이름입니다. 기본적으로 0입니다.  
  
 `nIDHeaderSubTitle`  
 속성 페이지 머리글의 부제목 위치에 배치 될 ID 이름입니다. 기본적으로 0입니다.  
  
### <a name="remarks"></a>설명  
 개체는 다음 조건이 모두 충족 되 후에 표시 됩니다.  
  
-   페이지 사용 하 여 속성 시트에 추가 된 [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage)합니다.  
  
-   속성 시트의 [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) 또는 [만들기](../../mfc/reference/cpropertysheet-class.md#create) 함수가 호출 되었습니다.  
  
-   사용자가 선택한 (탭)이이 페이지입니다.  
  
 호출 **생성** 호출 되지 않으면가 다른 클래스 생성자 중 하나입니다. `Construct` 멤버 함수는 매개 변수 문을 비워 하 고 다음 코드에서 여러 매개 변수 및 생성 시점을 지정 수 있으므로 유연 합니다.  
  
 사용 해야 `Construct` 배열 작업 시점과 호출 해야 **생성** 배열의 각 멤버에 대 한 데이터 멤버는 적절 한 값을 할당 되도록 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#112](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]  
  
##  <a name="cpropertypage"></a>  CPropertyPage::CPropertyPage  
 `CPropertyPage` 개체를 생성합니다.  
  
```  
CPropertyPage();

 
explicit CPropertyPage(
    UINT nIDTemplate,  
    UINT nIDCaption = 0,  
    DWORD dwSize = sizeof(PROPSHEETPAGE));

 
explicit CPropertyPage(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption = 0,  
    DWORD dwSize = sizeof(PROPSHEETPAGE));

 
CPropertyPage(
    UINT nIDTemplate,  
    UINT nIDCaption,  
    UINT nIDHeaderTitle,  
    UINT nIDHeaderSubTitle = 0,  
    DWORD dwSize = sizeof(PROPSHEETPAGE));

 
CPropertyPage(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption,  
    UINT nIDHeaderTitle,  
    UINT nIDHeaderSubTitle = 0,  
    DWORD dwSize = sizeof(PROPSHEETPAGE));
```  
  
### <a name="parameters"></a>매개 변수  
 `nIDTemplate`  
 이 페이지에 사용 되는 서식 파일의 ID입니다.  
  
 `nIDCaption`  
 이 페이지에 대 한 탭에 배치 될 ID 이름입니다. 0 인 경우,이 페이지에 대 한 대화 상자 템플릿에서 이름이 연결 됩니다.  
  
 `dwSize`  
 `lpszTemplateName`  
 이 페이지에 대 한 서식 파일의 이름을 포함 하는 문자열을 가리킵니다. 일 수 없습니다 **NULL**합니다.  
  
 `nIDHeaderTitle`  
 속성 페이지 머리글의 제목 위치에 배치 될 ID 이름입니다.  
  
 `nIDHeaderSubTitle`  
 속성 페이지 머리글의 부제목 위치에 배치 될 ID 이름입니다.  
  
### <a name="remarks"></a>설명  
 개체는 다음 조건이 모두 충족 되 후에 표시 됩니다.  
  
-   페이지 사용 하 여 속성 시트에 추가 된 [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage)합니다.  
  
-   속성 시트의 [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) 또는 [만들기](../../mfc/reference/cpropertysheet-class.md#create) 함수가 호출 되었습니다.  
  
-   사용자가 선택한 (탭)이이 페이지입니다.  
  
 사용 하 여 (예: 배열을 사용 하는 경우) 여러 매개 변수를 설정한 경우 [CPropertySheet::Construct](../../mfc/reference/cpropertysheet-class.md#construct) 대신 `CPropertyPage`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#113](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]  
  
##  <a name="getpsp"></a>  CPropertyPage::GetPSP  
 Windows 검색 [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) 와 연결 된 구조는 `CPropertyPage` 개체입니다.  
  
```  
const PROPSHEETPAGE& GetPSP() const;  
  
PROPSHEETPAGE& GetPSP();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 참조는 **PROPSHEETPAGE** 구조입니다.  
  
##  <a name="m_psp"></a>  CPropertyPage::m_psp  
 `m_psp` 멤버의 특성을 저장 하는 구조 [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548)합니다.  
  
```  
PROPSHEETPAGE m_psp;  
```  
  
### <a name="remarks"></a>설명  
 이 구조를 사용 하 여 생성 한 후 속성 페이지의 모양을 초기화 합니다.  
  
 해당 멤버의 목록을 포함 하 여이 구조에 대 한 자세한 내용은 참조 **PROPSHEETPAGE** Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#128](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]  
  
##  <a name="onapply"></a>  CPropertyPage::OnApply  
 이 멤버 함수는 확인 이나 지금 적용 단추를 선택 하면 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnApply();
```  
  
### <a name="return-value"></a>반환 값  
 변경 내용을 허용 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크에서이 함수를 호출 하면 속성 시트의 모든 속성 페이지에 대 한 변경 내용을 적용할 속성 시트에 포커스를 유지 하 고 `OnApply` 반환 **TRUE** (값 1). 하기 전에 `OnApply` 호출할 수는 프레임 워크에서 호출 해야 [SetModified](#setmodified) 해당 매개 변수를 설정 하 고 **TRUE**합니다. 그러면 사용자가 속성 페이지에서 변경 하면 즉시 지금 적용 단추를 활성화 됩니다.  
  
 프로그램은 지금 적용 단추를 클릭할 경우 동작을 지정 하려면이 멤버 함수를 재정의 합니다. 함수를 재정의할 때 반환 해야 **TRUE** 변경 내용을 적용할 수 및 **FALSE** 변경 내용이 적용 되지 않게 하려면.  
  
 기본 구현은 `OnApply` 호출 `OnOK`합니다.  
  
 사용자가 속성 시트에는 지금 적용 또는 확인 단추를 누를 때 전송 되는 알림 메시지에 대 한 자세한 내용은 참조 [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CPropertyPage::OnOK](#onok)합니다.  
  
##  <a name="oncancel"></a>  CPropertyPage::OnCancel  
 이 멤버 함수는 취소 단추를 선택할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnCancel();
```  
  
### <a name="remarks"></a>설명  
 취소 단추 동작을 수행 하려면이 멤버 함수를 재정의 합니다. 기본값에 적용 된 변경 내용을 부정 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#114](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]  
  
##  <a name="onkillactive"></a>  CPropertyPage::OnKillActive  
 이 멤버 함수는 페이지가 더 이상 활성 페이지가 있을 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnKillActive();
```  
  
### <a name="return-value"></a>반환 값  
 데이터를 성공적으로 업데이트 한 경우 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 특별 한 데이터 유효성 검사 작업을 수행 하려면이 멤버 함수를 재정의 합니다.  
  
 이 멤버 함수의 기본 구현은 속성 페이지에 있는 컨트롤에서 멤버 변수 속성 페이지의 설정을 복사합니다. 대화 상자 데이터 유효성 검사 (DDV) 오류로 인해 데이터가 성공적으로 업데이트 되지 않았습니다 페이지 포커스를 유지 합니다.  
  
 이 멤버 함수를 성공적으로 반환 된 후 프레임 워크의 페이지를 호출 합니다 [OnOK](#onok) 함수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#115](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]  
  
##  <a name="onok"></a>  CPropertyPage::OnOK  
 이 멤버 함수는 프레임 워크 호출 직후는 확인 또는 지금 적용 단추를 선택 하면 프레임 워크에서 호출 됩니다 [OnKillActive](#onkillactive)합니다.  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>설명  
 프레임 워크 수신 확인 이나 지금 적용 단추 중 하나를 선택 하는 경우는 [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) 속성 페이지에서 알림을 보내도록 합니다. 에 대 한 호출 `OnOK` 호출 하는 경우에 만들 수 없습니다 [CPropertySheet::PressButton](../../mfc/reference/cpropertysheet-class.md#pressbutton) 속성 페이지 알림을 보내지 않습니다는 경우 때문에 있습니다.  
  
 사용자는 전체 속성 시트를 해제할 때 현재 활성 페이지에 대 한 추가 동작을 구현 하려면이 멤버 함수를 재정의 합니다.  
  
 이 멤버 함수의 기본 구현은 페이지에서 데이터를 업데이트를 반영 하도록 "정리"로 표시 된 `OnKillActive` 함수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#116](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]  
  
##  <a name="onquerycancel"></a>  CPropertyPage::OnQueryCancel  
 이 멤버 함수는 취소 하기 전에 작업을 수행한 및 취소 단추를 클릭할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>반환 값  
 반환 **FALSE** 취소 작업 또는 허용 하려면 TRUE를 방지할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 취소 단추를 클릭할 때 프로그램에서 사용 하는 작업을 지정 하려면이 멤버 함수를 재정의 합니다.  
  
 기본 구현은 `OnQueryCancel` 반환 **TRUE**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#117](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]  
  
##  <a name="onreset"></a>  CPropertyPage::OnReset  
 이 멤버 함수는 취소 단추를 선택 하면 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnReset();
```  
  
### <a name="remarks"></a>설명  
 이전에 지금 적용 단추를 선택 하는 사용자가 만든 모든 속성 페이지에 변경 내용이 취소는 프레임 워크에서이 함수를 호출 하면 속성 시트 포커스를 유지 합니다.  
  
 프로그램은 사용자가 "취소" 단추가 클릭 동작을 지정 하려면이 멤버 함수를 재정의 합니다.  
  
 기본 구현은 `OnReset` 는 아무 작업도 수행 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CPropertyPage::OnCancel](#oncancel)합니다.  
  
##  <a name="onsetactive"></a>  CPropertyPage::OnSetActive  
 이 멤버 함수는 페이지는 사용자가 선택 되 고 활성 페이지가 됩니다 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnSetActive();
```  
  
### <a name="return-value"></a>반환 값  
 페이지를 성공적으로 활성화를 설정한 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 페이지가 활성화 될 때 작업을 수행 하려면이 멤버 함수를 재정의 합니다. 이 멤버 함수 재정의 하면 일반적으로 기본 버전 페이지 컨트롤을 새 데이터로 업데이트할 수 있도록 데이터 멤버를 업데이트 한 후에 호출 됩니다.  
  
 기본 구현은 페이지에 대 한 창을 만듭니다. 그렇지 않은 경우 이전에 만든 고 활성 페이지가 있습니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CPropertySheet::SetFinishText](../../mfc/reference/cpropertysheet-class.md#setfinishtext)합니다.  
  
##  <a name="onwizardback"></a>  CPropertyPage::OnWizardBack  
 이 멤버 함수는 사용자가 마법사에서 뒤로 단추를 클릭할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual LRESULT OnWizardBack();
```  
  
### <a name="return-value"></a>반환 값  
 자동으로 다음 페이지로 이동 하는 0 변경할 수 없도록 하려면 페이지-1입니다. 다음 중이 아닌 페이지 점프할 표시할 대화의 식별자를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 사용자는 뒤로 단추를 누를 때 수행 해야 하는 몇 가지 동작을 지정 하려면이 멤버 함수를 재정의 합니다.  
  
 마법사 형식의 속성 시트를 확인 하는 방법에 대 한 자세한 내용은 참조 하십시오. [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#118](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]  
  
##  <a name="onwizardfinish"></a>  CPropertyPage::OnWizardFinish  
 이 멤버 함수는 사용자가 마법사에서 "마침" 단추를 클릭할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>반환 값  
 마법사를 완료 합니다; 속성 시트 손상 된 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 사용자가 클릭할 때는 **마침** 이 함수를 호출 하는 프레임 워크는 마법사에서 단추 때 `OnWizardFinish` 반환 **TRUE** (0이 아닌 값) 속성 시트 소멸 될 예정 수 (하지만 실제로 제거 됨). 호출 `DestroyWindow` 속성 시트를 제거할 수 있습니다. 호출 하지 마십시오 `DestroyWindow` 에서 `OnWizardFinish`; 그렇게 하면 힙 손상 또는 기타 오류가 있습니다.  
  
 사용자는 "마침" 단추를 누를 때 수행 해야 하는 몇 가지 동작을 지정 하려면이 멤버 함수를 재정의할 수 있습니다. 이 함수를 재정의할 때 반환 **FALSE** 속성 시트 제거 되 고 하지 못하도록 합니다.  
  
 사용자가 마법사 속성 시트에서 "마침" 단추를 누를 때 전송 되는 알림 메시지에 대 한 자세한 내용은 참조 [PSN_WIZFINISH](http://msdn.microsoft.com/library/windows/desktop/bb774571) Windows sdk에서입니다.  
  
 마법사 형식의 속성 시트를 확인 하는 방법에 대 한 자세한 내용은 참조 하십시오. [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#119](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#120](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#121](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#122](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]  
  
##  <a name="onwizardnext"></a>  CPropertyPage::OnWizardNext  
 이 멤버 함수는 사용자가 마법사에서 다음 단추를 클릭할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual LRESULT OnWizardNext();
```  
  
### <a name="return-value"></a>반환 값  
 자동으로 다음 페이지로 이동 하는 0 변경할 수 없도록 하려면 페이지-1입니다. 다음 중이 아닌 페이지 점프할 표시할 대화의 식별자를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 다음 단추를 누를 때 수행 되어야 하는 몇 가지 동작을 지정 하려면이 멤버 함수를 재정의 합니다.  
  
 마법사 형식의 속성 시트를 확인 하는 방법에 대 한 자세한 내용은 참조 하십시오. [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#123](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]  
  
##  <a name="querysiblings"></a>  CPropertyPage::QuerySiblings  
 속성 시트의 각 페이지에 메시지를 전달 하려면이 멤버 함수를 호출 합니다.  
  
```  
LRESULT QuerySiblings(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>매개 변수  
 `wParam`  
 추가 메시지 종속 정보를 지정 합니다.  
  
 `lParam`  
 추가 메시지 종속 정보를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 값의 속성 시트 또는 인 경우 0에 있는 페이지에서 모든 페이지 값이 0 반환합니다.  
  
### <a name="remarks"></a>설명  
 속성 시트는 0이 아닌 값을 반환 하는 페이지의 후속 페이지에 메시지를 보내지 않습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#124](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#125](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#126](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]  
  
##  <a name="setmodified"></a>  CPropertyPage::SetModified  
 지금 적용 단추를 적절 한 외부 개체의 속성 페이지에서 설정을 적용 여부에 따라 사용 하지 않도록 설정 하거나 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bChanged`  
 **True 이면** 속성 페이지 설정; 적용 된 마지막 시간 이후 수정 된 것을 나타내기 위해 **FALSE** 속성 페이지 설정을 적용 하지 또는 무시할지를 나타내는입니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크 유지 트랙의 페이지는 "더티" 즉, 속성 페이지를 호출한 **SetModified (TRUE)** 합니다. 지금 적용 단추 호출 하는 경우에 항상 사용할 수 **SetModified (TRUE)** 페이지 중 하나에 대 한 합니다. 호출 하는 경우 지금 적용 단추가 비활성화 됩니다 **SetModified (FALSE)** 만 하는 경우 다른 페이지는 "더티"입니다. 하지만 페이지 중 하나에 대 한  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#127](../../mfc/codesnippet/cpp/cpropertypage-class_17.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 CMNCTRL1](../../visual-cpp-samples.md)   
 [MFC 샘플 CMNCTRL2](../../visual-cpp-samples.md)   
 [MFC 샘플 PROPDLG](../../visual-cpp-samples.md)   
 [MFC 샘플 SNAPVW](../../visual-cpp-samples.md)   
 [CDialog 클래스](../../mfc/reference/cdialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CPropertySheet 클래스](../../mfc/reference/cpropertysheet-class.md)   
 [CDialog 클래스](../../mfc/reference/cdialog-class.md)
