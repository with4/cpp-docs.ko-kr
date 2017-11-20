---
title: "CFileDialog 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileDialog
- AFXDLGS/CFileDialog
- AFXDLGS/CFileDialog::CFileDialog
- AFXDLGS/CFileDialog::AddCheckButton
- AFXDLGS/CFileDialog::AddComboBox
- AFXDLGS/CFileDialog::AddControlItem
- AFXDLGS/CFileDialog::AddEditBox
- AFXDLGS/CFileDialog::AddMenu
- AFXDLGS/CFileDialog::AddPlace
- AFXDLGS/CFileDialog::AddPushButton
- AFXDLGS/CFileDialog::AddRadioButtonList
- AFXDLGS/CFileDialog::AddSeparator
- AFXDLGS/CFileDialog::AddText
- AFXDLGS/CFileDialog::ApplyOFNToShellDialog
- AFXDLGS/CFileDialog::DoModal
- AFXDLGS/CFileDialog::EnableOpenDropDown
- AFXDLGS/CFileDialog::EndVisualGroup
- AFXDLGS/CFileDialog::GetCheckButtonState
- AFXDLGS/CFileDialog::GetControlItemState
- AFXDLGS/CFileDialog::GetControlState
- AFXDLGS/CFileDialog::GetEditBoxText
- AFXDLGS/CFileDialog::GetFileExt
- AFXDLGS/CFileDialog::GetFileName
- AFXDLGS/CFileDialog::GetFileTitle
- AFXDLGS/CFileDialog::GetFolderPath
- AFXDLGS/CFileDialog::GetIFileDialogCustomize
- AFXDLGS/CFileDialog::GetIFileOpenDialog
- AFXDLGS/CFileDialog::GetIFileSaveDialog
- AFXDLGS/CFileDialog::GetNextPathName
- AFXDLGS/CFileDialog::GetOFN
- AFXDLGS/CFileDialog::GetPathName
- AFXDLGS/CFileDialog::GetReadOnlyPref
- AFXDLGS/CFileDialog::GetResult
- AFXDLGS/CFileDialog::GetResults
- AFXDLGS/CFileDialog::GetSelectedControlItem
- AFXDLGS/CFileDialog::GetStartPosition
- AFXDLGS/CFileDialog::HideControl
- AFXDLGS/CFileDialog::IsPickFoldersMode
- AFXDLGS/CFileDialog::MakeProminent
- AFXDLGS/CFileDialog::RemoveControlItem
- AFXDLGS/CFileDialog::SetCheckButtonState
- AFXDLGS/CFileDialog::SetControlItemState
- AFXDLGS/CFileDialog::SetControlItemText
- AFXDLGS/CFileDialog::SetControlLabel
- AFXDLGS/CFileDialog::SetControlState
- AFXDLGS/CFileDialog::SetControlText
- AFXDLGS/CFileDialog::SetDefExt
- AFXDLGS/CFileDialog::SetEditBoxText
- AFXDLGS/CFileDialog::SetProperties
- AFXDLGS/CFileDialog::SetSelectedControlItem
- AFXDLGS/CFileDialog::SetTemplate
- AFXDLGS/CFileDialog::StartVisualGroup
- AFXDLGS/CFileDialog::UpdateOFNFromShellDialog
- AFXDLGS/CFileDialog::OnButtonClicked
- AFXDLGS/CFileDialog::OnCheckButtonToggled
- AFXDLGS/CFileDialog::OnControlActivating
- AFXDLGS/CFileDialog::OnFileNameChange
- AFXDLGS/CFileDialog::OnFileNameOK
- AFXDLGS/CFileDialog::OnFolderChange
- AFXDLGS/CFileDialog::OnInitDone
- AFXDLGS/CFileDialog::OnItemSelected
- AFXDLGS/CFileDialog::OnLBSelChangedNotify
- AFXDLGS/CFileDialog::OnShareViolation
- AFXDLGS/CFileDialog::OnTypeChange
- AFXDLGS/CFileDialog::m_ofn
dev_langs: C++
helpviewer_keywords:
- CFileDialog [MFC], CFileDialog
- CFileDialog [MFC], AddCheckButton
- CFileDialog [MFC], AddComboBox
- CFileDialog [MFC], AddControlItem
- CFileDialog [MFC], AddEditBox
- CFileDialog [MFC], AddMenu
- CFileDialog [MFC], AddPlace
- CFileDialog [MFC], AddPushButton
- CFileDialog [MFC], AddRadioButtonList
- CFileDialog [MFC], AddSeparator
- CFileDialog [MFC], AddText
- CFileDialog [MFC], ApplyOFNToShellDialog
- CFileDialog [MFC], DoModal
- CFileDialog [MFC], EnableOpenDropDown
- CFileDialog [MFC], EndVisualGroup
- CFileDialog [MFC], GetCheckButtonState
- CFileDialog [MFC], GetControlItemState
- CFileDialog [MFC], GetControlState
- CFileDialog [MFC], GetEditBoxText
- CFileDialog [MFC], GetFileExt
- CFileDialog [MFC], GetFileName
- CFileDialog [MFC], GetFileTitle
- CFileDialog [MFC], GetFolderPath
- CFileDialog [MFC], GetIFileDialogCustomize
- CFileDialog [MFC], GetIFileOpenDialog
- CFileDialog [MFC], GetIFileSaveDialog
- CFileDialog [MFC], GetNextPathName
- CFileDialog [MFC], GetOFN
- CFileDialog [MFC], GetPathName
- CFileDialog [MFC], GetReadOnlyPref
- CFileDialog [MFC], GetResult
- CFileDialog [MFC], GetResults
- CFileDialog [MFC], GetSelectedControlItem
- CFileDialog [MFC], GetStartPosition
- CFileDialog [MFC], HideControl
- CFileDialog [MFC], IsPickFoldersMode
- CFileDialog [MFC], MakeProminent
- CFileDialog [MFC], RemoveControlItem
- CFileDialog [MFC], SetCheckButtonState
- CFileDialog [MFC], SetControlItemState
- CFileDialog [MFC], SetControlItemText
- CFileDialog [MFC], SetControlLabel
- CFileDialog [MFC], SetControlState
- CFileDialog [MFC], SetControlText
- CFileDialog [MFC], SetDefExt
- CFileDialog [MFC], SetEditBoxText
- CFileDialog [MFC], SetProperties
- CFileDialog [MFC], SetSelectedControlItem
- CFileDialog [MFC], SetTemplate
- CFileDialog [MFC], StartVisualGroup
- CFileDialog [MFC], UpdateOFNFromShellDialog
- CFileDialog [MFC], OnButtonClicked
- CFileDialog [MFC], OnCheckButtonToggled
- CFileDialog [MFC], OnControlActivating
- CFileDialog [MFC], OnFileNameChange
- CFileDialog [MFC], OnFileNameOK
- CFileDialog [MFC], OnFolderChange
- CFileDialog [MFC], OnInitDone
- CFileDialog [MFC], OnItemSelected
- CFileDialog [MFC], OnLBSelChangedNotify
- CFileDialog [MFC], OnShareViolation
- CFileDialog [MFC], OnTypeChange
- CFileDialog [MFC], m_ofn
ms.assetid: fda4fd3c-08b8-4ce0-8e9d-7bab23f8c6c0
caps.latest.revision: "47"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2dead08eaeb525e626e9c1f02af346b0c3998260
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="cfiledialog-class"></a>CFileDialog 클래스
파일 열기 또는 저장 작업 파일에 사용 되는 일반 대화 상자를 캡슐화 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CFileDialog : public CCommonDialog  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CFileDialog::CFileDialog](#cfiledialog)|`CFileDialog` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CFileDialog::AddCheckButton](#addcheckbutton)|대화 상자에 확인 단추를 추가합니다.|  
|[CFileDialog::AddComboBox](#addcombobox)|대화 상자에 콤보 상자를 추가합니다.|  
|[CFileDialog::AddControlItem](#addcontrolitem)|대화 상자에서 컨테이너 컨트롤에 항목을 추가 합니다.|  
|[CFileDialog::AddEditBox](#addeditbox)|대화 상자에 입력란을 추가합니다.|  
|[CFileDialog::AddMenu](#addmenu)|대화 상자에 메뉴를 추가합니다.|  
|[CFileDialog::AddPlace](#addplace)|오버로드됨. 목록에 폴더를 열거나 항목을 저장 하는 사용자에 대해 사용할 수 있는 배치를 추가 합니다.|  
|[CFileDialog::AddPushButton](#addpushbutton)|대화 상자에 단추를 추가 합니다.|  
|[CFileDialog::AddRadioButtonList](#addradiobuttonlist)|대화 상자에 옵션 단추 (라디오 단추) 그룹을 추가합니다.|  
|[CFileDialog::AddSeparator](#addseparator)|대화 상자에는 구분 기호를 추가합니다.|  
|[CFileDialog::AddText](#addtext)|대화 상자에 텍스트 콘텐츠를 추가합니다.|  
|[CFileDialog::ApplyOFNToShellDialog](#applyofntoshelldialog)|상태 업데이트는 `CFileDialog` 매개 변수 및에 저장 하는 플래그와 일치 하는 `m_ofn` 멤버 변수입니다.|  
|[CFileDialog::DoModal](#domodal)|대화 상자를 표시 하 고 선택할 수 있습니다.|  
|[CFileDialog::EnableOpenDropDown](#enableopendropdown)|드롭 다운 목록에서 사용 하도록 설정 된 **열려** 또는 **저장** 대화 상자에서 단추입니다.|  
|[CFileDialog::EndVisualGroup](#endvisualgroup)|대화 상자에서 시각적 그룹에 요소가 추가 중지합니다.|  
|[CFileDialog::GetCheckButtonState](#getcheckbuttonstate)|대화 상자에서 확인 단추 (확인란)의 현재 상태를 가져옵니다.|  
|[CFileDialog::GetControlItemState](#getcontrolitemstate)|대화 상자에 있는 컨테이너 컨트롤에 있는 항목의 현재 상태를 가져옵니다.|  
|[CFileDialog::GetControlState](#getcontrolstate)|현재 표시 여부를 가져오고 지정 된 컨트롤의 상태를 사용 하도록 설정 합니다.|  
|[CFileDialog::GetEditBoxText](#geteditboxtext)|편집 상자 컨트롤에서 현재 텍스트를 가져옵니다.|  
|[CFileDialog::GetFileExt](#getfileext)|선택한 파일의 확장명을 반환 합니다.|  
|[CFileDialog::GetFileName](#getfilename)|선택한 파일의 파일 이름을 반환합니다.|  
|[CFileDialog::GetFileTitle](#getfiletitle)|선택한 파일의 제목을 반환합니다.|  
|[CFileDialog::GetFolderPath](#getfolderpath)|탐색기 스타일에 대 한 현재 열려 있는 폴더 또는 디렉터리의 경로 검색 **열고** 또는 **다른 이름으로 저장** 일반 대화 상자.|  
|[CFileDialog::GetIFileDialogCustomize](#getifiledialogcustomize)|사용자 지정에 대 한 내부 COM 개체를 검색 `CFileDialog` 개체입니다.|  
|[CFileDialog::GetIFileOpenDialog](#getifileopendialog)|에 대 한 내부 COM 개체를 검색 한 `CFileDialog` 로 사용 되는 한 **열려** 파일 대화 상자.|  
|[CFileDialog::GetIFileSaveDialog](#getifilesavedialog)|에 대 한 내부 COM 개체를 검색 한 `CFileDialog` 로 사용 되는 한 **저장** 파일 대화 상자.|  
|[CFileDialog::GetNextPathName](#getnextpathname)|선택된 된 다음 파일의 전체 경로 반환합니다.|  
|[CFileDialog::GetOFN](#getofn)|검색 된 `OPENFILENAME` 의 구조는 `CFileDialog` 개체입니다.|  
|[CFileDialog::GetPathName](#getpathname)|선택한 파일의 전체 경로 반환합니다.|  
|[CFileDialog::GetReadOnlyPref](#getreadonlypref)|선택한 파일의 읽기 전용 상태를 반환합니다.|  
|[CFileDialog::GetResult](#getresult)|사용자 대화 상자에서 수행 하는 항목을 가져옵니다.|  
|[CFileDialog::GetResults](#getresults)|다중 선택을 허용 하는 대화 상자에서 사용자의 선택 항목을 가져옵니다.|  
|[CFileDialog::GetSelectedControlItem](#getselectedcontrolitem)|대화 상자에서 지정 된 컨테이너 컨트롤에서 특정 항목을 가져옵니다.|  
|[CFileDialog::GetStartPosition](#getstartposition)|파일 이름 목록의 첫 번째 요소의 위치를 반환합니다.|  
|[CFileDialog::HideControl](#hidecontrol)|탐색기 스타일에서 지정된 된 컨트롤을 숨깁니다 **열려** 또는 **다른 이름으로 저장** 일반 대화 상자.|  
|[CFileDialog::IsPickFoldersMode](#ispickfoldersmode)|있는지 여부를 확인 폴더 선택 모드에서 현재 대화 상자.|  
|[CFileDialog::MakeProminent](#makeprominent)|위치 대화 상자에서 컨트롤 구별 되도록에 비해 다른 추가 된 컨트롤입니다.|  
|[CFileDialog::RemoveControlItem](#removecontrolitem)|대화 상자에서 컨테이너 컨트롤에서 항목을 제거 합니다.|  
|[CFileDialog::SetCheckButtonState](#setcheckbuttonstate)|대화 상자에서 확인 단추 (확인란)의 현재 상태를 설정합니다.|  
|[CFileDialog::SetControlItemState](#setcontrolitemstate)|대화 상자에 있는 컨테이너 컨트롤에서 항목의 현재 상태를 설정 합니다.|  
|[CFileDialog::SetControlItemText](#setcontrolitemtext)|컨트롤 항목의 텍스트를 설정합니다. 예를 들어, 라디오 단추 또는 메뉴의 항목을 함께 제공 되는 텍스트입니다.|  
|[CFileDialog::SetControlLabel](#setcontrollabel)|예: 단추 텍스트 또는 편집 상자 레이블 컨트롤에 연결 된 텍스트를 설정 합니다.|  
|[CFileDialog::SetControlState](#setcontrolstate)|현재 표시 여부를 설정 하 고 지정 된 컨트롤의 상태를 사용 하도록 설정 합니다.|  
|[CFileDialog::SetControlText](#setcontroltext)|탐색기 스타일에 지정된 된 컨트롤에 대 한 텍스트 설정 **열려** 또는 **다른 이름으로 저장** 일반 대화 상자.|  
|[CFileDialog::SetDefExt](#setdefext)|탐색기 스타일에 대 한 기본 파일 이름 확장명 설정 **열려** 또는 **다른 이름으로 저장** 일반 대화 상자.|  
|[CFileDialog::SetEditBoxText](#seteditboxtext)|편집 상자 컨트롤에서 현재 텍스트를 설정합니다.|  
|[CFileDialog::SetProperties](#setproperties)|저장 중인 항목에 사용할 기본값을 정의하는 속성 저장소를 제공합니다.|  
|[CFileDialog::SetSelectedControlItem](#setselectedcontrolitem)|옵션 단추 그룹 또는 대화 상자에 콤보 상자에서 특정 항목의 선택된 상태를 설정 합니다.|  
|[CFileDialog::SetTemplate](#settemplate)|설정에 대 한 대화 상자 템플릿에 `CFileDialog` 개체입니다.|  
|[CFileDialog::StartVisualGroup](#startvisualgroup)|대화 상자에서 시각적 그룹을 선언합니다. 이 그룹에 해당 요소를 추가 하는 이후에 모든 "추가" 메서드를 호출 합니다.|  
|[CFileDialog::UpdateOFNFromShellDialog](#updateofnfromshelldialog)|에 저장 된 데이터를 업데이트 하는 `m_ofn` 파일 대화 상자의 현재 상태와 일치 하는 멤버 변수입니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CFileDialog::OnButtonClicked](#onbuttonclicked)|단추를 클릭할 때 호출 됩니다.|  
|[CFileDialog::OnCheckButtonToggled](#oncheckbuttontoggled)|확인란이 선택/선택 취소 하는 경우 호출 됩니다.|  
|[CFileDialog::OnControlActivating](#oncontrolactivating)|컨트롤은 활성화 될 때 호출 됩니다.|  
|[CFileDialog::OnFileNameChange](#onfilenamechange)|처리는 `WM_NOTIFY CDN_SELCHANGE` 메시지입니다.|  
|[CFileDialog::OnFileNameOK](#onfilenameok)|대화 상자에 입력 된 파일 이름 유효성을 검사 합니다.|  
|[CFileDialog::OnFolderChange](#onfolderchange)|처리는 `WM_NOTIFY CDN_FOLDERCHANGE` 메시지입니다.|  
|[CFileDialog::OnInitDone](#oninitdone)|처리는 `WM_NOTIFY CDN_INITDONE` 메시지입니다.|  
|[CFileDialog::OnItemSelected](#onitemselected)|컨테이너 항목을 선택 하면 호출 됩니다.|  
|[CFileDialog::OnLBSelChangedNotify](#onlbselchangednotify)|파일 선택이 변경 될 때 사용자 지정 작업을 수행할 수 있습니다.|  
|[CFileDialog::OnShareViolation](#onshareviolation)|핸들 공유 위반 합니다.|  
|[CFileDialog::OnTypeChange](#ontypechange)|처리는 `WM_NOTIFY CDN_TYPECHANGE` 메시지입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CFileDialog::m_ofn](#m_ofn)|Windows `OPENFILENAME` 구조입니다. 기본 파일 대화 상자 매개 변수에 대 한 액세스를 제공합니다.|  
  
## <a name="remarks"></a>설명  
 공용 파일 대화 상자를 사용 하면 파일 선택 대화 상자, 예를 들어를 구현할 수 **열려 있는 파일** 및 **다른 이름으로 저장**, Windows 표준와 일치 하는 방식에서입니다.  
  
 사용할 수 있습니다 `CFileDialog` 도 제공 하는 생성자로 있는 그대로 또는 사용자 고유의 대화 상자 클래스에서 파생 시킬 수 있습니다 `CFileDialog` 필요에 따라 생성자 작성 하 고 있습니다. 어떤 경우 든 이러한 대화 상자는 처럼 동작 표준 MFC 대화 상자에서 파생 되기 때문에 [CCommonDialog 클래스](../../mfc/reference/ccommondialog-class.md)합니다. `CFileDialog`COMMDLG에 의존합니다. Windows에 포함 된 DLL 파일입니다.  
  
 모양과 기능을 모두는 `CFileDialog` 와 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 이전 버전의 Windows에서 다릅니다. 기본 `CFileDialog` 를 자동으로 새 사용 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 없이 컴파일되면 해당 프로그램은 경우에 코드 변경 및 실행 하는 스타일 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]합니다. 사용 된 `bVistaStyle` 이 자동 업데이트를 수동으로 재정의 하는 생성자의 매개 변수입니다. 자동 업데이트는 예외는 사용자 지정된 대화 상자입니다. 또한 새 스타일으로 변환 되지 됩니다. 생성자에 대 한 자세한 내용은 참조 [CFileDialog::CFileDialog](#cfiledialog)합니다.  
  
> [!NOTE]
>  컨트롤 ID 시스템에 다른 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 에서 이전 버전의 Windows 사용 하는 경우는 `CFileDialog`합니다. 에 대 한 모든 참조를 업데이트 해야 `CFileDialog` 이전 버전의 Windows에서 프로젝트를 이식할 수 전에 코드에서 컨트롤입니다.  
  
 일부 `CFileDialog` 방법에서 지원 되지 않는 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]합니다. 메서드가 기능의 지원 여부에 대 한 정보에 대 한 개별 메서드 항목을 확인 합니다. 또한 상속된 된 다음 함수에서 지원 되지 않습니다는 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]:  
  
- [CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog)  
  
- [CDialog::OnSetFont](../../mfc/reference/cdialog-class.md#onsetfont)  
  
 에 대 한 windows 메시지는 `CFileDialog` 클래스를 사용 하는 운영 체제에 따라 달라 집니다. 예를 들어 Windows XP 지원 하지 않습니다 [CDialog::OnCancel](../../mfc/reference/cdialog-class.md#oncancel) 및 [CDialog::OnOK](../../mfc/reference/cdialog-class.md#onok) 에 대 한는 `CFileDialog` 클래스입니다. 그러나 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 지원 않는 합니다. 생성 되는 다양 한 메시지와 수신 된 순서에 대 한 자세한 내용은 참조 [CFileDialog 샘플: 로깅 이벤트 순서](../../visual-cpp-samples.md)합니다.  
  
 사용 하는 `CFileDialog` 개체를 사용 하 여 개체를 먼저 만들는 `CFileDialog` 생성자입니다. 대화 상자를 생성 한 후이 설정 하거나의 모든 값을 수정할 수 있습니다는 [CFileDialog::m_ofn](#m_ofn) 구조에서 값 또는 대화 상자 컨트롤의 상태를 초기화 합니다. `m_ofn` 형식의 구조는 `OPENFILENAME`합니다. 자세한 내용은 참조는 [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) Windows SDK에는 구조입니다.  
  
 대화 상자 컨트롤을 초기화 한 후 호출 된 [CFileDialog::DoModal](#domodal) 대화 상자를 표시 하려면 상자는 사용자의 경로 파일 이름을 입력할 수 있도록 합니다. `DoModal`사용자 확인 (IDOK) 이나 취소 (IDCANCEL) 단추를 클릭 여부를 반환 합니다. 경우 `DoModal` IDOK, 반환 중 하나를 사용할 수 있습니다는 `CFileDialog` 정보를 검색 하는 공용 멤버 함수는 사용자에 의해에 저장 합니다.  
  
> [!NOTE]
>  아래 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]를 여러 번 호출 [IFileDialog::SetFileTypes](http://msdn.microsoft.com/library/windows/desktop/bb775980) 하면 오류가 발생 합니다. 두 번째 호출으로 `SetFileTypes` 의 모든 인스턴스에 대해는 `CFileDialog` 돌아갑니다 `E_UNEXPECTED` 에서 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]합니다. 일부 `CFileDialog` 메서드 호출이 작동 `SetFileTypes`합니다. 예를 들어 두 호출 `CFileDialog::DoModal` 의 동일한 인스턴스에 대해는 `CFileDialog` 생성 [ASSERT](diagnostic-services.md#assert)합니다.  
  
 `CFileDialog`공유 위반, 파일 이름 유효성 검사 및 목록 상자 변경 알림을의 사용자 지정 처리 작업을 수행할 수 있는 몇 가지 보호 된 멤버를 포함 합니다. 이러한 보호 된 멤버는 대부분의 응용 프로그램 기본 처리를 자동으로 수행 되기 때문에 사용 하지 않아도 되는 콜백 함수입니다. 표준 가상 함수가 되기 때문에 이러한 함수에 대 한 메시지 맵 항목 필요 하지 않습니다.  
  
 Windows를 사용할 수 있습니다 [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) 함수는 오류에 대 한 자세한 내용을 보려면 및 대화 상자를 초기화 하는 동안 오류가 발생 한 것인지 확인 합니다.  
  
 소멸 `CFileDialog` 개체는 자동으로 처리 합니다. 호출할 필요가 없습니다 [CDialog::EndDialog](../../mfc/reference/cdialog-class.md#enddialog)합니다.  
  
 여러 파일을 선택 하는 사용자를 수 있게 하려면 설정는 `OFN_ALLOWMULTISELECT` 호출 하기 전에 플래그 `DoModal`합니다. 여러 파일 이름의 반환된 목록에 맞게 사용자 고유의 파일 이름 버퍼를 제공 해야 합니다. 대체 하 여이 작업을 수행 `m_ofn.lpstrFile` 버퍼에 대 한 포인터와 할당을 생성 하면 반복기는 `CFileDialog`를 호출 하기 전에 `DoModal`합니다.  
  
 설정 해야 또한 `m_ofn.nMaxFile` 가리키는 버퍼의 문자 수를 사용 하 여 `m_ofn.lpstrFile`합니다. 선택 하려면 파일의 최대 수를 설정 하는 경우 `n`, 필요한 버퍼 크기는 `n * (_MAX_PATH + 1) + 1`합니다. 버퍼에 반환 되는 첫 번째 항목에는 파일이 선택 된 폴더의 경로입니다. 에 대 한 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]-스타일 대화 상자, 디렉터리 및 파일 이름 문자열은 null로 종료 되는 마지막 파일 이름 뒤에 오는 추가 null 문자로 합니다. 이 형식의 공백을 포함 하는 긴 파일 이름을 반환할 탐색기 스타일 대화 상자를 사용 합니다. 이전 스타일 대화 상자에 대 한 디렉터리 및 파일 이름 문자열은 공백으로 및 함수에서 공백을 사용 하 여 파일 이름에 대 한 약식 파일 이름을 사용 합니다.  
  
 다음 예제에서는 버퍼를 검색 하 여 여러 파일 이름 목록을 사용 하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFCFiles#23](../../atl-mfc-shared/reference/codesnippet/cpp/cfiledialog-class_1.cpp)]  
  
 여러 파일 이름을 선택 하 여 사용자에 대 한 응답에서 버퍼 크기를 변경 하려면에서 새 클래스를 파생 해야 `CFileDialog` 재정의 [CFileDialog::OnFileNameChange](#onfilenamechange) 메서드.  
  
 새 클래스를 파생 하는 경우 `CFileDialog`, 모든 메시지를 처리 하는 메시지 맵을 사용할 수 있습니다. 기본 메시지 처리를 확장 하려면에서 클래스를 파생 `CFileDialog`, 메시지 맵을 새 클래스에 추가 하 고 새 메시지에 대 한 멤버 함수를 제공 합니다. 사용자 지정 대화 상자에 후크 함수를 제공할 필요가 없습니다.  
  
 대화 상자를 사용자 지정 하려면 클래스를 파생 `CFileDialog`, 사용자 지정 대화 상자 템플릿을 제공 하 고 확장 된 컨트롤에서 알림 메시지를 처리 한 메시지 맵을 추가 합니다. 기본 클래스를 모두 처리 되지 않은 메시지를 전달 합니다. 후크 함수를 사용자 지정할 필요가 없습니다.  
  
 사용 하는 경우는 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 의 스타일은 `CFileDialog`, 메시지 맵 및 대화 상자 템플릿을 사용할 수 없습니다. 대신, 유사한 기능에 대 한 COM 인터페이스를 사용 해야 합니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `CFileDialog`, 참조 [일반 대화 상자 클래스](../../mfc/common-dialog-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFileDialog`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdlgs.h  
  
##  <a name="addcheckbutton"></a>CFileDialog::AddCheckButton  
 대화 상자에 확인 단추를 추가합니다.  
  
```  
HRESULT AddCheckButton(
    DWORD dwIDCtl,  
    const CString& strLabel,  
    BOOL bChecked);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 추가 하려면 확인 단추의 ID입니다.  
  
 `strLabel`  
 확인 단추 이름입니다.  
  
 `bChecked`  
 확인 단추의 현재 상태를 나타내는 부울입니다. `TRUE`선택 된 경우 `FALSE` 그렇지 않은 경우  
  
### <a name="remarks"></a>설명  
  
##  <a name="addcombobox"></a>CFileDialog::AddComboBox  
 대화 상자에 콤보 상자를 추가합니다.  
  
```  
HRESULT AddComboBox(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 추가 콤보 상자의 ID입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="addcontrolitem"></a>CFileDialog::AddControlItem  
 대화 상자에서 컨테이너 컨트롤에 항목을 추가 합니다.  
  
```  
HRESULT AddControlItem(
    DWORD dwIDCtl,  
    DWORD dwIDItem,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 항목을 추가할 컨테이너 컨트롤의 ID입니다.  
  
 `dwIDItem`  
 항목의 ID입니다.  
  
 `strLabel`  
 항목의 텍스트입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="addeditbox"></a>CFileDialog::AddEditBox  
 대화 상자에 입력란을 추가합니다.  
  
```  
HRESULT AddEditBox(
    DWORD dwIDCtl,  
    const CString& strText);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 추가할 입력란의 ID입니다.  
  
 `strText`  
 편집 상자 이름입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="addmenu"></a>CFileDialog::AddMenu  
 대화 상자에 메뉴를 추가합니다.  
  
```  
HRESULT AddMenu(
    DWORD dwIDCtl,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 추가할 메뉴의 ID입니다.  
  
 `strLabel`  
 메뉴 이름입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="addplace"></a>CFileDialog::AddPlace  
 목록에 폴더를 열거나 항목을 저장 하는 사용자에 대해 사용할 수 있는 배치를 추가 합니다.  
  
```  
void AddPlace(
    LPCWSTR lpszFolder,  
    FDAP fdap = FDAP_TOP) throw();

 
void AddPlace(
    IShellItem* psi,  
    FDAP fdap = FDAP_TOP) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszFolder`  
 사용자에 게 사용할 수 있게 하려면 해당 폴더에 대 한 경로입니다. 이 폴더 수만 있습니다.  
  
 `fdap`  
 목록 내에서 폴더 위치를 지정 합니다.  
  
 `psi`  
 사용자에 게 사용할 수 있게 하려면 폴더를 나타내는 IShellItem에 대 한 포인터입니다. 이 폴더 수만 있습니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="addpushbutton"></a>CFileDialog::AddPushButton  
 대화 상자에 단추를 추가 합니다.  
  
```  
HRESULT AddPushButton(
    DWORD dwIDCtl,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 추가 단추의 ID입니다.  
  
 `strLabel`  
 단추 이름입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="addradiobuttonlist"></a>CFileDialog::AddRadioButtonList  
 대화 상자에 옵션 단추 (라디오 단추) 그룹을 추가합니다.  
  
```  
HRESULT AddRadioButtonList(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 추가 옵션 단추 그룹의 ID입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="addseparator"></a>CFileDialog::AddSeparator  
 대화 상자에는 구분 기호를 추가합니다.  
  
```  
HRESULT AddSeparator(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 구분 기호 ID를 추가 합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="addtext"></a>CFileDialog::AddText  
 대화 상자에 텍스트를 추가합니다.  
  
```  
HRESULT AddText(
    DWORD dwIDCtl,  
    const CString& strText);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 추가 텍스트의 ID입니다.  
  
 `strText`  
 텍스트 이름입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="applyofntoshelldialog"></a>CFileDialog::ApplyOFNToShellDialog  
 현재 상태를 업데이트는 [CFileDialog](../../mfc/reference/cfiledialog-class.md) 에 저장 된 값을 기반으로 `m_ofn` 데이터 구조입니다.  
  
```  
void ApplyOFNToShellDialog();
```  
  
### <a name="remarks"></a>설명  
 버전의 Windows 하기 전에 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], 멤버 [OPENFILENAME](https://msdn.microsoft.com/library/ms911906.aspx) 데이터 구조를 지속적으로의 상태와 동기화 할는 `CFileDialog`합니다. 변경 내용이 [m_ofn](#m_ofn) 멤버 변수 대화 상자의 상태에 바로 반영 되었습니다. 또한 대화 상자의 상태 변경 내용이 즉시 업데이트 하는 `m_ofn` 멤버 변수입니다.  
  
 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]에 있는 값의 `m_ofn` 멤버 변수 및 상태에는 `CFileDialog` 항상 동기화 되어야 하는 것은 아닙니다. 상태를 강제로이 함수는 `CFileDialog` 일치 하도록 업데이트 하는 `m_ofn` 구조입니다. 동안 자동으로이 함수를 호출 하는 Windows [CFileDialog::DoModal](#domodal)합니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `CFileDialog` 아래 클래스 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], 참조 [CFileDialog 클래스](../../mfc/reference/cfiledialog-class.md)합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CFileDialog::UpdateOFNFromShellDialog](#updateofnfromshelldialog)합니다.  
  
##  <a name="cfiledialog"></a>CFileDialog::CFileDialog  
 표준 Windows 파일 대화 상자를 생성 하려면이 함수를 호출 합니다.  
  
```  
explicit CFileDialog(
    BOOL bOpenFileDialog,  
    LPCTSTR lpszDefExt = NULL,  
    LPCTSTR lpszFileName = NULL,  
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT,  
    LPCTSTR lpszFilter = NULL,  
    CWnd* pParentWnd = NULL,  
    DWORD dwSize = 0,  
    BOOL bVistaStyle = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bOpenFileDialog`  
 대화 상자 유형을 지정 하는 매개 변수입니다. 로 설정 `TRUE` 생성 하는 **파일 열기** 대화 상자. 로 설정 `FALSE` 생성 하는 **다른 이름으로 저장** 대화 상자.  
  
 [in] `lpszDefExt`  
 기본 파일 이름 확장명입니다. 확장에서 지정한 파일 이름 상자에 사용자 (사용자의 컴퓨터에 연결 된 하나) 알려진된 확장명이 포함 되어 있지 않으면, `lpszDefExt` 파일 이름에 자동으로 추가 됩니다. 이 매개 변수가 `NULL`, 없습니다 확장명이 추가 됩니다.  
  
 [in] `lpszFileName`  
 파일 이름 상자에 표시 되는 초기 파일 이름입니다. 경우 `NULL`, 초기 파일 이름 없이 표시 됩니다.  
  
 [in] `dwFlags`  
 대화 상자를 사용자 지정 하는 데 사용할 수 있는 하나 이상의 플래그의 조합입니다. 이러한 플래그에 대 한 참조는 [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) Windows SDK에는 구조입니다. 수정 하는 경우는 `m_ofn.Flags` 구조 멤버, 변경에서 비트 OR 연산자를 사용 하 여 기본 동작을 그대로 유지 합니다.  
  
 [in] `lpszFilter`  
 필터를 지정 하는 문자열 쌍 파일에 적용할 수 있습니다. 파일 필터를 지정 하면 필터 조건과 일치 하는 파일만 파일 목록에 표시 됩니다. 파일 필터와 함께 작동 하는 방법에 대 한 자세한 내용은 설명 섹션을 참조 하십시오.  
  
 [in] `pParentWnd`  
 파일 대화 상자의 부모 또는 소유자 창에 대 한 포인터입니다.  
  
 [in] `dwSize`  
 크기는 `OPENFILENAME` 구조입니다. 이 값은 운영 체제 버전에 따라 달라 집니다. MFC 대화 상자를 만들 적합 한 유형의 결정 하기 위해이 매개 변수를 사용 합니다 (예를 들어 new [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] NT4 대화 상자 대신 대화 상자). 프로그램이 실행 되는 운영 체제 버전을 기반으로 기본 크기는 MFC 코드를 사용 하 여 해당 대화 상자 크기를 결정 하는 0 이면 합니다.  
  
 [in] `bVistaStyle`  
 **참고** 이 매개 변수는 Visual Studio 2008에서 사용할 수 있는 이상에서 및을 새 스타일 대화 상자에서 실행 하는 경우에 사용 될 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 이상.  
  
 파일 대화 상자의 스타일을 지정 하는 매개 변수입니다. 로 설정 `TRUE` 새 Vista 스타일 파일 대화 상자를 사용 하도록 합니다. 그렇지 않으면 이전 스타일의 대화 상자를 사용 됩니다. Vista에서 실행에 대 한 자세한 내용은 설명 섹션을 참조 합니다.  
  
### <a name="remarks"></a>설명  
 어느 한 **파일 열기** 또는 **다른 이름으로 저장** 값에 따라 대화 상자를 생성 `bOpenFileDialog`합니다.  
  
 사용 하 여 기본 확장 지정 `lpszDefExt` 있기 때문에 거의 예측 가능한 어떤 확장 사용자의 컴퓨터에서 파일 연결에는 예상 되는 동작을 얻을 수 없습니다. 고유한 클래스를 파생 시켜 더 많이 제어할 기본 확장 프로그램을 추가 해야 할 경우 `CFileDialog`, 재정의 `CFileDialog::OnFileNameOK` 고유 확장 프로그램 처리를 수행 하는 메서드.  
  
 사용자가 여러 파일을 선택할 수 있도록 설정 된 `OFN_ALLOWMULTISELECT` 호출 하기 전에 플래그 [DoModal](#domodal)합니다. 여러 파일 이름의 반환된 목록 저장할 고유한 파일 이름 버퍼를 제공 해야 합니다. 대체 하 여이 작업을 수행 `m_ofn.lpstrFile` 버퍼에 대 한 포인터와 할당을 생성 하면 반복기는 [CFileDialog](../../mfc/reference/cfiledialog-class.md)를 호출 하기 전에 `DoModal`합니다. 설정 해야 또한 `m_ofn.nMaxFile` 가리키는 버퍼에 있는 문자의 수와 `m_ofn.lpstrFile`합니다. 선택 하려면 파일의 최대 수를 설정 하는 경우 `n`, 필요한 버퍼 크기는 `n`*(_MAX_PATH + 1) + 1입니다. 예:  
  
 [!code-cpp[NVC_MFCFiles#23](../../atl-mfc-shared/reference/codesnippet/cpp/cfiledialog-class_1.cpp)]  
  
 마우스 또는 키보드를 사용 하 여 크기 조정 된 탐색기 스타일 대화 상자에 사용자를 사용 하려면 설정의 `OFN_ENABLESIZING` 플래그입니다. 이 플래그를 설정 하는 것은 후크 프로시저 또는 사용자 지정 서식 파일을 제공 하는 경우에 필요 합니다. 플래그는 탐색기 스타일 대화 상자 에서만 작동 이전 스타일 대화 상자 크기를 조정할 수 없습니다.  
  
 `lpszFilter` 매개 변수는 파일 목록에 표시 되는 파일 있어야 하는 파일 이름의 형식을 사용 합니다. 문자열 쌍의 첫 번째 문자열; 필터를 설명합니다. 두 번째 문자열에는 파일 이름 확장명을 사용을 나타냅니다. 구분 기호로 세미콜론 (';' 문자)를 사용 하 여 여러 확장명을 지정할 수 있습니다. 두 개의로 끝나는 문자열 ' &#124;' 문자 다음에 `NULL` 문자입니다. 사용할 수도 있습니다는 [CString](../../atl-mfc-shared/using-cstring.md) 이 매개 변수에 대 한 개체입니다.  
  
 예를 들어 [!INCLUDE[ofprexcel](../../mfc/reference/includes/ofprexcel_md.md)] 다른 규칙 으로부터 확장.xlc (차트) 또는.xls (워크시트)에 있는 파일을 열 수 있습니다. Excel에 대 한 필터는 다음과 같이 작성할 수 없습니다.  
  
 [!code-cpp[NVC_MFCFiles#24](../../atl-mfc-shared/reference/codesnippet/cpp/cfiledialog-class_2.cpp)]  
  
 그러나이 문자열을 직접 사용 하려는 경우 업데이트는 `OPENFILENAME` 구조를 문자열 대신 세로 막대에는 ' \0', null 문자로 구분 해야 ('&#124;').  
  
 `bVistaStyle` 매개 변수는 실행 하는 경우에 적용할 수 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]합니다. 이전 버전의 Windows에서이 매개 변수는 무시 됩니다. 경우 `bVistaStyle` 로 설정 된 `TRUE`프로그램으로 Visual Studio 2008 이상에서는 새 Vista 스타일을 컴파일할 때 **파일 대화 상자** 사용 됩니다. 그렇지 않으면 이전 MFC 스타일 **파일 대화 상자** 사용 됩니다.  
  
 대화 상자 템플릿은 기반으로 하는 대화 상자에서 지원 되지 않습니다.`bVistaStyle`  
  
### <a name="example"></a>예제  
  예를 참조 [CFileDialog::DoModal](#domodal)합니다.  
  
##  <a name="domodal"></a>CFileDialog::DoModal  
 Windows 공용 파일 대화 상자를 표시 하 고 사용자가 파일 및 디렉터리를 검색 하 고 파일 이름을 지정 하도록 허용 하려면이 함수를 호출 합니다.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>반환 값  
 **IDOK** 또는 **IDCANCEL**합니다. 경우 **IDCANCEL** 은 Windows 호출 반환 [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) 함수 오류가 발생 한 것인지 확인 합니다.  
  
 **IDOK** 및 **IDCANCEL** 는 사용자 확인 또는 취소 단추를 선택 하는지 여부를 나타내는 상수입니다.  
  
### <a name="remarks"></a>설명  
 멤버를 설정 하 여 다양 한 파일 대화 상자 옵션을 초기화 하려는 경우는 **m_ofn** 구조를 호출 하기 전에이 작업을 수행 해야 `DoModal`, 대화 상자 개체를 생성 한 후 하지만 합니다.  
  
 예를 들어 사용자가 여러 파일을 선택 하도록 허용 하려면 설정는 `OFN_ALLOWMULTISELECT` 호출 하기 전에 플래그 `DoModal`이 항목의 코드 예제에 나온 것 처럼 합니다.  
  
 대화 상자에서 옵션 대화 상자 확인 또는 취소 단추 또는 닫기가 선택 되어 사용자가 클릭 메뉴를 제어 하는 경우 컨트롤이 응용 프로그램에 반환 됩니다. 호출할 수 있습니다 설정 또는 정보를 검색 하는 다른 멤버 함수는 사용자 입력 대화 상자에 있습니다.  
  
 `DoModal`클래스에서 재정의 된 가상 함수인 `CDialog`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCFiles#25](../../atl-mfc-shared/reference/codesnippet/cpp/cfiledialog-class_3.cpp)]  
  
##  <a name="enableopendropdown"></a>CFileDialog::EnableOpenDropDown  
 드롭 다운 목록 열기 또는 저장 대화 상자에서 단추를 사용 하도록 설정 합니다.  
  
```  
HRESULT EnableOpenDropDown(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 드롭 다운 목록의 ID입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="endvisualgroup"></a>CFileDialog::EndVisualGroup  
 대화 상자에서 시각적 그룹에 요소가 추가 중지합니다.  
  
```  
HRESULT EndVisualGroup();
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고 반환 그렇지 않으면 오류 값입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getcheckbuttonstate"></a>CFileDialog::GetCheckButtonState  
 대화 상자에서 확인 단추 (확인란)의 현재 상태를 검색합니다.  
  
```  
HRESULT GetCheckButtonState(
    DWORD dwIDCtl,  
    BOOL& bChecked);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 확인란의 ID입니다.  
  
 `bChecked`  
 확인란의 상태입니다. `TRUE`checked; 나타냅니다. `FALSE` 선택 되지 않은 나타냅니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getcontrolitemstate"></a>CFileDialog::GetControlItemState  
 대화 상자에 있는 컨테이너 컨트롤에 있는 항목의 현재 상태를 검색 합니다.  
  
```  
HRESULT GetControlItemState(
    DWORD dwIDCtl,  
    DWORD dwIDItem,  
    CDCONTROLSTATEF& dwState);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 컨테이너 컨트롤의 ID입니다.  
  
 `dwIDItem`  
 항목의 ID입니다.  
  
 `dwState`  
 컨트롤의 현재 상태를 나타내는 CDCONTROLSTATE 열거형에서 더 많은 값 중 하나를 수신 하는 변수를 가리킵니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getcontrolstate"></a>CFileDialog::GetControlState  
 현재 표시 여부를 검색 하 고 지정 된 컨트롤의 상태를 사용 하도록 설정 합니다.  
  
```  
HRESULT GetControlState(
    DWORD dwIDCtl,  
    CDCONTROLSTATEF& dwState);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 컨트롤의 ID입니다.  
  
 `dwState`  
 컨트롤의 현재 상태를 나타내는 CDCONTROLSTATE 열거형에서 하나 이상의 값을 수신 하는 변수를 가리킵니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="geteditboxtext"></a>CFileDialog::GetEditBoxText  
 편집 상자 컨트롤에서 현재 텍스트를 검색합니다.  
  
```  
HRESULT GetEditBoxText(
    DWORD dwIDCtl,  
    CString& strText);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 입력란의 ID입니다.  
  
 `strText`  
 텍스트 값입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getfileext"></a>CFileDialog::GetFileExt  
 대화 상자에 입력 된 파일 이름 확장명을 검색 하려면이 함수를 호출 합니다.  
  
```  
CString GetFileExt() const;  
```  
  
### <a name="return-value"></a>반환 값  
 파일 이름 확장명입니다.  
  
### <a name="remarks"></a>설명  
 예를 들어 파일의 이름을 입력 하는 경우에 데이터입니다. TXT, `GetFileExt` "TXT"를 반환 합니다.  
  
 경우 `m_ofn.Flags` 에 `OFN_ALLOWMULTISELECT` 플래그가 설정,이 문자열의 첫 번째 문자열을 파일 그룹 선택의 디렉터리 경로와 null로 끝나는 문자열의 시퀀스가 포함 된 다음에 사용자가 선택한 모든 파일의 이름을 합니다. 파일 경로 검색 하려면 사용 된 [GetStartPosition](#getstartposition) 및 [GetNextPathName](#getnextpathname) 멤버 함수입니다.  
  
##  <a name="getfilename"></a>CFileDialog::GetFileName  
 대화 상자에 입력 된 파일의 이름을 검색 하려면이 함수를 호출 합니다.  
  
```  
CString GetFileName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 파일의 이름입니다.  
  
### <a name="remarks"></a>설명  
 파일의 이름에는 접두사와 확장명을 모두 포함 됩니다. 예를 들어 `GetFileName` "텍스트가 반환 됩니다. DAT "C:\FILES\TEXT.DAT 파일에 대 한 합니다.  
  
 경우 `m_ofn.Flags` 에 `OFN_ALLOWMULTISELECT` 플래그가 설정, 호출 해야 [GetStartPosition](#getstartposition) 및 [GetNextPathName](#getnextpathname) 를 파일 경로 검색 합니다.  
  
##  <a name="getfiletitle"></a>CFileDialog::GetFileTitle  
 대화 상자에 입력 된 파일의 제목을 검색 하려면이 함수를 호출 합니다.  
  
```  
CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 파일의 제목입니다.  
  
### <a name="remarks"></a>설명  
 파일의 제목이 접두사를 경로 또는 확장명 없이 포함 되어 있습니다. 예를 들어 `GetFileTitle` C:\FILES\TEXT.DAT 파일에 대 한 "TEXT"를 반환 합니다.  
  
 경우 `m_ofn.Flags` 에 `OFN_ALLOWMULTISELECT` 플래그가 설정,이 문자열의 첫 번째 문자열을 파일 그룹 선택의 디렉터리 경로와 null로 끝나는 문자열의 시퀀스가 포함 된 다음에 사용자가 선택한 모든 파일의 이름을 합니다. 이러한 이유로 사용는 [GetStartPosition](#getstartposition) 및 [GetNextPathName](#getnextpathname) 멤버 함수를 목록에서 다음 파일 이름을 검색 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CFileDialog::DoModal](#domodal)합니다.  
  
##  <a name="getfolderpath"></a>CFileDialog::GetFolderPath  
 현재 열려 있는 폴더 또는 탐색기 스타일 Open 또는 다른 이름으로 저장 일반 대화 상자에 대 한 디렉터리의 경로 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
CString GetFolderPath() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 현재 열려 있는 폴더 또는 디렉터리를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 대화 상자를 생성 합니다는 **OFN_EXPLORER** 스타일; 그렇지 메서드는 어설션이 실패 합니다.  
  
 대화 상자를 표시 하는 동안에이 메서드를 호출할 수 있습니다. 대화 상자가 닫힌 후이 기능을 더 이상 사용, 및 메서드는 어설션을 함께 실패 합니다.  
  
##  <a name="getifiledialogcustomize"></a>CFileDialog::GetIFileDialogCustomize  
 검색에 대 한 내부 COM 개체에 대 한 포인터는 주어진 [CFileDialog](../../mfc/reference/cfiledialog-class.md)합니다.  
  
```  
IFileDialogCustomize* GetIFileDialogCustomize();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 내부 COM 개체에 대 한 포인터는 `CFileDialog`합니다. 이 포인터를 적절 하 게 해제 하기 위해 작업은 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 사용 하 여 에서만 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 있는 개체와 `bVistaStyle` 로 설정 `true`합니다. 이 함수를 사용 하는 경우 때 `bVistaStyle` 은 `false`를 반환 합니다 `NULL` 릴리스 모드가 고 디버그 모드에서 어설션 throw 합니다.  
  
 에 대 한 자세한 내용은 `IFileDialogCustomize` 인터페이스를 참조 [IFileDialogCustomize](http://msdn.microsoft.com/library/windows/desktop/bb775912)합니다.  
  
### <a name="example"></a>예제  
 이 예에서는 내부 COM 개체를 검색합니다. 이 코드 예제를 실행 하려면 컴파일해야 아래 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]합니다.  
  
 [!code-cpp[NVC_MFC_CFileDialog#4](../../mfc/reference/codesnippet/cpp/cfiledialog-class_4.cpp)]  
  
##  <a name="getifileopendialog"></a>CFileDialog::GetIFileOpenDialog  
 검색에 대 한 내부 COM 개체에 대 한 포인터는 주어진 `CFileDialog`합니다.  
  
```  
IFileOpenDialog* GetIFileOpenDialog();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 내부 COM 개체에 대 한 포인터는 `CFileDialog`합니다. 이 포인터를 적절 하 게 해제 하기 위해 작업은 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 사용 하 여 에서만 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 있는 개체와 `bVistaStyle` 로 설정 `true`합니다. 이 함수는 반환 `NULL` 경우는 `CFileDialog` 않습니다는 **열려** 대화 상자 또는 `bVistaStyle` 로 설정 된 `false`합니다. 이 최종 경우에만 반환 `NULL` -릴리스 모드에서 디버그 모드에서 throw 됩니다 한 어설션입니다.  
  
 에 대 한 자세한 내용은 `IFileOpenDialog` 인터페이스를 참조 [IFileOpenDialog](http://msdn.microsoft.com/library/windows/desktop/bb775834)합니다.  
  
### <a name="example"></a>예제  
 이 예에서는 내부 COM 개체를 검색합니다. 이 코드를 실행 하려면 컴파일해야 아래 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]합니다.  
  
 [!code-cpp[NVC_MFC_CFileDialog#2](../../mfc/reference/codesnippet/cpp/cfiledialog-class_5.cpp)]  
  
##  <a name="getifilesavedialog"></a>CFileDialog::GetIFileSaveDialog  
 검색에 대 한 내부 COM 개체에 대 한 포인터는 주어진 `CFileDialog`합니다.  
  
```  
IFileSaveDialog* GetIFileSaveDialog();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 내부 COM 개체에 대 한 포인터는 `CFileDialog`합니다. 이 포인터를 적절 하 게 해제 하기 위해 작업은 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 사용 하 여 에서만 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 있는 개체와 `bVistaStyle` 로 설정 `true`합니다. 이 함수는 반환 `NULL` 경우는 `CFileDialog` 않습니다는 **저장** 대화 상자 또는 `bVistaStyle` 로 설정 된 `false`합니다. 이 최종 경우에만 반환 `NULL` -릴리스 모드에서 디버그 모드에서 throw 됩니다 한 어설션입니다.  
  
 에 대 한 자세한 내용은 `IFileSaveDialog` 인터페이스를 참조 [IFileSaveDialog](http://msdn.microsoft.com/library/windows/desktop/bb775688)합니다.  
  
### <a name="example"></a>예제  
 이 예에서는 내부 COM 개체를 검색합니다. 이 코드 예제를 실행 하려면 컴파일해야 아래 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]합니다.  
  
 [!code-cpp[NVC_MFC_CFileDialog#3](../../mfc/reference/codesnippet/cpp/cfiledialog-class_6.cpp)]  
  
##  <a name="getnextpathname"></a>CFileDialog::GetNextPathName  
 대화 상자에서 선택한 그룹에서 다음 파일 이름을 검색 하려면이 함수를 호출 합니다.  
  
```  
CString GetNextPathName(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 에 대 한 참조는 **위치** 이전에서 반환 된 값 `GetNextPathName` 또는 `GetStartPosition` 함수 호출 합니다. **NULL** 목록의 끝에 도달한 경우.  
  
### <a name="return-value"></a>반환 값  
 파일의 전체 경로입니다.  
  
### <a name="remarks"></a>설명  
 파일의 경로 파일의 제목와 전체 디렉터리 경로 포함 됩니다. 예를 들어 `GetNextPathName` "C:\FILES\TEXT를 반환 합니다. DAT "C:\FILES\TEXT.DAT 파일에 대 한 합니다. 사용할 수 있습니다 `GetNextPathName` 을 호출 하 여 초기 위치를 설정 하는 경우 앞으로 반복 루프에서 `GetStartPosition`합니다.  
  
 선택 영역을 하나의 파일로 구성 된 경우 해당 파일 이름이 반환 됩니다.  
  
##  <a name="getofn"></a>CFileDialog::GetOFN  
 연결 된 검색 **OPENFILENAME** 구조입니다.  
  
```  
const OPENFILENAME& GetOFN() const;  
  
OPENFILENAME& GetOFN();
```  
  
### <a name="return-value"></a>반환 값  
 [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) 구조입니다.  
  
### <a name="remarks"></a>설명  
 이 함수의 두 번째 버전을 사용 하 여의 모양을 초기화 하는 **파일 열기** 또는 **다른 이름으로 저장** 상태로 함께 해당 스크립트가 표시 되는 생성 된 후 대화 상자는 `DoModal` 멤버 함수입니다. 예를 들어, 설정할 수는 **lpstrTitle** 소속 **m_ofn** 캡션에 대화 상자를 원하는 합니다.  
  
##  <a name="getpathname"></a>CFileDialog::GetPathName  
 대화 상자에 입력 된 파일의 전체 경로 검색 하려면이 함수를 호출 합니다.  
  
```  
CString GetPathName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 파일의 전체 경로입니다.  
  
### <a name="remarks"></a>설명  
 파일의 경로 파일의 제목와 전체 디렉터리 경로 포함 됩니다. 예를 들어 `GetPathName` "C:\FILES\TEXT를 반환 합니다. DAT "C:\FILES\TEXT.DAT 파일에 대 한 합니다.  
  
 경우 `m_ofn.Flags` 에 `OFN_ALLOWMULTISELECT` 플래그가 설정,이 문자열에는 시퀀스의 null teminated는 첫 번째 문자열을 파일 그룹 선택의 디렉터리 경로 가진 문자열을 다음에 사용자가 선택한 모든 파일의 이름을 합니다. 이러한 이유로 사용는 [GetStartPosition](#getstartposition) 및 [GetNextPathName](#getnextpathname) 멤버 함수를 목록에서 다음 파일 이름을 검색 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CFileDialog::DoModal](#domodal)합니다.  
  
##  <a name="getreadonlypref"></a>CFileDialog::GetReadOnlyPref  
 Windows 표준 파일 열기 및 파일 이름으로 저장 대화 상자에서 읽기 전용 확인란이 선택 되어 있는지 여부를 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL GetReadOnlyPref() const;  
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 대화 상자에서 읽기 전용 확인란을 선택 합니다. 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 읽기 전용 확인란을 설정 하 여 숨길 수 있습니다는 `OFN_HIDEREADONLY` 에 스타일을 `CFileDialog` 생성자입니다.  
  
> [!NOTE]
> [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]스타일 `CFileDialog` 개체는이 함수를 지원 하지 않습니다. 이 함수를 사용 하는 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 스타일 `CFileDialog` 시킵니다 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)합니다.   
  
##  <a name="getresult"></a>CFileDialog::GetResult  
 사용자 대화 상자에서 수행 하는 항목을 검색 합니다.  
  
```  
IShellItem* GetResult() throw();
```  
  
### <a name="return-value"></a>반환 값  
 사용자가 선택한 항목을 나타내는 IShellItem에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getresults"></a>CFileDialog::GetResults  
 다중 선택을 허용 하는 대화 상자에서 사용자의 선택 항목을 검색 합니다.  
  
```  
IShellItemArray* GetResults() throw();
```  
  
### <a name="return-value"></a>반환 값  
 대화 상자에서 선택한 항목에 액세스할 수 있는 한 IShellItemArray에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getselectedcontrolitem"></a>CFileDialog::GetSelectedControlItem  
 대화 상자에서 지정 된 컨테이너 컨트롤에서 특정 항목을 검색합니다.  
  
```  
HRESULT GetSelectedControlItem(
    DWORD dwIDCtl,  
    DWORD& dwIDItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 컨테이너 컨트롤의 ID입니다.  
  
 `dwIDItem`  
 사용자 컨트롤에서 선택한 항목의 ID입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getstartposition"></a>CFileDialog::GetStartPosition  
 목록에서 첫 번째 파일 경로 이름의 위치를 검색 하려면이 멤버 함수를 호출 하 여 경우 `m_ofn.Flags` 에 `OFN_ALLOWMULTISELECT` 플래그가 설정 합니다.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **위치** 반복;에 대해 사용할 수 있는 값 **NULL** 목록이 비어 있는 경우.  
  
##  <a name="hidecontrol"></a>CFileDialog::HideControl  
 탐색기 스타일 Open 또는 다른 이름으로 저장 일반 대화 상자에서 지정 된 컨트롤을 숨기려면이 멤버 함수를 호출 합니다.  
  
```  
void HideControl(int nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `nID`  
 숨기는 컨트롤의 ID입니다.  
  
### <a name="remarks"></a>설명  
 대화 상자를 생성 합니다는 **OFN_EXPLORER** 스타일; 그렇지 않으면, 함수는 어설션이 실패 합니다.  
  
##  <a name="ispickfoldersmode"></a>CFileDialog::IsPickFoldersMode  
 현재 대화 상자에서 폴더 선택 모드 인지 여부를 확인 합니다.  
  
```  
BOOL IsPickFoldersMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`폴더 선택 모드;에서 대화 상자 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="m_ofn"></a>CFileDialog::m_ofn  
 `m_ofn`형식의 구조 `OPENFILENAME`합니다. 이 구조에 있는 데이터의 현재 상태를 나타내는 `CFileDialog`합니다.  
  
### <a name="remarks"></a>설명  
 이 구조를 사용 하 여의 모양을 초기화는 **파일 열기** 또는 **다른 이름으로 저장** 생성 하면 하지만 사용 하 여 표시 하기 전에 대화 상자는 [DoModal](#domodal) 메서드. 예를 들어, 설정할 수는 `lpstrTitle` 소속 `m_ofn` 캡션에 대화 상자를 원하는 합니다.  
  
 와 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 의 스타일 [CFileDialog](../../mfc/reference/cfiledialog-class.md), `m_ofn` 항상 대화 상자의 상태와 일치 하도록 작성 된 것은 아닙니다. 이전 버전의 Windows에서 대화 상자와 동기화 합니다. 참조 [CFileDialog::ApplyOFNToShellDialog](#applyofntoshelldialog) 및 [CFileDialog::UpdateOFNFromShellDialog](#updateofnfromshelldialog) 동기화에 대 한 자세한 내용은 `m_ofn` 구조 및 `CFileDialog` 상태 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]합니다.  
  
 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]특정 멤버와의 플래그 스타일 파일 대화 상자를 지원 하지 않습니다는 `CFileDialog`합니다. 결과적으로, 이러한 효과가 없습니다.  
  
 다음은에서 지원 되지 않는 멤버 목록이 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]:  
  
- `lpstrCustomFilter`  
  
- `lpstrInitialDir`  
  
- `lCustData`  
  
- `lpfnHook`  
  
- `lpTemplateName`  
  
 다음과 같은 플래그는 지원 되지 않으며 따라서 효과가 없습니다. 사용 하는 경우는 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 의 스타일 `CFileDialog`:  
  
-   OFN_ENABLEHOOK  
  
-   OFN_ENABLEINCLUDENOTIFY  
  
-   OFN_ENABLETEMPLATE  
  
-   OFN_ENABLETEMPLATEHANDLE  
  
-   OFN_EXPLORER  
  
-   OFN_EXTENSIONDIFFERENT  
  
-   OFN_HIDEREADONLY  
  
-   OFN_LONGNAMES-항상 효과적으로에[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
-   OFN_NOLONGNAMES-항상 효과적으로 해제[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
-   OFN_NONETWORKBUTTON-항상 효과적으로에[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
-   OFN_READONLY  
  
-   OFN_SHOWHELP  
  
 이 구조에 대 한 자세한 내용은 참조는 [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) Windows SDK에는 구조입니다.  
  
##  <a name="makeprominent"></a>CFileDialog::MakeProminent  
 위치 대화 상자에서 컨트롤 구별 되도록에 비해 다른 컨트롤입니다.  
  
```  
HRESULT MakeProminent(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 컨트롤의 ID입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="onbuttonclicked"></a>CFileDialog::OnButtonClicked  
 단추를 클릭할 때 호출 됩니다.  
  
```  
virtual void OnButtonClicked(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 단추의 ID입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="oncheckbuttontoggled"></a>CFileDialog::OnCheckButtonToggled  
 확인란 표시 상태 checked 또는 unchecked 때 호출 됩니다.  
  
```  
virtual void OnCheckButtonToggled(
    DWORD dwIDCtl,  
    BOOL bChecked);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 확인란의 ID입니다.  
  
 `bChecked`  
 Checked 또는 unchecked 합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="oncontrolactivating"></a>CFileDialog::OnControlActivating  
 컨트롤이 활성화 될 때 호출 됩니다.  
  
```  
virtual void OnControlActivating(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 컨트롤의 ID입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="onfilenamechange"></a>CFileDialog::OnFileNY` `변경  
 처리 하려는 경우이 메서드를 재정의 `WM_NOTIFY` `CDN_SELCHANGE` 메시지입니다.  
  
```  
virtual void OnFileNameChange();
```  
  
### <a name="remarks"></a>설명  
 시스템은 보냅니다는 `CDN_SELCHANGE` 사용자가 새 파일 또는 폴더의 파일 목록에서 선택 하는 경우 메시지는 **열려** 또는 **다른 이름으로 저장** 대화 상자. 이 메시지에 대 한 응답으로 작업을 수행 하려는 경우이 메서드를 재정의 합니다.  
  
 시스템은 OFN_EXPLORER 플래그가 설정 대화 상자를 만든 경우에이 메시지를 보냅니다. 알림에 대 한 자세한 내용은 참조 [CDN_SELCHANGE](http://msdn.microsoft.com/library/windows/desktop/ms646865)합니다. OFN_EXPLORER 플래그에 대 한 정보를 참조 하십시오.는 [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) 구조 및 [열기 및 저장으로 대화 상자](http://msdn.microsoft.com/library/windows/desktop/ms646960)합니다.  
  
##  <a name="onfilenameok"></a>CFileDialog::OnFileNameOK  
 공용 파일 대화 상자에 입력 되는 파일 이름의 사용자 지정 유효성 검사를 제공 하려는 경우에이 함수를 재정의 합니다.  
  
```  
virtual BOOL OnFileNameOK();
```  
  
### <a name="return-value"></a>반환 값  
 파일 이름이 올바른 파일 이름을; 이면 1 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 사용 하면 어떤 이유로 든 응용 프로그램 관련에 대 한 파일 이름을 거부할 수 있습니다. 일반적으로 프레임 워크 파일의 기본 유효성 검사를 제공 하 고 잘못 된 파일 이름을 입력 한 경우 메시지 상자를 표시 하기 때문에이 함수를 사용할 필요가 없습니다.  
  
 1이 반환 되 면 대화 상자 사용자가 다른 파일 이름을 입력 하는 표시 된 상태로 유지 됩니다. 반환 되는 0 이면 대화 상자를 해제 하는 대화 상자 프로시저입니다. 다른 0이 아닌 반환 값 현재 예약 되어 있으므로 사용 하지 않아야 합니다.  
  
##  <a name="onfolderchange"></a>CFileDialog::OnFolderChange  
 처리 하려면이 함수를 재정의 하는 **WM_NOTIFYCDN_FOLDERCHANGE** 메시지입니다.  
  
```  
virtual void OnFolderChange();
```  
  
### <a name="remarks"></a>설명  
 알림 메시지는 Open 또는 다른 이름으로 저장 대화 상자에서 새 폴더를 열 때 전송 됩니다.  
  
 대화 상자 OFN_EXPLORER 스타일을 사용 하 여 만든 경우에 알림이 전송 됩니다. 알림에 대 한 자세한 내용은 참조 [CDN_FOLDERCHANGE](http://msdn.microsoft.com/library/windows/desktop/ms646859)합니다. OFN_EXPLORER 스타일에 대 한 정보를 참조 하십시오.는 [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) 구조 및 [열기 및 저장으로 대화 상자](http://msdn.microsoft.com/library/windows/desktop/ms646960)합니다.  
  
##  <a name="oninitdone"></a>CFileDialog::OnInitDone  
 처리 하려면이 함수를 재정의 하는 `WM_NOTIFY` `CDN_INITDONE` 메시지입니다.  
  
```  
virtual void OnInitDone();
```  
  
### <a name="remarks"></a>설명  
 시스템에서 컨트롤 정렬 완료 되 면 시스템은이 알림 메시지를 보냅니다는 **열려** 또는 **다른 이름으로 저장** 자식 대화 상자의 컨트롤에 대 한 공간을 만들기 위해 대화 상자.  
  
 시스템이 대화 상자 OFN_EXPLORER 스타일을 사용 하 여 만든 경우에 보냅니다. 알림에 대 한 자세한 내용은 참조 [CDN_INITDONE](http://msdn.microsoft.com/library/windows/desktop/ms646863)합니다. OFN_EXPLORER 스타일에 대 한 정보를 참조 하십시오.는 [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) 구조 및 [열기 및 저장으로 대화 상자](http://msdn.microsoft.com/library/windows/desktop/ms646960)합니다.  
  
> [!NOTE]
> [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]스타일 파일 대화 상자에서이 함수를 지원 하지 않습니다. 이 함수를 사용 하는 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 스타일 파일 대화 상자를 발생 시킵니다 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)합니다. 
  
##  <a name="onitemselected"></a>CFileDialog::OnItemSelected  
 컨테이너 항목을 선택할 때 호출 됩니다.  
  
```  
virtual void OnItemSelected(
    DWORD dwIDCtl,  
    DWORD dwIDItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 컨테이너 컨트롤의 ID입니다.  
  
 `dwIDItem`  
 항목의 ID입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="onlbselchangednotify"></a>CFileDialog::OnLBSelChangedNotify  
 목록 상자에서 현재 선택 영역을 변경 하 려 할 때마다이 함수가 호출 됩니다.  
  
```  
virtual void OnLBSelChangedNotify(
    UINT nIDBox,  
    UINT iCurSel,  
    UINT nCode);
```  
  
### <a name="parameters"></a>매개 변수  
 *nIDBox*  
 목록 상자 또는 콤보 상자는 선택 된 발생의 ID입니다.  
  
 `iCurSel`  
 현재 선택 항목의 인덱스입니다.  
  
 `nCode`  
 컨트롤 알림 코드입니다. 이 매개 변수는 다음 값 중 하나가 있어야 합니다.  
  
- **CD_LBSELCHANGE** 지정 `iCurSel` 단일 선택 목록 상자에서 선택한 항목입니다.  
  
- **CD_LBSELSUB** 지정 `iCurSel` 다중 선택 목록 상자에서 선택을 취소 합니다.  
  
- **CD_LBSELADD** 지정 `iCurSel` 다중 선택 목록 상자에서를 선택 합니다.  
  
- **CD_LBSELNOITEMS** 다중 선택 목록 상자에 선택 항목이 있는 지정 합니다.  
  
### <a name="remarks"></a>설명  
 목록 상자에서 선택 항목이 변경 됨의 사용자 지정 처리를 제공 하려면이 함수를 재정의 합니다. 예를 들어 액세스 권한을 표시 하려면이 함수를 사용할 수 있습니다 또는 날짜-마지막 수정 각 파일의 사용자가을 선택 합니다.  
  
##  <a name="onshareviolation"></a>CFileDialog::OnShareViolation  
 공유 위반의 사용자 지정 처리를 제공 하려면이 함수를 재정의 합니다.  
  
```  
virtual UINT OnShareViolation(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszPathName`  
 공유 위반이 발생 한 파일의 경로입니다.  
  
### <a name="return-value"></a>반환 값  
 다음 값 중 하나입니다.  
  
- **OFN_SHAREFALLTHROUGH** 대화 상자에서 파일 이름이 반환 됩니다.  
  
- **OFN_SHARENOWARN** 추가 작업이 없으므로 수행 해야 합니다.  
  
- **OFN_SHAREWARN** 사용자에 게이 오류에 대 한 표준 경고 메시지가 있습니다.  
  
### <a name="remarks"></a>설명  
 일반적으로 프레임 워크에서는 공유 위반 검사를 수행 하는 기본 제공 하 고 공유 위반이 발생 한 경우 메시지 상자를 표시 하기 때문에이 함수를 사용할 필요가 없습니다.  
  
 공유 위반 검사가 사용 하지 않도록 설정 하려면 비트 OR 연산자를 사용 하 여 플래그를 결합할 **OFN_SHAREAWARE** 와 `m_ofn.Flags`합니다.  
  
##  <a name="ontypechange"></a>CFileDialog::OnTypeChange  
 처리 하려면이 함수를 재정의 하는 **WM_NOTIFYCDN_TYPECHANGE** 메시지입니다.  
  
```  
virtual void OnTypeChange();
```  
  
### <a name="remarks"></a>설명  
 알림 메시지는 사용자가 목록에서 새 파일 형식을 열기에서 파일 형식 또는 이름으로 저장 대화 상자를 선택할 때 보내집니다.  
  
 대화 상자 OFN_EXPLORER 스타일을 사용 하 여 만든 경우에 알림이 전송 됩니다. 알림에 대 한 자세한 내용은 참조 [CDN_TYPECHANGE](http://msdn.microsoft.com/library/windows/desktop/ms646868)합니다. OFN_EXPLORER 스타일에 대 한 정보를 참조 하십시오.는 [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) 구조 및 [열기 및 저장으로 대화 상자](http://msdn.microsoft.com/library/windows/desktop/ms646960)합니다.  
  
##  <a name="removecontrolitem"></a>CFileDialog::RemoveControlItem  
 대화 상자에서 컨테이너 컨트롤에서 항목을 제거 합니다.  
  
```  
HRESULT RemoveControlItem(
    DWORD dwIDCtl,  
    DWORD dwIDItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 항목을 제거 하는 컨테이너 컨트롤의 ID입니다.  
  
 `dwIDItem`  
 항목의 ID입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="setcheckbuttonstate"></a>CFileDialog::SetCheckButtonState  
 대화 상자에서 확인 단추 (확인란)의 현재 상태를 설정합니다.  
  
```  
HRESULT SetCheckButtonState(
    DWORD dwIDCtl,  
    BOOL bChecked);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 확인란의 ID입니다.  
  
 `bChecked`  
 확인란의 상태입니다. `TRUE`checked; 나타냅니다. `FALSE` 선택 하지 않은 상태를 나타냅니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="setcontrolitemstate"></a>CFileDialog::SetControlItemState  
 대화 상자에 있는 컨테이너 컨트롤에서 항목의 현재 상태를 설정 합니다.  
  
```  
HRESULT SetControlItemState(
    DWORD dwIDCtl,  
    DWORD dwIDItem,  
    CDCONTROLSTATEF dwState);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 컨테이너 컨트롤의 ID입니다.  
  
 `dwIDItem`  
 항목의 ID입니다.  
  
 `dwState`  
 하나 이상의 열거형의 값 CDCONTROLSTATE 컨트롤의 새 상태를 나타내는입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="setcontrolitemtext"></a>CFileDialog::SetControlItemText  
 컨트롤 항목의 텍스트를 설정합니다. 예를 들어, 라디오 단추 또는 메뉴의 항목을 함께 제공 되는 텍스트입니다.  
  
```  
HRESULT SetControlItemText(
    DWORD dwIDCtl,  
    DWORD dwIDItem,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 컨테이너 컨트롤의 ID입니다.  
  
 `dwIDItem`  
 항목의 ID입니다.  
  
 `strLabel`  
 항목의 텍스트입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="setcontrollabel"></a>CFileDialog::SetControlLabel  
 예: 단추 텍스트 또는 편집 상자 레이블 컨트롤에 연결 된 텍스트를 설정 합니다.  
  
```  
HRESULT SetControlLabel(
    DWORD dwIDCtl,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 컨트롤의 ID입니다.  
  
 `strLabel`  
 컨트롤 이름입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="setcontrolstate"></a>CFileDialog::SetControlState  
 현재 표시 여부를 설정 하 고 지정 된 컨트롤의 상태를 사용 하도록 설정 합니다.  
  
```  
HRESULT SetControlState(
    DWORD dwIDCtl,  
    CDCONTROLSTATEF dwState);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 컨트롤의 ID입니다.  
  
 `dwState`  
 하나 이상의 열거형의 값 CDCONTROLSTATE 컨트롤의 현재 상태를 나타내는입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="setcontroltext"></a>CFileDialog::SetControlText  
 탐색기 스타일에서 지정된 된 컨트롤에 대 한 텍스트를 설정 하려면이 메서드를 호출 **열려** 또는 **다른 이름으로 저장** 대화 상자.  
  
```  
void SetControlText(
    int nID,  
    LPCSTR lpsz);

 
void SetControlText(
    int nID,  
    const wchar_t *lpsz);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nID`  
 텍스트를 설정 하는 컨트롤의 ID입니다.  
  
 [in] `lpsz`  
 컨트롤에 대해 설정할 텍스트를 포함 하는 문자열에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 함수의 두 버전 모두 유니코드를 사용 하는 응용 프로그램에 적합 합니다. 그러나 LPCSTR 형식과 버전에만를 사용 하는 응용 프로그램에 대 한 유효 [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)]합니다.  
  
 이 메서드를 사용 하려면 대화 상자 OFN_EXPLORER 스타일을 만들어야 합니다. 그렇지 않으면 함수가 어설션에서 실패 합니다.  
  
##  <a name="setdefext"></a>CFileDialog::SetDefExt  
 탐색기 스타일 Open 또는 다른 이름으로 저장 일반 대화 상자에 대 한 기본 파일 이름 확장명을 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetDefExt(LPCSTR lpsz);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpsz`  
 대화 상자 개체에 사용할 기본 확장 프로그램을 포함 하는 문자열에 대 한 포인터입니다. 이 문자열에 마침표 (.)를 사용할 수 없습니다.  
  
### <a name="remarks"></a>설명  
 대화 상자를 생성 합니다는 **OFN_EXPLORER** 스타일; 그렇지 않으면, 함수는 어설션이 실패 합니다.  
  
##  <a name="seteditboxtext"></a>CFileDialog::SetEditBoxText  
 편집 상자 컨트롤에서 현재 텍스트를 설정합니다.  
  
```  
HRESULT SetEditBoxText(
    DWORD dwIDCtl,  
    const CString& strText);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 입력란의 ID입니다.  
  
 `strText`  
 텍스트 값입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="setproperties"></a>CFileDialog::SetProperties  
 저장 중인 항목에 사용할 기본값을 정의하는 속성 저장소를 제공합니다.  
  
```  
BOOL SetProperties(LPCWSTR lpszPropList);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszPropList`  
 ";"으로 구분되는 미리 정의된 속성의 목록입니다. 목록이 플래그에 대 한 참조는 `Flags` 섹션 [OPENFILENAME](http://msdn.microsoft.com/en-us/8cecfd45-f7c1-4f8d-81a0-4e7fecc3b104)합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="setselectedcontrolitem"></a>CFileDialog::SetSelectedControlItem  
 옵션 단추 그룹 또는 대화 상자에 콤보 상자에서 특정 항목의 선택된 상태를 설정 합니다.  
  
```  
HRESULT SetSelectedControlItem(
    DWORD dwIDCtl,  
    DWORD dwIDItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 컨테이너 컨트롤의 ID입니다.  
  
 `dwIDItem`  
 사용자 컨트롤에서 선택한 항목의 ID입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="settemplate"></a>CFileDialog::SetTemplate  
 설정에 대 한 대화 상자 템플릿에 [CFileDialog](../../mfc/reference/cfiledialog-class.md) 개체입니다.  
  
```  
void SetTemplate(
    UINT nWin3ID,  
    UINT nWin4ID);

 
void SetTemplate(
    LPCTSTR lpWin3ID,  
    LPCTSTR lpWin4ID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nWin3ID`  
 비-탐색기에 대 한 템플릿 리소스의 ID 번호를 포함 `CFileDialog` 개체입니다. 이 템플릿은 Windows NT 3.51 또는 OFN_EXPLORER 스타일 없을 경우에 사용 됩니다.  
  
 [in] `nWin4ID`  
 탐색기에 대 한 템플릿 리소스의 ID 번호를 포함 `CFileDialog` 개체입니다. 이 서식 파일의 경우에 사용 됩니다 [!INCLUDE[WinNt4Family](../../mfc/reference/includes/winnt4family_md.md)] 및 이상 버전, Windows 95 및 이상 버전 또는 OFN_EXPLORER 스타일이 포함 됩니다.  
  
 [in] `lpWin3ID`  
 비-탐색기에 대 한 템플릿 리소스의 이름을 포함 `CFileDialog` 개체입니다. 이 템플릿은 Windows NT 3.51 또는 OFN_EXPLORER 스타일 없을 경우에 사용 됩니다.  
  
 [in] `lpWin4ID`  
 탐색기의 템플릿 리소스의 이름을 포함 `CFileDialog` 개체입니다. 이 서식 파일의 경우에 사용 됩니다 [!INCLUDE[WinNt4Family](../../mfc/reference/includes/winnt4family_md.md)] 및 이상 버전, Windows 95 및 이상 버전 또는 OFN_EXPLORER 스타일이 포함 됩니다.  
  
### <a name="remarks"></a>설명  
 지정 된 템플릿 중 하나에 사용 됩니다. 사용할 템플릿을 OFN_EXPLORER 스타일 및 응용 프로그램에서 실행 되는 운영 체제의 유무에 따라 결정 됩니다. 비 탐색기와 템플릿 탐색기 스타일을 지정 하 여 쉽게 지원, Windows NT 3.51 수 있기 [!INCLUDE[WinNt4Family](../../mfc/reference/includes/winnt4family_md.md)] 및 이상 버전 및 Windows 95 및 이상 버전입니다.  
  
> [!NOTE]
> [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]스타일 파일 대화 상자에서이 함수를 지원 하지 않습니다. 이 함수를 사용 하는 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 스타일 파일 대화 상자를 발생 시킵니다 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)합니다. 대신은 사용자 지정된 대화 상자를 사용 하는 것입니다. 사용자 지정을 사용 하는 방법에 대 한 자세한 내용은 `CFileDialog`, 참조 [IFileDialogCustomize](http://msdn.microsoft.com/library/windows/desktop/bb775912)합니다.  
  
##  <a name="startvisualgroup"></a>CFileDialog::StartVisualGroup  
 대화 상자에서 시각적 그룹을 선언합니다. 이 그룹에 해당 요소를 추가 하는 이후에 모든 "추가" 메서드를 호출 합니다.  
  
```  
HRESULT StartVisualGroup(
    DWORD dwIDCtl,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwIDCtl`  
 시각적 그룹의 ID입니다.  
  
 `strLabel`  
 그룹 이름입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="updateofnfromshelldialog"></a>CFileDialog::UpdateOFNFromShellDialog  
 업데이트는 `m_ofn` 의 데이터 구조는 [CFileDialog](../../mfc/reference/cfiledialog-class.md) 내부 개체의 현재 상태에 기반 합니다.  
  
```  
void UpdateOFNFromShellDialog();
```  
  
### <a name="remarks"></a>설명  
 버전의 Windows 하기 전에 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], 멤버 [OPENFILENAME](https://msdn.microsoft.com/library/ms911906.aspx) 데이터 구조를 지속적으로의 상태와 동기화 할는 `CFileDialog`합니다. 변경 내용이 [m_ofn](#m_ofn) 멤버 변수 대화 상자의 상태에 직접적인 영향을 받는 합니다. 또한 대화의 상태 변경 내용이 즉시 m_ofn 멤버 변수를 업데이트 합니다.  
  
 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], `m_ofn` 데이터 구조가 자동으로 업데이트 되지 않습니다. 에 있는 데이터의 정확성을 보장 하려면는 `m_ofn` 호출 해야 멤버 변수는 `UpdateOFNFromShellDialog` 데이터에 액세스 하기 전에 함수입니다. Windows이 함수를 호출이 자동으로 처리 하는 동안 [IFileDialog::OnFileOK](http://msdn.microsoft.com/library/windows/desktop/bb775879)합니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `CFileDialog` 아래 클래스 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], 참조 [CFileDialog 클래스](../../mfc/reference/cfiledialog-class.md)합니다.  
  
### <a name="example"></a>예제  
 이 예에서는 업데이트는 `CFileDialog` 표시 하기 전에. 업데이트 하기 전에 `m_ofn` 멤버 변수 대화 상자의 현재 상태를 동기화 하려면 필요 합니다.  
  
 [!code-cpp[NVC_MFC_CFileDialog#1](../../mfc/reference/codesnippet/cpp/cfiledialog-class_7.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CCommonDialog 클래스](../../mfc/reference/ccommondialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)

