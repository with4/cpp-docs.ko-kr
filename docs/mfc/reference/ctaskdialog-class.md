---
title: CTaskDialog 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- CTaskDialog
- AFXTASKDIALOG/CTaskDialog
- AFXTASKDIALOG/CTaskDialog::CTaskDialog
- AFXTASKDIALOG/CTaskDialog::AddCommandControl
- AFXTASKDIALOG/CTaskDialog::AddRadioButton
- AFXTASKDIALOG/CTaskDialog::ClickCommandControl
- AFXTASKDIALOG/CTaskDialog::ClickRadioButton
- AFXTASKDIALOG/CTaskDialog::DoModal
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonCount
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonFlag
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonId
- AFXTASKDIALOG/CTaskDialog::GetOptions
- AFXTASKDIALOG/CTaskDialog::GetSelectedCommandControlID
- AFXTASKDIALOG/CTaskDialog::GetSelectedRadioButtonID
- AFXTASKDIALOG/CTaskDialog::GetVerificationCheckboxState
- AFXTASKDIALOG/CTaskDialog::IsCommandControlEnabled
- AFXTASKDIALOG/CTaskDialog::IsRadioButtonEnabled
- AFXTASKDIALOG/CTaskDialog::IsSupported
- AFXTASKDIALOG/CTaskDialog::LoadCommandControls
- AFXTASKDIALOG/CTaskDialog::LoadRadioButtons
- AFXTASKDIALOG/CTaskDialog::NavigateTo
- AFXTASKDIALOG/CTaskDialog::OnCommandControlClick
- AFXTASKDIALOG/CTaskDialog::OnCreate
- AFXTASKDIALOG/CTaskDialog::OnDestroy
- AFXTASKDIALOG/CTaskDialog::OnExpandButtonClick
- AFXTASKDIALOG/CTaskDialog::OnHelp
- AFXTASKDIALOG/CTaskDialog::OnHyperlinkClick
- AFXTASKDIALOG/CTaskDialog::OnInit
- AFXTASKDIALOG/CTaskDialog::OnNavigatePage
- AFXTASKDIALOG/CTaskDialog::OnRadioButtonClick
- AFXTASKDIALOG/CTaskDialog::OnTimer
- AFXTASKDIALOG/CTaskDialog::OnVerificationCheckboxClick
- AFXTASKDIALOG/CTaskDialog::RemoveAllCommandControls
- AFXTASKDIALOG/CTaskDialog::RemoveAllRadioButtons
- AFXTASKDIALOG/CTaskDialog::SetCommandControlOptions
- AFXTASKDIALOG/CTaskDialog::SetCommonButtonOptions
- AFXTASKDIALOG/CTaskDialog::SetCommonButtons
- AFXTASKDIALOG/CTaskDialog::SetContent
- AFXTASKDIALOG/CTaskDialog::SetDefaultCommandControl
- AFXTASKDIALOG/CTaskDialog::SetDefaultRadioButton
- AFXTASKDIALOG/CTaskDialog::SetDialogWidth
- AFXTASKDIALOG/CTaskDialog::SetExpansionArea
- AFXTASKDIALOG/CTaskDialog::SetFooterIcon
- AFXTASKDIALOG/CTaskDialog::SetFooterText
- AFXTASKDIALOG/CTaskDialog::SetMainIcon
- AFXTASKDIALOG/CTaskDialog::SetMainInstruction
- AFXTASKDIALOG/CTaskDialog::SetOptions
- AFXTASKDIALOG/CTaskDialog::SetProgressBarMarquee
- AFXTASKDIALOG/CTaskDialog::SetProgressBarPosition
- AFXTASKDIALOG/CTaskDialog::SetProgressBarRange
- AFXTASKDIALOG/CTaskDialog::SetProgressBarState
- AFXTASKDIALOG/CTaskDialog::SetRadioButtonOptions
- AFXTASKDIALOG/CTaskDialog::SetVerificationCheckbox
- AFXTASKDIALOG/CTaskDialog::SetVerificationCheckboxText
- AFXTASKDIALOG/CTaskDialog::SetWindowTitle
- AFXTASKDIALOG/CTaskDialog::ShowDialog
- AFXTASKDIALOG/CTaskDialog::TaskDialogCallback
dev_langs:
- C++
helpviewer_keywords:
- CTaskDialog [MFC], CTaskDialog
- CTaskDialog [MFC], AddCommandControl
- CTaskDialog [MFC], AddRadioButton
- CTaskDialog [MFC], ClickCommandControl
- CTaskDialog [MFC], ClickRadioButton
- CTaskDialog [MFC], DoModal
- CTaskDialog [MFC], GetCommonButtonCount
- CTaskDialog [MFC], GetCommonButtonFlag
- CTaskDialog [MFC], GetCommonButtonId
- CTaskDialog [MFC], GetOptions
- CTaskDialog [MFC], GetSelectedCommandControlID
- CTaskDialog [MFC], GetSelectedRadioButtonID
- CTaskDialog [MFC], GetVerificationCheckboxState
- CTaskDialog [MFC], IsCommandControlEnabled
- CTaskDialog [MFC], IsRadioButtonEnabled
- CTaskDialog [MFC], IsSupported
- CTaskDialog [MFC], LoadCommandControls
- CTaskDialog [MFC], LoadRadioButtons
- CTaskDialog [MFC], NavigateTo
- CTaskDialog [MFC], OnCommandControlClick
- CTaskDialog [MFC], OnCreate
- CTaskDialog [MFC], OnDestroy
- CTaskDialog [MFC], OnExpandButtonClick
- CTaskDialog [MFC], OnHelp
- CTaskDialog [MFC], OnHyperlinkClick
- CTaskDialog [MFC], OnInit
- CTaskDialog [MFC], OnNavigatePage
- CTaskDialog [MFC], OnRadioButtonClick
- CTaskDialog [MFC], OnTimer
- CTaskDialog [MFC], OnVerificationCheckboxClick
- CTaskDialog [MFC], RemoveAllCommandControls
- CTaskDialog [MFC], RemoveAllRadioButtons
- CTaskDialog [MFC], SetCommandControlOptions
- CTaskDialog [MFC], SetCommonButtonOptions
- CTaskDialog [MFC], SetCommonButtons
- CTaskDialog [MFC], SetContent
- CTaskDialog [MFC], SetDefaultCommandControl
- CTaskDialog [MFC], SetDefaultRadioButton
- CTaskDialog [MFC], SetDialogWidth
- CTaskDialog [MFC], SetExpansionArea
- CTaskDialog [MFC], SetFooterIcon
- CTaskDialog [MFC], SetFooterText
- CTaskDialog [MFC], SetMainIcon
- CTaskDialog [MFC], SetMainInstruction
- CTaskDialog [MFC], SetOptions
- CTaskDialog [MFC], SetProgressBarMarquee
- CTaskDialog [MFC], SetProgressBarPosition
- CTaskDialog [MFC], SetProgressBarRange
- CTaskDialog [MFC], SetProgressBarState
- CTaskDialog [MFC], SetRadioButtonOptions
- CTaskDialog [MFC], SetVerificationCheckbox
- CTaskDialog [MFC], SetVerificationCheckboxText
- CTaskDialog [MFC], SetWindowTitle
- CTaskDialog [MFC], ShowDialog
- CTaskDialog [MFC], TaskDialogCallback
ms.assetid: 1991ec98-ae56-4483-958b-233809c8c559
caps.latest.revision: 29
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2ebe8b22c0bd05a36f0bcdbfa21ad97105ee1ae2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ctaskdialog-class"></a>CTaskDialog Class
메시지 상자처럼 작동하지만 사용자에게 추가 정보를 표시할 수 있는 팝업 대화 상자입니다. `CTaskDialog` 에는 사용자로부터 정보를 수집하는 기능을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CTaskDialog : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[CTaskDialog::CTaskDialog](#ctaskdialog)|`CTaskDialog` 개체를 생성합니다.|  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[CTaskDialog::AddCommandControl](#addcommandcontrol)|명령 단추 컨트롤을 추가 하는 `CTaskDialog`합니다.|  
|[CTaskDialog::AddRadioButton](#addradiobutton)|라디오 단추를 추가 하는 `CTaskDialog`합니다.|  
|[CTaskDialog::ClickCommandControl](#clickcommandcontrol)|프로그래밍 방식으로 명령 단추 컨트롤 또는 일반 단추를 클릭합니다.|  
|[CTaskDialog::ClickRadioButton](#clickradiobutton)|프로그래밍 방식으로 라디오 단추를 클릭합니다.|  
|[CTaskDialog::DoModal](#domodal)|`CTaskDialog`를 표시합니다.|  
|[CTaskDialog::GetCommonButtonCount](#getcommonbuttoncount)|사용할 수 있는 일반적인 단추 수를 검색합니다.|  
|[CTaskDialog::GetCommonButtonFlag](#getcommonbuttonflag)|Windows 단추를 일반 단추 형식에 연결 된 표준 변환에서 `CTaskDialog` 클래스입니다.|  
|[CTaskDialog::GetCommonButtonId](#getcommonbuttonid)|와 관련 된 일반적인 단추 형식 중 하나를 변환는 `CTaskDialog` 표준 Windows 단추에는 클래스입니다.|  
|[CTaskDialog::GetOptions](#getoptions)|이 대 한 옵션 플래그를 반환 `CTaskDialog`합니다.|  
|[CTaskDialog::GetSelectedCommandControlID](#getselectedcommandcontrolid)|선택한 명령 단추 컨트롤을 반환합니다.|  
|[CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid)|선택 된 라디오 단추를 반환합니다.|  
|[CTaskDialog::GetVerificationCheckboxState](#getverificationcheckboxstate)|확인 확인란의 상태를 검색합니다.|  
|[CTaskDialog::IsCommandControlEnabled](#iscommandcontrolenabled)|명령 단추 컨트롤 또는 일반 단추 사용 되는지 여부를 결정 합니다.|  
|[CTaskDialog::IsRadioButtonEnabled](#isradiobuttonenabled)|라디오 단추를 사용할 수 있는지 여부를 결정 합니다.|  
|[CTaskDialog::IsSupported](#issupported)|응용 프로그램을 실행 하는 컴퓨터를 지원 하는지 여부를 결정은 `CTaskDialog`합니다.|  
|[CTaskDialog::LoadCommandControls](#loadcommandcontrols)|문자열 테이블에서 데이터를 사용 하 여 명령 단추 컨트롤을 추가 합니다.|  
|[CTaskDialog::LoadRadioButtons](#loadradiobuttons)|문자열 테이블에서 데이터를 사용 하 여 라디오 단추를 추가 합니다.|  
|[CTaskDialog::NavigateTo](#navigateto)|포커스를 다른 전송 `CTaskDialog`합니다.|  
|[CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)|명령 단추 컨트롤을 마우스 오른쪽 단추로 클릭할 때 프레임 워크에서이 메서드를 호출 합니다.|  
|[CTaskDialog::OnCreate](#oncreate)|프레임 워크를 만든 후이 메서드는 호출 된 `CTaskDialog`합니다.|  
|[CTaskDialog::OnDestroy](#ondestroy)|제거 하기 전에 즉시 프레임 워크에서이 메서드를 호출는 `CTaskDialog`합니다.|  
|[CTaskDialog::OnExpandButtonClick](#onexpandbuttonclick)|프레임 워크는 사용자가 확장 단추를 클릭할 때이 메서드를 호출 합니다.|  
|[CTaskDialog::OnHelp](#onhelp)|프레임 워크 사용자 도움말을 요청 하는 경우이 메서드를 호출 합니다.|  
|[CTaskDialog::OnHyperlinkClick](#onhyperlinkclick)|프레임 워크는 사용자가 하이퍼링크를 클릭할 때이 메서드를 호출 합니다.|  
|[CTaskDialog::OnInit](#oninit)|이 메서드를 호출 하는 프레임 워크는 경우는 `CTaskDialog` 초기화 됩니다.|  
|[CTaskDialog::OnNavigatePage](#onnavigatepage)|프레임 워크 컨트롤을 고려 하 여 포커스를 이동할 때이 메서드 호출의 `CTaskDialog`합니다.|  
|[CTaskDialog::OnRadioButtonClick](#onradiobuttonclick)|프레임 워크는 사용자가 라디오 단추 컨트롤을 선택할 때이 메서드를 호출 합니다.|  
|[CTaskDialog::OnTimer](#ontimer)|프레임 워크 타이머가 만료 되는 경우이 메서드를 호출 합니다.|  
|[CTaskDialog::OnVerificationCheckboxClick](#onverificationcheckboxclick)|확인 확인란을 두 번 클릭할 때 프레임 워크에서이 메서드를 호출 합니다.|  
|[CTaskDialog::RemoveAllCommandControls](#removeallcommandcontrols)|명령 컨트롤을 모두 제거는 `CTaskDialog`합니다.|  
|[CTaskDialog::RemoveAllRadioButtons](#removeallradiobuttons)|모든 라디오 단추에서 제거 된 `CTaskDialog`합니다.|  
|[CTaskDialog::SetCommandControlOptions](#setcommandcontroloptions)|명령 단추 컨트롤에서 업데이트는 `CTaskDialog`합니다.|  
|[CTaskDialog::SetCommonButtonOptions](#setcommonbuttonoptions)|일반적인 단추를 사용 하도록 설정 하 고 UAC 권한 상승이 필요의 하위 집합을 업데이트 합니다.|  
|[CTaskDialog::SetCommonButtons](#setcommonbuttons)|일반적인 단추를 추가 하는 `CTaskDialog`합니다.|  
|[CTaskDialog::SetContent](#setcontent)|내용을 업데이트는 `CTaskDialog`합니다.|  
|[CTaskDialog::SetDefaultCommandControl](#setdefaultcommandcontrol)|기본 명령 단추 컨트롤을 지정합니다.|  
|[CTaskDialog::SetDefaultRadioButton](#setdefaultradiobutton)|기본 라디오 단추를 지정합니다.|  
|[CTaskDialog::SetDialogWidth](#setdialogwidth)|너비를 조정는 `CTaskDialog`합니다.|  
|[CTaskDialog::SetExpansionArea](#setexpansionarea)|확장 영역을 업데이트는 `CTaskDialog`합니다.|  
|[CTaskDialog::SetFooterIcon](#setfootericon)|업데이트에 대 한 바닥글 아이콘은 `CTaskDialog`합니다.|  
|[CTaskDialog::SetFooterText](#setfootertext)|바닥글에 텍스트를 업데이트 하는 `CTaskDialog`합니다.|  
|[CTaskDialog::SetMainIcon](#setmainicon)|업데이트의 기본 아이콘은 `CTaskDialog`합니다.|  
|[CTaskDialog::SetMainInstruction](#setmaininstruction)|기본 명령 업데이트는 `CTaskDialog`합니다.|  
|[CTaskDialog::SetOptions](#setoptions)|에 대 한 옵션을 구성에서 `CTaskDialog`합니다.|  
|[CTaskDialog::SetProgressBarMarquee](#setprogressbarmarquee)|구성에 대 한 움직이는 텍스트 막대는 `CTaskDialog` 대화 상자에 추가 합니다.|  
|[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)|진행률 표시줄의 위치를 조정 합니다.|  
|[CTaskDialog::SetProgressBarRange](#setprogressbarrange)|진행률 표시줄의 범위를 조정합니다.|  
|[CTaskDialog::SetProgressBarState](#setprogressbarstate)|진행률 표시줄의 상태를 설정 하 고에 표시 된 `CTaskDialog`합니다.|  
|[CTaskDialog::SetRadioButtonOptions](#setradiobuttonoptions)|라디오 단추를 사용 하지 않도록 설정 하거나 사용 합니다.|  
|[CTaskDialog::SetVerificationCheckbox](#setverificationcheckbox)|확인 확인란의 선택된 상태를 설정합니다.|  
|[CTaskDialog::SetVerificationCheckboxText](#setverificationcheckboxtext)|확인 확인란 오른쪽에 텍스트를 설정합니다.|  
|[CTaskDialog::SetWindowTitle](#setwindowtitle)|제목을 설정는 `CTaskDialog`합니다.|  
|[CTaskDialog::ShowDialog](#showdialog)|만들고 표시 한 `CTaskDialog`합니다.|  
|[CTaskDialog::TaskDialogCallback](#taskdialogcallback)|프레임 워크는 다양 한 Windows 메시지에 대 한 응답에서이 호출합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|`m_aButtons`|에 대 한 명령 단추 컨트롤의 배열에서 `CTaskDialog`합니다.|  
|`m_aRadioButtons`|배열에 대 한 라디오 단추 컨트롤은 `CTaskDialog`합니다.|  
|`m_bVerified`|`TRUE` 확인 확인란을 선택; 나타냅니다. `FALSE` 은 의미 합니다.|  
|`m_footerIcon`|아이콘의 바닥글에는 `CTaskDialog`합니다.|  
|`m_hWnd`|에 대 한 창 핸들은 `CTaskDialog`합니다.|  
|`m_mainIcon`|주 아이콘은 `CTaskDialog`합니다.|  
|`m_nButtonDisabled`|일반적인 있는 단추를 나타내는 마스크 비활성화 됩니다.|  
|`m_nButtonElevation`|일반적인 있는 단추를 나타내는 마스크 UAC 권한 상승이 필요 합니다.|  
|`m_nButtonId`|선택한 명령 단추 컨트롤의 ID입니다.|  
|`m_nCommonButton`|일반적인 단추를 나타내는 마스크에 표시 되는 `CTaskDialog`합니다.|  
|`m_nDefaultCommandControl`|명령 단추의 ID를 제어 하는 경우에 선택 되어는 `CTaskDialog` 표시 됩니다.|  
|`m_nDefaultRadioButton`|라디오 단추의 ID를 제어 하는 경우 선택은 `CTaskDialog` 표시 됩니다.|  
|`m_nFlags`|에 대 한 옵션을 나타내는 마스크는 `CTaskDialog`합니다.|  
|`m_nProgressPos`|진행률 표시줄에 대 한 현재 위치입니다.  이 값은 `m_nProgressRangeMin`와 `m_nProgressRangeMax` 사이의 값이어야 합니다.|  
|`m_nProgressRangeMax`|진행률 표시줄에 대 한 최대값입니다.|  
|`m_nProgressRangeMin`|진행률 표시줄에 대 한 최소값입니다.|  
|`m_nProgressState`|진행률 표시줄의 상태입니다. 자세한 내용은 참조 [CTaskDialog::SetProgressBarState](#setprogressbarstate)합니다.|  
|`m_nRadioId`|선택 된 라디오 단추 컨트롤의 ID입니다.|  
|`m_nWidth`|너비는 `CTaskDialog` (픽셀)에서입니다.|  
|`m_strCollapse`|문자열의 `CTaskDialog` 확장 된 정보는 숨겨져 확장 상자 오른쪽에 표시 됩니다.|  
|`m_strContent`|콘텐츠 문자열은 `CTaskDialog`합니다.|  
|`m_strExpand`|문자열의 `CTaskDialog` 확장 된 정보를 표시할 때 확장 상자 오른쪽에 표시 됩니다.|  
|`m_strFooter`|바닥글에는 `CTaskDialog`합니다.|  
|`m_strInformation`|에 대 한 확장 된 정보는 `CTaskDialog`합니다.|  
|`m_strMainInstruction`|기본 명령은 `CTaskDialog`합니다.|  
|`m_strTitle`|제목은 `CTaskDialog`합니다.|  
|`m_strVerification`|문자열 하 고 `CTaskDialog` 확인 확인란 오른쪽에 표시 됩니다.|  
  
## <a name="remarks"></a>설명  
 `CTaskDialog` 클래스는 표준 Windows 메시지 상자를 대체 하 고 사용자 로부터 정보를 수집할 새 컨트롤과 같은 추가 기능도 있습니다. 이 클래스는 MFC 라이브러리의 [!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)]합니다. `CTaskDialog` 는 Windows Vista부터 사용할 수 있습니다. 이전 버전의 Windows 표시할 수 없습니다는 `CTaskDialog` 개체입니다. 사용 하 여 `CTaskDialog::IsSupported` 를 현재 사용자는 작업 대화 상자를 표시할 수 있는지 여부를 런타임에 결정 합니다. 표준 Windows 메시지 상자는에서 계속 지원 [!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)]합니다.  
  
 `CTaskDialog` 를 빌드할 때 응용 프로그램이 유니코드 라이브러리를 사용 하 여 사용할 수 있습니다.  
  
 `CTaskDialog` 서로 다른 두 명의 생성자가 있습니다. 생성자가 하나를 사용 하면 명령 단추 두 개 및 최대 6 개의 일반 단추 컨트롤을 지정할 수 있습니다. 만든 후에 더 많은 명령 단추를 추가할 수는 `CTaskDialog`합니다. 두 번째 생성자는 모든 명령 단추를 지원 하지 않지만 개수에 제한 없이 일반 단추 컨트롤을 추가할 수 있습니다. 생성자에 대 한 자세한 내용은 참조 [CTaskDialog::CTaskDialog](#ctaskdialog)합니다.  
  
 다음 이미지는 예제를 보여 줍니다. `CTaskDialog` 을 일부 컨트롤의 위치를 보여 줍니다.  
  
 ![CTaskDialog의 예](../../mfc/reference/media/ctaskdialogsample.png "ctaskdialogsample")  
CTaskDialog 샘플  
  
## <a name="requirements"></a>요구 사항  
 **필요한 최소 운영 체제:** Windows Vista  
  
 **헤더:** afxtaskdialog.h  
  
##  <a name="addcommandcontrol"></a>  CTaskDialog::AddCommandControl  
 새 명령 단추 컨트롤을 추가 하는 `CTaskDialog`합니다.  
  
```  
void AddCommandControl(
    int nCommandControlID,  
    const CString& strCaption,  
    BOOL bEnabled = TRUE,  
    BOOL bRequiresElevation = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nCommandControlID`  
 명령 컨트롤 id.  
  
 [in] `strCaption`  
 문자열 하 고 `CTaskDialog` 사용자에 게 표시 합니다. 이 문자열을 사용 하 여 명령의 용도 설명 합니다.  
  
 [in] `bEnabled`  
 새 단추 사용 하도록 설정 되거나 해제 되는 경우를 나타내는 부울 매개 변수입니다.  
  
 [in] `bRequiresElevation`  
 명령을 상승 하는지 여부를 나타내는 부울 매개 변수입니다.  
  
### <a name="remarks"></a>설명  
 `CTaskDialog Class` 개수에 제한 없이 명령 단추 컨트롤을 표시할 수 있습니다. 그러나 경우는 `CTaskDialog` 모든 명령 단추 컨트롤에 표시할, 최대 6 개의 단추를 표시할 수 있습니다. 경우는 `CTaskDialog` 에 명령 단추 컨트롤이, 무제한의 단추를 표시할 수 있습니다.  
  
 명령 단추 컨트롤을 선택할 때의 `CTaskDialog` 닫힙니다. 응용 프로그램이 사용 하 여 대화 상자를 표시 하는 경우 [CTaskDialog::DoModal](#domodal), `DoModal` 반환 된 `nCommandControlID` 선택한 명령 단추 컨트롤의 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="addradiobutton"></a>  CTaskDialog::AddRadioButton  
 라디오 단추를 추가 하는 `CTaskDialog`합니다.  
  
```  
void CTaskDialog::AddRadioButton(
    int nRadioButtonID,  
    const CString& strCaption,  
    BOOL bEnabled = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nRadioButtonID`  
 라디오 단추의 id.  
  
 [in] `strCaption`  
 문자열 하 고 `CTaskDialog` 라디오 단추 옆에 표시 됩니다.  
  
 [in] `bEnabled`  
 라디오 단추를 사용할 수 있는지 여부를 나타내는 부울 매개 변수입니다.  
  
### <a name="remarks"></a>설명  
 에 대 한 라디오 단추는 [CTaskDialog 클래스](../../mfc/reference/ctaskdialog-class.md) 사용자 로부터 정보를 수집할 수 있도록 합니다. 함수를 사용 하 여 [CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid) 라디오 단추 선택 되었는지 확인 하려면.  
  
 `CTaskDialog` 것을 요구 하지는 `nRadioButtonID` 매개 변수는 각 라디오 단추에 대해 고유 합니다. 그러나 각 라디오 단추에 대 한 고유 식별자를 사용 하지 않는 경우 예기치 않은 동작이 발생할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="clickcommandcontrol"></a>  CTaskDialog::ClickCommandControl  
 프로그래밍 방식으로 명령 단추 컨트롤 또는 일반 단추를 클릭합니다.  
  
```  
protected:  
void ClickCommandControl(int nCommandControlID) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nCommandControlID`  
 클릭 하 여 컨트롤의 명령 ID입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 windows 메시지 생성 `TDM_CLICK_BUTTON`합니다.  
  
##  <a name="clickradiobutton"></a>  CTaskDialog::ClickRadioButton  
 프로그래밍 방식으로 라디오 단추를 클릭합니다.  
  
```  
protected:  
void ClickRadioButton(int nRadioButtonID) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nRadioButtonID`  
 이 라디오 단추를 클릭 하 여의 ID입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 windows 메시지 생성 `TDM_CLICK_RADIO_BUTTON`합니다.  
  
##  <a name="ctaskdialog"></a>  CTaskDialog::CTaskDialog  
 인스턴스를 만듭니다는 [CTaskDialog 클래스](../../mfc/reference/ctaskdialog-class.md)합니다.  
  
```  
CTaskDialog(
    const CString& strContent,  
    const CString& strMainInstruction,  
    const CString& strTitle,  
    int nCommonButtons = TDCBF_OK_BUTTON | TDCBF_CANCEL_BUTTON,  
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,  
    const CString& strFooter = _T(""));

 
CTaskDialog(
    const CString& strContent,  
    const CString& strMainInstruction,  
    const CString& strTitle,  
    int nIDCommandControlsFirst,  
    int nIDCommandControlsLast,  
    int nCommonButtons,  
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,  
    const CString& strFooter = _T(""));
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `strContent`  
 콘텐츠에 대 한 사용 하는 문자열은 `CTaskDialog`합니다.  
  
 [in] `strMainInstruction`  
 기본 명령은 `CTaskDialog`합니다.  
  
 [in] `strTitle`  
 제목은 `CTaskDialog`합니다.  
  
 [in] `nCommonButtons`  
 에 추가 하는 일반 단추의 마스크는 `CTaskDialog`합니다.  
  
 [in] `nTaskDialogOptions`  
 에 대해 사용할 수 있는 옵션 집합은 `CTaskDialog`합니다.  
  
 [in] `strFooter`  
 바닥글으로 사용할 문자열입니다.  
  
 [in] `nIDCommandControlsFirst`  
 첫 번째 명령은의 문자열 ID입니다.  
  
 [in] `nIDCommandControlsLast`  
 마지막 명령의 문자열 ID입니다.  
  
### <a name="remarks"></a>설명  
 추가할 수 있는 두 가지는 `CTaskDialog` 응용 프로그램에 있습니다. 첫 번째 방법은 만들려는 생성자 중 하나를 사용 하는 `CTaskDialog` 표시를 사용 하 여 [CTaskDialog::DoModal](#domodal)합니다. 정적 함수를 사용 하는 두 번째 방법은 [CTaskDialog::ShowDialog](#showdialog)를 표시할 수 있습니다는 `CTaskDialog` 명시적으로 만들지 않고는 `CTaskDialog` 개체입니다.  
  
 두 번째 생성자는 응용 프로그램의 리소스 파일에서 데이터를 사용 하 여 명령 단추 컨트롤을 만듭니다. 리소스 파일에 문자열 테이블에는 연결된 문자열 Id와 여러 문자열에 있습니다. 이 메서드 간의 문자열 테이블에 유효한 각 항목에 대 한 명령 단추 컨트롤을 추가 `nIDCommandControlsFirst` 및 `nCommandControlsLast`(포함). 이러한 명령 단추 컨트롤에 대 한 문자열 테이블에는 문자열은 컨트롤의 캡션 및 문자열 ID는 컨트롤의 id입니다.  
  
 참조 [CTaskDialog::SetOptions](#setoptions) 사용할 수 있는 옵션의 목록에 대 한 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="domodal"></a>  CTaskDialog::DoModal  
 표시는 `CTaskDialog` 모달로 전환 합니다.  
  
```  
INT_PTR DoModal (HWND hParent = ::GetActiveWindow());
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hParent`  
 에 대 한 부모 창에서 `CTaskDialog`합니다.  
  
### <a name="return-value"></a>반환 값  
 사용자가 선택한 항목에 해당 하는 정수입니다.  
  
### <a name="remarks"></a>설명  
 이 인스턴스를 표시 된 [CTaskDialog](../../mfc/reference/ctaskdialog-class.md)합니다. 그런 다음 응용 프로그램 대화 상자를 닫으려면 사용자에 대 한 대기 합니다.  
  
 `CTaskDialog` 명령 링크 컨트롤, 일반적인 단추를 선택 하거나 닫을 때 닫습니다는 `CTaskDialog`합니다. 반환 값은 사용자 대화 상자를 닫은 방법을 나타내는 식별자입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="getcommonbuttoncount"></a>  CTaskDialog::GetCommonButtonCount  
 일반적인 단추 수를 검색합니다.  
  
```  
int GetCommonButtonCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 사용할 수 있는 일반적인 단추가 수입니다.  
  
### <a name="remarks"></a>설명  
 일반적인 단추를 제공 하는 기본 단추는 [CTaskDialog::CTaskDialog](#ctaskdialog)합니다. [CTaskDialog 클래스](../../mfc/reference/ctaskdialog-class.md) 대화 상자의 아래쪽 단추를 표시 합니다.  
  
 단추의 열거 목록은 CommCtrl.h에 제공 됩니다.  
  
##  <a name="getcommonbuttonflag"></a>  CTaskDialog::GetCommonButtonFlag  
 Windows 단추를 일반 단추 형식에 연결 된 표준 변환에서 [CTaskDialog 클래스](../../mfc/reference/ctaskdialog-class.md)합니다.  
  
```  
int GetCommonButtonFlag(int nButtonId) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nButtonId`  
 표준 Windows 단추 값입니다.  
  
### <a name="return-value"></a>반환 값  
 해당 값 `CTaskDialog` 일반 단추입니다. 해당 공통 단추가 없는 경우이 메서드는 0을 반환 합니다.  
  
##  <a name="getcommonbuttonid"></a>  CTaskDialog::GetCommonButtonId  
 와 관련 된 일반적인 단추 형식 중 하나를 변환의 [CTaskDialog 클래스](../../mfc/reference/ctaskdialog-class.md) 표준 Windows 단추를 합니다.  
  
```  
int GetCommonButtonId(int nFlag);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nFlag`  
 와 관련 된 일반적인 단추 종류는 `CTaskDialog` 클래스입니다.  
  
### <a name="return-value"></a>반환 값  
 해당 표준 Windows 단추의 값입니다. 해당 Windows 단추 없는 경우 메서드가 0을 반환 합니다.  
  
##  <a name="getoptions"></a>  CTaskDialog::GetOptions  
 이 대 한 옵션 플래그를 반환 `CTaskDialog`합니다.  
  
```  
int GetOptions() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 플래그는 `CTaskDialog`합니다.  
  
### <a name="remarks"></a>설명  
 사용할 수 있는 옵션에 대 한 자세한 내용은 [CTaskDialog 클래스](../../mfc/reference/ctaskdialog-class.md), 참조 [CTaskDialog::SetOptions](#setoptions)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="getselectedcommandcontrolid"></a>  CTaskDialog::GetSelectedCommandControlID  
 선택한 명령 단추 컨트롤을 반환합니다.  
  
```  
int GetSelectedCommandControlID() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 선택 된 명령 단추 컨트롤의 ID입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 사용자가 선택한 명령 단추의 ID를 검색할 필요가 없습니다. 해당 ID가 다음과 같은 방법으로 반환 됩니다. [CTaskDialog::DoModal](#domodal) 또는 [CTaskDialog::ShowDialog](#showdialog)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="getselectedradiobuttonid"></a>  CTaskDialog::GetSelectedRadioButtonID  
 선택 된 라디오 단추를 반환합니다.  
  
```  
int GetSelectedRadioButtonID() const;  
```  
  
### <a name="return-value"></a>반환 값  
 선택 된 라디오 단추의 ID입니다.  
  
### <a name="remarks"></a>설명  
 사용자 선택 된 라디오 단추를 검색할 수 있는 대화 상자를 닫은 후이 메서드를 사용할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="getverificationcheckboxstate"></a>  CTaskDialog::GetVerificationCheckboxState  
 확인 확인란의 상태를 검색합니다.  
  
```  
BOOL GetVerificationCheckboxState() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 확인란을 선택한 경우 `FALSE` 없는 경우.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="iscommandcontrolenabled"></a>  CTaskDialog::IsCommandControlEnabled  
 명령 단추 컨트롤 또는 단추 사용 되는지 여부를 결정 합니다.  
  
```  
BOOL IsCommandControlEnabled(int nCommandControlID) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nCommandControlID`  
 테스트 명령 단추 컨트롤 또는 단추의 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 컨트롤이 활성화 되 면 `FALSE` 없는 경우.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 모두 명령 단추 컨트롤의 가용성과의 공통 단추를 결정 하는 `CTaskDialog Class`합니다.  
  
 경우 `nCommandControlID` 는 올바른 식별자가 아닌 중 하나에 대 한 공통 `CTaskDialog` 단추나 명령 단추 컨트롤이이 메서드에서 예외를 throw 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="isradiobuttonenabled"></a>  CTaskDialog::IsRadioButtonEnabled  
 라디오 단추를 사용할 수 있는지 여부를 결정 합니다.  
  
```  
BOOL IsRadioButtonEnabled(int nRadioButtonID) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nRadioButtonID`  
 테스트 라디오 단추의 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 라디오 단추를 사용 하는 경우 `FALSE` 없는 경우.  
  
### <a name="remarks"></a>설명  
 경우 `nRadioButtonID` 유효한 식별자가 아닙니다 라디오 단추에 대 한이 메서드는 예외를 throw 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="issupported"></a>  CTaskDialog::IsSupported  
 응용 프로그램을 실행 하는 컴퓨터를 지원 하는지 여부를 결정은 `CTaskDialog`합니다.  
  
```  
static BOOL IsSupported();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 컴퓨터에서 지원 되는 경우는 `CTaskDialog`; `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>설명  
 이 함수를 사용 하 여 응용 프로그램을 실행 하는 컴퓨터에서 지 원하는 경우 런타임 시 결정 하는 `CTaskDialog Class`합니다. 컴퓨터를 지원 하지 않는 경우는 `CTaskDialog`, 사용자에 게 정보를 전달 하는 또 다른 방법을 제공 해야 합니다. 사용 하려는 경우 응용 프로그램 작동이 중단 됩니다는 `CTaskDialog` 지원 하지 않는 컴퓨터에는 `CTaskDialog` 클래스입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]  
  
##  <a name="loadcommandcontrols"></a>  CTaskDialog::LoadCommandControls  
 문자열 테이블에서 데이터를 사용 하 여 명령 단추 컨트롤을 추가 합니다.  
  
```  
void LoadCommandControls(
    int nIDCommandControlsFirst,  
    int nIDCommandControlsLast);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIDCommandControlsFirst`  
 첫 번째 명령은의 문자열 ID입니다.  
  
 [in] `nIDCommandControlsLast`  
 마지막 명령의 문자열 ID입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 응용 프로그램의 리소스 파일에서 데이터를 사용 하 여 명령 단추 컨트롤을 만듭니다. 리소스 파일에 문자열 테이블에는 연결된 문자열 Id와 여러 문자열에 있습니다. 이 메서드를 사용 하 여 추가 된 새로운 명령 단추 컨트롤에 대 한 컨트롤의 id입니다. 컨트롤의 캡션 및 문자열 ID에 대 한 문자열을 사용 선택 하는 문자열의 범위에서 제공 `nIDCommandControlsFirst` 및 `nCommandControlsLast`(포함). 범위에 빈 항목 있으면 메서드가 해당 항목에 대 한 명령 단추 컨트롤을 추가 하지 않습니다.  
  
 기본적으로 새 명령 단추 컨트롤을 사용 및 권한 상승이 필요 하지 않습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="loadradiobuttons"></a>  CTaskDialog::LoadRadioButtons  
 문자열 테이블에서 데이터를 사용 하 여 라디오 단추 컨트롤을 추가 합니다.  
  
```  
void LoadRadioButtons(
    int nIDRadioButtonsFirst,  
    int nIDRadioButtonsLast);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIDRadioButtonsFirst`  
 첫 번째 라디오 단추의 문자열 ID입니다.  
  
 [in] `nIDRadioButtonsLast`  
 마지막 라디오 단추의 문자열 ID입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 응용 프로그램의 리소스 파일에서 데이터를 사용 하 여 라디오 단추를 만듭니다. 리소스 파일에 문자열 테이블에는 연결된 문자열 Id와 여러 문자열에 있습니다. 이 메서드를 사용 하 여 추가 된 새 라디오 단추 문자열 라디오 단추의 캡션 및 문자열 ID에 대 한 ID를 사용 라디오 단추 선택 하는 문자열의 범위에서 제공 `nIDRadioButtonsFirst` 및 `nRadioButtonsLast`(포함). 범위에 빈 항목 있으면 메서드는 해당 항목에 대 한 라디오 단추를 추가 하지 않습니다.  
  
 기본적으로 새 라디오 단추가 활성화 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="navigateto"></a>  CTaskDialog::NavigateTo  
 포커스를 다른 전송 `CTaskDialog`합니다.  
  
```  
protected:  
void NavigateTo(CTaskDialog& oTaskDialog) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `oTaskDialog`  
 `CTaskDialog` 포커스를 받는 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 현재 숨깁니다 `CTaskDialog` 표시 될 때는 `oTaskDialog`합니다. `oTaskDialog` 현재와 같은 위치에 표시 되 `CTaskDialog`합니다.  
  
##  <a name="oncommandcontrolclick"></a>  CTaskDialog::OnCommandControlClick  
 명령 단추 컨트롤을 마우스 오른쪽 단추로 클릭할 때 프레임 워크에서이 메서드를 호출 합니다.  
  
```  
virtual HRESULT OnCommandControlClick(int nCommandControlID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nCommandControlID`  
 사용자가 선택한 명령 단추 컨트롤의 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 기본 구현은 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 사용자 지정 동작을 구현 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="oncreate"></a>  CTaskDialog::OnCreate  
 프레임 워크를 만든 후이 메서드는 호출 된 `CTaskDialog`합니다.  
  
```  
virtual HRESULT OnCreate();
```  
  
### <a name="return-value"></a>반환 값  
 기본 구현은 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 사용자 지정 동작을 구현 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="ondestroy"></a>  CTaskDialog::OnDestroy  
 제거 하기 전에 즉시 프레임 워크에서이 메서드를 호출는 `CTaskDialog`합니다.  
  
```  
virtual HRESULT OnDestroy();
```  
  
### <a name="return-value"></a>반환 값  
 기본 구현은 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 사용자 지정 동작을 구현 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="onexpandbuttonclick"></a>  CTaskDialog::OnExpandButtonClick  
 프레임 워크는 사용자가 확장 단추를 클릭할 때이 메서드를 호출 합니다.  
  
```  
virtual HRESULT OnExpandButtonClicked(BOOL bExpanded);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bExpanded`  
 0이 아닌 값을 지정 하면 추가 정보가 표시 됩니다. 0 추가 정보는 표시를 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 기본 구현은 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 사용자 지정 동작을 구현 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="onhelp"></a>  CTaskDialog::OnHelp  
 프레임 워크 사용자 도움말을 요청 하는 경우이 메서드를 호출 합니다.  
  
```  
virtual HRESULT OnHelp();
```  
  
### <a name="return-value"></a>반환 값  
 기본 구현은 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 사용자 지정 동작을 구현 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="onhyperlinkclick"></a>  CTaskDialog::OnHyperlinkClick  
 프레임 워크는 사용자가 하이퍼링크를 클릭할 때이 메서드를 호출 합니다.  
  
```  
virtual HRESULT OnHyperlinkClick(const CString& strHref);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `strHref`  
 하이퍼링크를 나타내는 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 기본 구현은 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 호출 [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) 반환 하기 전에 `S_OK`합니다.  
  
 사용자 지정 동작을 구현 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="oninit"></a>  CTaskDialog::OnInit  
 이 메서드를 호출 하는 프레임 워크는 경우는 `CTaskDialog` 초기화 됩니다.  
  
```  
virtual HRESULT OnInit();
```  
  
### <a name="return-value"></a>반환 값  
 기본 구현은 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 사용자 지정 동작을 구현 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="onnavigatepage"></a>  CTaskDialog::OnNavigatePage  
 에 대 한 응답에서이 메서드를 호출 하는 프레임 워크는 [CTaskDialog::NavigateTo](#navigateto) 메서드.  
  
```  
virtual HRESULT OnNavigatePage();
```  
  
### <a name="return-value"></a>반환 값  
 기본 구현은 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 사용자 지정 동작을 구현 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="onradiobuttonclick"></a>  CTaskDialog::OnRadioButtonClick  
 프레임 워크는 사용자가 라디오 단추 컨트롤을 선택할 때이 메서드를 호출 합니다.  
  
```  
virtual HRESULT OnRadioButtonClick(int nRadioButtonID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nRadioButtonID`  
 사용자가 클릭 한 라디오 단추 컨트롤의 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 기본 구현은 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 사용자 지정 동작을 구현 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="ontimer"></a>  CTaskDialog::OnTimer  
 프레임 워크 타이머가 만료 되는 경우이 메서드를 호출 합니다.  
  
```  
virtual HRESULT OnTimer(long lTime);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lTime`  
 시간 (밀리초) 이후에 `CTaskDialog` 만들어진 또는 타이머 다시 설정 되었습니다.  
  
### <a name="return-value"></a>반환 값  
 기본 구현은 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 사용자 지정 동작을 구현 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="onverificationcheckboxclick"></a>  CTaskDialog::OnVerificationCheckboxClick  
 확인 확인란을 두 번 클릭할 때 프레임 워크에서이 메서드를 호출 합니다.  
  
```  
virtual HRESULT OnVerificationCheckboxClick(BOOL bChecked);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bChecked`  
 `TRUE` 확인 확인란은 선택 된; 나타냅니다. `FALSE` 은 의미 합니다.  
  
### <a name="return-value"></a>반환 값  
 기본 구현은 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 사용자 지정 동작을 구현 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="removeallcommandcontrols"></a>  CTaskDialog::RemoveAllCommandControls  
 명령 단추 컨트롤을 모두 제거는 `CTaskDialog`합니다.  
  
```  
void RemoveAllCommandControls();
```  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="removeallradiobuttons"></a>  CTaskDialog::RemoveAllRadioButtons  
 모든 라디오 단추에서 제거 된 `CTaskDialog`합니다.  
  
```  
void RemoveAllRadioButtons();
```  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setcommandcontroloptions"></a>  CTaskDialog::SetCommandControlOptions  
 명령 단추 컨트롤에서 업데이트는 `CTaskDialog`합니다.  
  
```  
void SetCommandControlOptions(
    int nCommandControlID,  
    BOOL bEnabled,  
    BOOL bRequiresElevation = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nCommandControlID`  
 업데이트 명령 컨트롤의 ID입니다.  
  
 [in] `bEnabled`  
 지정 된 명령 단추 컨트롤 사용 여부를 나타내는 부울 매개 변수입니다.  
  
 [in] `bRequiresElevation`  
 지정 된 명령 단추 컨트롤 권한 상승이 필요한 경우를 나타내는 부울 매개 변수입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 명령 단추 컨트롤을 사용 하도록 설정할지에 추가 된 후 권한 상승이 필요한 지 여부를 변경 하는 `CTaskDialog Class`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="setcommonbuttonoptions"></a>  CTaskDialog::SetCommonButtonOptions  
 사용 하도록 설정 하 고 UAC 권한 상승을 요구 하려면 일반적인 단추의 하위 집합을 업데이트 합니다.  
  
```  
void SetCommonButtonOptions(
    int nDisabledButtonMask,  
    int nElevationButtonMask = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nDisabledButtonMask`  
 사용 하지 않으려면 일반 단추에 대 한 마스크입니다.  
  
 [in] `nElevationButtonMask`  
 상승이 필요한 일반적인 단추에 대 한 마스크입니다.  
  
### <a name="remarks"></a>설명  
 인스턴스를 사용할 수 있는 일반적인 단추가 설정할 수 있습니다는 [CTaskDialog 클래스](../../mfc/reference/ctaskdialog-class.md) 생성자를 사용 하 여 [CTaskDialog::CTaskDialog](#ctaskdialog) 장치와 [CTaskDialog::SetCommonButtons ](#setcommonbuttons). `CTaskDialog::SetCommonButtonOptions` 새 일반 단추 추가 지원 하지 않습니다.  
  
 사용 하지 않도록 설정 하거나이 사용할 수 있는 일반적인 단추 상승이 메서드를 사용 하는 경우 `CTaskDialog`,이 메서드를 사용 하 여 예외를 throw는 [확인](diagnostic-services.md#ensure) 매크로입니다.  
  
 이 메서드를 통해 사용할 수 있는 모든 단추는 `CTaskDialog` 에 속하지 않는 있지만 `nDisabledButtonMask`이전에 비활성화 된 경우에 합니다. 이 메서드는 비슷한 방식으로 권한 상승 처리: 일반 단추를 사용할 수 있지만에 포함 되지 않고 경우 상승 필요 하지 않은 일반적인 단추 기록 `nElevationButtonMask`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]  
  
##  <a name="setcommonbuttons"></a>  CTaskDialog::SetCommonButtons  
 일반적인 단추를 추가 하는 `CTaskDialog`합니다.  
  
```  
void SetCommonButtons(
    int nButtonMask,  
    int nDisabledButtonMask = 0,  
    int nElevationButtonMask = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nButtonMask`  
 에 추가 하는 단추의 마스크는 `CTaskDialog`합니다.  
  
 [in] `nDisabledButtonMask`  
 단추를 사용 하지 않도록 설정의 마스크입니다.  
  
 [in] `nElevationButtonMask`  
 권한 상승이 필요 단추의 마스크입니다.  
  
### <a name="remarks"></a>설명  
 이 인스턴스에 대 한 창 표시 한 후이 메서드를 호출할 수 없습니다는 `CTaskDialog Class` 만들어집니다. 이렇게 하면이 메서드는 예외를 throw 합니다.  
  
 단추 가리키는 `nButtonMask` 재정의에 이전에 추가 된 모든 공용 단추는 `CTaskDialog`합니다. 에 표시 된 단추만 `nButtonMask` 사용할 수 있습니다.  
  
 경우 `nDisabledButtonMask` 또는 `nElevationButtonMask` 에 속하지 않은 단추가 포함 `nButtonMask`,이 메서드를 사용 하 여 예외를 throw는 [확인](diagnostic-services.md#ensure) 매크로입니다.  
  
 기본적으로 모든 공통 단추가 설정 되어 있고 권한 상승이 필요 하지 않습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]  
  
##  <a name="setcontent"></a>  CTaskDialog::SetContent  
 내용을 업데이트는 `CTaskDialog`합니다.  
  
```  
void SetContent(const CString& strContent);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `strContent`  
 사용자에 게 표시할 문자열입니다.  
  
### <a name="remarks"></a>설명  
 콘텐츠는 `CTaskDialog Class` 대화 상자의 주 섹션의 사용자에 게 표시 되는 텍스트입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setdefaultcommandcontrol"></a>  CTaskDialog::SetDefaultCommandControl  
 기본 명령 단추 컨트롤을 지정합니다.  
  
```  
void SetDefaultCommandControl(int nCommandControlID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nCommandControlID`  
 기본값으로 지정할 명령 단추 컨트롤의 ID입니다.  
  
### <a name="remarks"></a>설명  
 기본 명령 단추 컨트롤은 컨트롤의 경우 선택은 `CTaskDialog` 처음 사용자에 게 표시 합니다.  
  
 로 지정 된 명령 단추 컨트롤을 찾을 수 없는 경우이 메서드는 예외를 throw `nCommandControlID`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="setdefaultradiobutton"></a>  CTaskDialog::SetDefaultRadioButton  
 기본 라디오 단추를 지정합니다.  
  
```  
void SetDefaultRadioButton(int nRadioButtonID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nRadioButtonID`  
 기본 라디오 단추의 ID입니다.  
  
### <a name="remarks"></a>설명  
 기본 라디오 단추는 단추입니다 경우 선택 된 `CTaskDialog` 처음 사용자에 게 표시 합니다.  
  
 로 지정 된 라디오 단추를 찾을 수 없는 경우이 메서드는 예외를 throw `nRadioButtonID`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setdialogwidth"></a>  CTaskDialog::SetDialogWidth  
 너비를 조정는 `CTaskDialog`합니다.  
  
```  
void SetDialogWidth(int nWidth = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nWidth`  
 대화 상자의 픽셀 너비입니다.  
  
### <a name="remarks"></a>설명  
 매개 변수 `nWidth` 보다 크거나 0 이어야 합니다. 그렇지 않으면이 메서드에서 예외가 throw 됩니다.  
  
 경우 `nWidth` 이 메서드 설정 대화 상자 기본 크기를 0으로 설정 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setexpansionarea"></a>  CTaskDialog::SetExpansionArea  
 확장 영역을 업데이트는 `CTaskDialog`합니다.  
  
```  
void SetExpansionArea(
    const CString& strExpandedInformation,  
    const CString& strCollapsedLabel = _T(""),  
    const CString& strExpandedLabel = _T(""));
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `strExpandedInformation`  
 문자열 하 고 `CTaskDialog` 확장 단추를 클릭할 때 대화 상자 본문에 표시 됩니다.  
  
 [in] `strCollapsedLabel`  
 문자열 하 고 `CTaskDialog` 확장 된 영역이 축소 된 경우 확장 단추 옆에 표시 됩니다.  
  
 [in] `strExpandedLabel`  
 문자열 하 고 `CTaskDialog` 확장 된 영역을 표시 하는 경우 확장 단추 옆에 표시 됩니다.  
  
### <a name="remarks"></a>설명  
 확장 영역은 `CTaskDialog Class` 사용자에 게 추가 정보를 제공할 수 있습니다. 확장 영역은의 주요 부분에는 `CTaskDialog`, 제목 및 콘텐츠 문자열의 바로 아래 위치 합니다.  
  
 경우는 `CTaskDialog` 처음 확장 된 정보는 표시 되지 않습니다 및 배치 표시 `strCollapsedLabel` 확장 단추 옆에 있는 합니다. 확장 단추를 클릭할 때는 `CTaskDialog` 표시 `strExpandedInformation` 레이블을 변경 하 고 `strExpandedLabel`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setfootericon"></a>  CTaskDialog::SetFooterIcon  
 업데이트의 바닥글 아이콘은 `CTaskDialog`합니다.  
  
```  
void SetFooterIcon(HICON hFooterIcon);  
void SetFooterIcon(LPCWSTR lpszFooterIcon);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hFooterIcon`  
 에 대 한 새 아이콘의 `CTaskDialog`합니다.  
  
 [in] `lpszFooterIcon`  
 에 대 한 새 아이콘의 `CTaskDialog`합니다.  
  
### <a name="remarks"></a>설명  
 바닥글 아이콘의 맨 아래에 표시 되는 [CTaskDialog 클래스](../../mfc/reference/ctaskdialog-class.md)합니다. 바닥글 텍스트를 연결 있을 수 있습니다. 바닥글 텍스트를 변경할 수 있습니다 [CTaskDialog::SetFooterText](#setfootertext)합니다.  
  
 사용 하 여 예외를 throw는 [확인](diagnostic-services.md#ensure) 매크로 경우는 `CTaskDialog` 표시 됩니다 또는 입력된 매개 변수가 `NULL`합니다.  
  
 A `CTaskDialog` 받아들일 수 있습니다는 `HICON` 또는 `LPCWSTR` 바닥글 아이콘으로 합니다. 이 옵션을 설정 하 여 구성 된 `TDF_USE_HICON_FOOTER` 생성자에서 또는 [CTaskDialog::SetOptions](#setoptions)합니다. 기본적으로는 `CTaskDialog` 사용 하도록 구성 된 `LPCWSTR` 바닥글 아이콘에 대 한 입력된 유형으로 합니다. 이 메서드는 부적절 한 형식을 사용 하 여 아이콘을 설정 하려고 하면 예외를 생성 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setfootertext"></a>  CTaskDialog::SetFooterText  
 바닥글에 텍스트를 업데이트 하는 `CTaskDialog`합니다.  
  
```  
void SetFooterText(const CString& strFooterText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `strFooterText`  
 바닥글에 대 한 새 텍스트입니다.  
  
### <a name="remarks"></a>설명  
 바닥글 아이콘이 맨 아래에서 바닥글 텍스트 옆에 표시 된 `CTaskDialog`합니다. 가 있는 바닥글 아이콘을 변경할 수 있습니다 [CTaskDialog::SetFooterIcon](#setfootericon)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setmainicon"></a>  CTaskDialog::SetMainIcon  
 업데이트의 기본 아이콘은 `CTaskDialog`합니다.  
  
```  
void SetMainIcon(HICON hMainIcon);  
void SetMainIcon(LPCWSTR lpszMainIcon);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hMainIcon`  
 새 아이콘입니다.  
  
 [in] `lpszMainIcon`  
 새 아이콘입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 예외를 throw는 [확인](diagnostic-services.md#ensure) 매크로 경우는 `CTaskDialog` 표시 됩니다 또는 입력된 매개 변수가 `NULL`합니다.  
  
 A `CTaskDialog` 받아들일 수 있습니다는 `HICON` 또는 `LPCWSTR` 주 아이콘으로 합니다. 설정 하 여이 구성할 수 있습니다는 `TDF_USE_HICON_MAIN` 생성자 나 옵션의 [CTaskDialog::SetOptions](#setoptions) 메서드. 기본적으로는 `CTaskDialog` 사용 하도록 구성 된 `LPCWSTR` 주 아이콘에 대 한 입력된 유형으로 합니다. 이 메서드는 부적절 한 형식을 사용 하 여 아이콘을 설정 하려고 하면 예외를 생성 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setmaininstruction"></a>  CTaskDialog::SetMainInstruction  
 기본 명령 업데이트는 `CTaskDialog`합니다.  
  
```  
void SetMainInstruction(const CString& strInstructions);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `strInstructions`  
 새 기본 명령입니다.  
  
### <a name="remarks"></a>설명  
 기본 명령은 `CTaskDialog Class` 큰 굵은 글꼴의 사용자에 게 표시 되는 텍스트입니다. 대화 상자의 제목 표시줄 아래에 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setoptions"></a>  CTaskDialog::SetOptions  
 에 대 한 옵션을 구성에서 `CTaskDialog`합니다.  
  
```  
void SetOptions(int nOptionFlag);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nOptionFlag`  
 에 사용할 플래그 집합이 `CTaskDialog`합니다.  
  
### <a name="remarks"></a>설명  
 이 방법에 대 한 현재 옵션을 모두 해제는 `CTaskDialog`합니다. 현재 옵션을 유지 하려면 검색 해야에 처음으로 [CTaskDialog::GetOptions](#getoptions) 및 옵션을 설정 하려면을 결합 합니다.  
  
 다음 표에서 모든 유효한 옵션을 나열합니다.  
  
 `TDF_ENABLE_HYPERLINKS`  
 하이퍼링크를 사용 하도록 설정 된 `CTaskDialog`합니다.  
  
 `TDF_USE_HICON_MAIN`  
 구성에서 `CTaskDialog` 사용 하는 `HICON` 주 아이콘에 대 한 합니다. 사용 하는 `LPCWSTR`합니다.  
  
 `TDF_USE_HICON_FOOTER`  
 구성에서 `CTaskDialog` 사용 하는 `HICON` 바닥글 아이콘에 대 한 합니다. 사용 하는 `LPCWSTR`합니다.  
  
 `TDF_ALLOW_DIALOG_CANCELLATION`  
 닫을 수 있습니다는 `CTaskDialog` 키보드를 사용 하 여 또는 대화 상자의 오른쪽 위 모서리에 있는 아이콘을 사용 하 여 경우에는 **취소** 단추가 활성화 되지 않습니다. 이 플래그가 설정 되지 않은 경우 및 **취소** 단추가 활성화 되지 않으면, 사용자 Alt + F4 키를 사용 하 여 대화 상자를 닫을 수 없습니다 또는 제목 표시줄의 닫기 단추입니다.  
  
 `TDF_USE_COMMAND_LINKS`  
 구성의 `CTaskDialog` 명령 단추 컨트롤을 사용 하도록 합니다.  
  
 `TDF_USE_COMMAND_LINKS_NO_ICON`  
 구성의 `CTaskDialog` 컨트롤 옆에 있는 아이콘을 표시 하지 않고 명령 단추 컨트롤을 사용 하도록 합니다. `TDF_USE_COMMAND_LINKS`는 `TDF_USE_COMMAND_LINKS_NO_ICON`를 재정의합니다.  
  
 `TDF_EXPAND_FOOTER_AREA`  
 현재 확장 되어 확장 영역을 나타냅니다.  
  
 `TDF_EXPANDED_BY_DEFAULT`  
 기본적으로 확장으로 확장 되는지 여부를 결정 합니다.  
  
 `TDF_VERIFICATION_FLAG_CHECKED`  
 확인 확인란 현재 선택 된 것을 나타냅니다.  
  
 `TDF_SHOW_PROGRESS_BAR`  
 구성의 `CTaskDialog` 진행률 표시줄을 표시 합니다.  
  
 `TDF_SHOW_MARQUEE_PROGRESS_BAR`  
 움직이는 텍스트 진행률 표시줄 되도록 진행률 표시줄을 구성 합니다. 이 옵션을 사용 하는 경우 설정 해야 `TDF_SHOW_PROGRESS_BAR` 예상 동작입니다.  
  
 `TDF_CALLBACK_TIMER`  
 나타냅니다는 `CTaskDialog` 콜백 간격은 약 200 밀리초로 설정 됩니다.  
  
 `TDF_POSITION_RELATIVE_TO_WINDOW`  
 구성의 `CTaskDialog` 부모 창을 기준으로 가운데 맞춤 될 합니다. 이 플래그를 사용 하지 않는 경우는 `CTaskDialog` 모니터를 기준으로 가운데 맞춤 합니다.  
  
 `TDF_RTL_LAYOUT`  
 구성의 `CTaskDialog` 오른쪽에서 왼쪽 읽기 모드에 대 한 합니다.  
  
 `TDF_NO_DEFAULT_RADIO_BUTTON`  
 없는 라디오 단추가 선택 되어 있는지 나타냅니다 때는 `CTaskDialog` 나타납니다.  
  
 `TDF_CAN_BE_MINIMIZED`  
 최소화 하기 위해 사용자는 `CTaskDialog`합니다. 이 옵션을 지원 하기 위해는 `CTaskDialog` 모달 수 없습니다. MFC MFC는 모덜리스를 지원 하지 않으므로이 옵션을 지원 하지 않습니다 `CTaskDialog`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setprogressbarmarquee"></a>  CTaskDialog::SetProgressBarMarquee  
 구성에 대 한 움직이는 텍스트 막대는 `CTaskDialog` 대화 상자에 추가 합니다.  
  
```  
void SetProgressBarMarquee(
    BOOL bEnabled = TRUE,  
    int nMarqueeSpeed = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnabled`  
 `TRUE` 움직이는 텍스트 바;를 사용 하도록 설정 하려면 `FALSE` 움직이는 텍스트 막대를 사용 하지 않도록 설정에서 제거 하는 `CTaskDialog`합니다.  
  
 [in] `nMarqueeSpeed`  
 움직이는 텍스트 막대의 속도 나타내는 정수입니다.  
  
### <a name="remarks"></a>설명  
 움직이는 텍스트 막대의 주 텍스트 아래에 표시 된 `CTaskDialog Class`합니다.  
  
 사용 하 여 `nMarqueeSpeed` 움직이는 텍스트 바;의 속도 설정 하려면 더 큰 값은 느린 속도 나타냅니다. 값이 0에 대 한 `nMarqueeSpeed` Windows의 기본 속도로 이동할 움직이는 텍스트 모음입니다.  
  
 사용 하 여 예외를 throw는 [확인](diagnostic-services.md#ensure) 매크로 경우 `nMarqueeSpeed` 0 보다 작습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarposition"></a>  CTaskDialog::SetProgressBarPosition  
 진행률 표시줄의 위치를 조정 합니다.  
  
```  
void SetProgressBarPosition(int nProgressPos);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nProgressPos`  
 진행률 표시줄에 대 한 위치입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 예외를 throw 하는이 메서드는 [확인](diagnostic-services.md#ensure) 매크로 경우 `nProgressPos` 진행률 표시줄 범위에 있지 않습니다. 진행률 표시줄 범위와 변경할 수 있습니다 [CTaskDialog::SetProgressBarRange](#setprogressbarrange)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarrange"></a>  CTaskDialog::SetProgressBarRange  
 진행률 표시줄의 범위를 조정합니다.  
  
```  
void SetProgressBarRange(
    int nRangeMin,  
    int nRangeMax);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nRangeMin`  
 진행률 표시줄의 하 한입니다.  
  
 [in] `nRangeMax`  
 진행률 표시줄의 상한입니다.  
  
### <a name="remarks"></a>설명  
 진행률 표시줄의 위치는 상대적으로 `nRangeMin` 및 `nRangeMax`합니다. 예를 들어 경우 `nRangeMin` 은 50 및 `nRangeMax` 은 100, 75의 위치는 진행률 표시줄 짝수가 있습니다. 사용 하 여 [CTaskDialog::SetProgressBarPosition](#setprogressbarposition) 진행률 표시줄의 위치를 설정 합니다.  
  
 진행률 표시줄 옵션을 표시 하려면 `TDF_SHOW_PROGRESS_BAR` 활성화 해야 하 고 `TDF_SHOW_MARQUEE_PROGRESS_BAR` 사용 되지 않아야 합니다. 이 메서드를 자동으로 설정 `TDF_SHOW_PROGRESS_BAR` 지웁니다 `TDF_SHOW_MARQUEE_PROGRESS_BAR`합니다. 사용 하 여 [CTaskDialog::SetOptions](#setoptions) 수동으로의이 인스턴스에 대 한 옵션을 변경 하는 [CTaskDialog 클래스](../../mfc/reference/ctaskdialog-class.md)합니다.  
  
 사용 하 여 예외를 throw는 [확인](diagnostic-services.md#ensure) 매크로 경우 `nRangeMin` 은 보다 작지 않음 `nRangeMax`합니다. 이 메서드는 또한 예외를 throw 하는 경우는 `CTaskDialog` 이미 표시 되 고 진행률 표시줄이 움직이는 텍스트입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarstate"></a>  CTaskDialog::SetProgressBarState  
 진행률 표시줄의 상태를 설정 하 고에 표시 된 `CTaskDialog`합니다.  
  
```  
void SetProgressBarState(int nState = PBST_NORMAL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nState`  
 진행률 표시줄의 상태입니다. 가능한 값에 대 한 설명 섹션을 참조 하십시오.  
  
### <a name="remarks"></a>설명  
 사용 하 여 예외를 throw는 [확인](diagnostic-services.md#ensure) 매크로 경우는 `CTaskDialog` 이미 표시 되 고 진행률 표시줄이 움직이는 텍스트입니다.  
  
 다음 표에서 가능한 값에 대 한 `nState`합니다. 이러한 모든 경우 지정 된 위치에 도달할 때까지 진행률 표시줄이 일반 색상으로 채워집니다. 해당 시점에 색 상태에 따라 변경 됩니다.  
  
 PBST_NORMAL  
 진행률 표시줄 채우는, `CTaskDialog` 막대의 색을 변경 되지 않습니다. 기본적으로 일반 색은 녹색입니다.  
  
 PBST_ERROR  
 진행률 표시줄 채우는, `CTaskDialog` 오류 색 막대의 색을 변경 합니다. 기본적으로 빨강입니다.  
  
 PBST_PAUSED  
 진행률 표시줄 채우는, `CTaskDialog` 일시 중지 된 색 막대의 색을 변경 합니다. 기본적으로 노란색입니다.  
  
 와 함께 진행률 표시줄을 중지 하는 위치를 설정할 수 있습니다 [CTaskDialog::SetProgressBarPosition](#setprogressbarposition)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setradiobuttonoptions"></a>  CTaskDialog::SetRadioButtonOptions  
 라디오 단추를 사용 하지 않도록 설정 하거나 사용 합니다.  
  
```  
void SetRadioButtonOptions(
    int nRadioButtonID,  
    BOOL bEnabled);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nRadioButtonID`  
 라디오 단추 컨트롤의 ID입니다.  
  
 [in] `bEnabled`  
 `TRUE` 라디오 단추를 사용 하도록 설정 하려면 `FALSE` 라디오 단추를 사용 하지 않도록 설정 하려면.  
  
### <a name="remarks"></a>설명  
 사용 하 여 예외를 throw 하는이 메서드는 [확인](diagnostic-services.md#ensure) 매크로 경우 `nRadioButtonID` 라디오 단추에 대 한 올바른 ID가 아닙니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setverificationcheckbox"></a>  CTaskDialog::SetVerificationCheckbox  
 확인 확인란의 선택된 상태를 설정합니다.  
  
```  
void SetVerificationCheckbox(BOOL bChecked);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bChecked`  
 `TRUE` 확인 하려면 확인란은 선택 될 때는 `CTaskDialog` 표시 됩니다. `FALSE` 확인할 확인란 선택 되지 않은 경우는 `CTaskDialog` 표시 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="setverificationcheckboxtext"></a>  CTaskDialog::SetVerificationCheckboxText  
 확인 확인란 오른쪽에 표시 되는 텍스트를 설정 합니다.  
  
```  
void SetVerificationCheckboxText(CString& strVerificationText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `strVerificationText`  
 확인 확인란 옆에 있는이 메서드를 표시 하는 텍스트입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 예외를 throw는 [확인](diagnostic-services.md#ensure) 이 매크로의 인스턴스는 `CTaskDialog Class` 이미 표시 되어 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="setwindowtitle"></a>  CTaskDialog::SetWindowTitle  
 제목을 설정는 `CTaskDialog`합니다.  
  
```  
void SetWindowTitle(CString& strWindowTitle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `strWindowTitle`  
 에 대 한 새 제목을 `CTaskDialog`합니다.  
  
### <a name="remarks"></a>설명  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="showdialog"></a>  CTaskDialog::ShowDialog  
 만들고 표시 한 `CTaskDialog`합니다.  
  
```  
static INT_PTR ShowDialog(
    const CString& strContent,  
    const CString& strMainInstruction,  
    const CString& strTitle,  
    int nIDCommandControlsFirst,  
    int nIDCommandControlsLast,  
    int nCommonButtons = TDCBF_YES_BUTTON | TDCBF_NO_BUTTON,  
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,  
    const CString& strFooter = _T(""));
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `strContent`  
 콘텐츠에 대 한 사용 하는 문자열은 `CTaskDialog`합니다.  
  
 [in] `strMainInstruction`  
 기본 명령은 `CTaskDialog`합니다.  
  
 [in] `strTitle`  
 제목은 `CTaskDialog`합니다.  
  
 [in] `nIDCommandControlsFirst`  
 첫 번째 명령은의 문자열 ID입니다.  
  
 [in] `nIDCommandControlsLast`  
 마지막 명령의 문자열 ID입니다.  
  
 [in] `nCommonButtons`  
 에 추가 하는 단추의 마스크는 `CTaskDialog`합니다.  
  
 [in] `nTaskDialogOptions`  
 에 대해 사용할 수 있는 옵션 집합은 `CTaskDialog`합니다.  
  
 [in] `strFooter`  
 바닥글으로 사용할 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 사용자가 선택한 항목에 해당 하는 정수입니다.  
  
### <a name="remarks"></a>설명  
 이 정적 메서드를 사용 하면의 인스턴스를 만들 수는 `CTaskDialog Class` 명시적으로 만들지 않고는 `CTaskDialog` 코드에서이 개체입니다. 있기 때문에 없는 `CTaskDialog` 개체의 다른 모든 메서드를 호출할 수 없습니다는 `CTaskDialog` 표시 하려면이 메서드를 사용 하는 경우는 `CTaskDialog` 사용자에 게 합니다.  
  
 이 메서드는 응용 프로그램의 리소스 파일에서 데이터를 사용 하 여 명령 단추 컨트롤을 만듭니다. 리소스 파일에 문자열 테이블에는 연결된 문자열 Id와 여러 문자열에 있습니다. 이 메서드 간의 문자열 테이블에 유효한 각 항목에 대 한 명령 단추 컨트롤을 추가 `nIDCommandControlsFirst` 및 `nCommandControlsLast`(포함). 이러한 명령 단추 컨트롤에 대 한 문자열 테이블에는 문자열은 컨트롤의 캡션 및 문자열 ID는 컨트롤의 id입니다.  
  
 참조 [CTaskDialog::SetOptions](#setoptions) 사용할 수 있는 옵션의 목록에 대 한 합니다.  
  
 `CTaskDialog` 명령 링크 컨트롤, 일반적인 단추를 선택 하거나 닫을 때 닫습니다는 `CTaskDialog`합니다. 반환 값은 사용자 대화 상자를 닫은 방법을 나타내는 식별자입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]  
  
##  <a name="taskdialogcallback"></a>  CTaskDialog::TaskDialogCallback  
 프레임 워크는 다양 한 Windows 메시지에 대 한 응답에서이 메서드를 호출합니다.  
  
```  
friend:  
HRESULT TaskDialogCallback(
    HWND hWnd,  
    UINT uNotification,  
    WPARAM wParam,  
    LPARAM lParam,  
    LONG_PTR dwRefData);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hwnd`  
 에 대 한 핸들은 `m_hWnd` 에 대 한 구조는 `CTaskDialog`합니다.  
  
 [in] `uNotification`  
 생성된 된 메시지를 지정 하는 알림 코드입니다.  
  
 [in] `wParam`  
 메시지에 대 한 자세한 정보입니다.  
  
 [in] `lParam`  
 메시지에 대 한 자세한 정보입니다.  
  
 [in] `dwRefData`  
 에 대 한 포인터는 `CTaskDialog` 콜백 메시지에 적용 되는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 특정 알림 코드에 따라 다릅니다. 자세한 내용은 설명 부분을 참조하세요.  
  
### <a name="remarks"></a>설명  
 기본 구현은 `TaskDialogCallback` 특정 메시지를 처리 한 다음의 메서드에서 적절 한를 호출는 [CTaskDialog 클래스](../../mfc/reference/ctaskdialog-class.md)합니다. 에 대 한 응답의 예를 들어는 `TDN_BUTTON_CLICKED` 메시지 `TaskDialogCallback` 호출 [CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)합니다.  
  
 에 대 한 값 `wParam` 및 `lParam` 생성된 된 특정 메시지에 따라 달라 집니다. 비어 있는 것으로 이러한 값 중 하나 또는 모두에 대 한 것 같습니다. 다음 표에 지원 되는 기본 알림 및 작업의 값 `wParam` 및 `lParam` 나타냅니다. 파생된 클래스에서이 메서드를 재정의 하는 경우 다음 표에서 각 메시지에 대 한 콜백 코드가 구현 해야 합니다.  
  
|알림 메시지|`wParam` 값|`lParam` 값|  
|--------------------------|--------------------|--------------------|  
|`TDN_CREATED`|사용되지 않습니다.|사용되지 않습니다.|  
|`TDN_NAVIGATED`|사용되지 않습니다.|사용되지 않습니다.|  
|`TDN_BUTTON_CLICKED`|명령 단추 컨트롤 id입니다.|사용되지 않습니다.|  
|`TDN_HYPERLINK_CLICKED`|사용되지 않습니다.|A [lpcwstr을 사용](http://msdn.microsoft.com/library/windows/desktop/aa383751) 링크가 포함 된 구조입니다.|  
|`TDN_TIMER`|시간 (밀리초) 이후에 `CTaskDialog` 만들어진 또는 타이머 다시 설정 되었습니다.|사용되지 않습니다.|  
|`TDN_DESTROYED`|사용되지 않습니다.|사용되지 않습니다.|  
|`TDN_RADIO_BUTTON_CLICKED`|라디오 단추 id입니다.|사용되지 않습니다.|  
|`TDN_DIALOG_CONSTRUCTED`|사용되지 않습니다.|사용되지 않습니다.|  
|`TDN_VERIFICATION_CLICKED`|확인란을 선택한 경우 1, 없는 경우 0입니다.|사용되지 않습니다.|  
|`TDN_HELP`|사용되지 않습니다.|사용되지 않습니다.|  
|`TDN_EXPANDO_BUTTON_CLICKED`|확장 영역 축소 되 면 0 이 속성을 0이 아닌 이면 확장 텍스트가 표시 됩니다.|사용되지 않습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [연습: 응용 프로그램에 CTaskDialog 추가](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)



