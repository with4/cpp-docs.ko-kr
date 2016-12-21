---
title: "CFileDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFileDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFileDialog class"
  - "common file dialog boxes"
  - "대화 상자, common"
ms.assetid: fda4fd3c-08b8-4ce0-8e9d-7bab23f8c6c0
caps.latest.revision: 47
caps.handback.revision: 37
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFileDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일 열기 또는 파일 저장 작업을 사용 하 여 일반 대화 상자를 캡슐화 합니다.  
  
## 구문  
  
```  
class CFileDialog : public CCommonDialog  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CFileDialog::CFileDialog](../Topic/CFileDialog::CFileDialog.md)|`CFileDialog` 개체를 생성합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CFileDialog::AddCheckButton](../Topic/CFileDialog::AddCheckButton.md)|대화 상자에 확인 단추를 추가합니다.|  
|[CFileDialog::AddComboBox](../Topic/CFileDialog::AddComboBox.md)|대화 상자에 콤보 상자를 추가합니다.|  
|[CFileDialog::AddControlItem](../Topic/CFileDialog::AddControlItem.md)|컨테이너 컨트롤이 대화 상자에서에 항목을 추가 합니다.|  
|[CFileDialog::AddEditBox](../Topic/CFileDialog::AddEditBox.md)|입력란 대화 상자를 추가합니다.|  
|[CFileDialog::AddMenu](../Topic/CFileDialog::AddMenu.md)|대화 상자에 있는 메뉴를 추가합니다.|  
|[CFileDialog::AddPlace](../Topic/CFileDialog::AddPlace.md)|오버로드.  폴더 목록을 열거나 항목을 저장 하는 사용자에 대해 사용할 수 있는 배치를 추가 합니다.|  
|[CFileDialog::AddPushButton](../Topic/CFileDialog::AddPushButton.md)|대화 상자에 단추를 추가 합니다.|  
|[CFileDialog::AddRadioButtonList](../Topic/CFileDialog::AddRadioButtonList.md)|옵션 단추 \(라디오 단추 라고도 함\) 그룹 대화에 추가합니다.|  
|[CFileDialog::AddSeparator](../Topic/CFileDialog::AddSeparator.md)|구분선 대화 상자를 추가합니다.|  
|[CFileDialog::AddText](../Topic/CFileDialog::AddText.md)|대화 상자에 텍스트 콘텐츠를 추가합니다.|  
|[CFileDialog::ApplyOFNToShellDialog](../Topic/CFileDialog::ApplyOFNToShellDialog.md)|상태 업데이트는 `CFileDialog` 매개 변수와 저장 된 플래그와 일치 하는 `m_ofn` 멤버 변수.|  
|[CFileDialog::DoModal](../Topic/CFileDialog::DoModal.md)|대화 상자를 표시 하 고 선택할 수 있습니다.|  
|[CFileDialog::EnableOpenDropDown](../Topic/CFileDialog::EnableOpenDropDown.md)|드롭다운 목록에서 활성화는  **열기** 또는  **저장** 단추 대화 상자에서.|  
|[CFileDialog::EndVisualGroup](../Topic/CFileDialog::EndVisualGroup.md)|요소가 시각적 그룹 대화 상자에서 추가 중지합니다.|  
|[CFileDialog::GetCheckButtonState](../Topic/CFileDialog::GetCheckButtonState.md)|대화 상자에서 확인 단추 \(확인란\)의 현재 상태를 가져옵니다.|  
|[CFileDialog::GetControlItemState](../Topic/CFileDialog::GetControlItemState.md)|대화 상자에 컨테이너 컨트롤에 있는 항목의 현재 상태를 가져옵니다.|  
|[CFileDialog::GetControlState](../Topic/CFileDialog::GetControlState.md)|현재 가시성을 가져와서 지정 된 컨트롤 상태를 사용할 수 있습니다.|  
|[CFileDialog::GetEditBoxText](../Topic/CFileDialog::GetEditBoxText.md)|편집 상자 컨트롤에서 현재 텍스트를 가져옵니다.|  
|[CFileDialog::GetFileExt](../Topic/CFileDialog::GetFileExt.md)|선택한 파일의 확장명을 반환합니다.|  
|[CFileDialog::GetFileName](../Topic/CFileDialog::GetFileName.md)|선택한 파일의 파일 이름을 반환합니다.|  
|[CFileDialog::GetFileTitle](../Topic/CFileDialog::GetFileTitle.md)|선택한 파일의 제목을 반환합니다.|  
|[CFileDialog::GetFolderPath](../Topic/CFileDialog::GetFolderPath.md)|탐색기 스타일에 대 한 현재 열려 있는 폴더 또는 디렉터리의 경로 검색 합니다.  **열기** 또는  **으로 저장** 공용 대화 상자.|  
|[CFileDialog::GetIFileDialogCustomize](../Topic/CFileDialog::GetIFileDialogCustomize.md)|내부 COM 개체에 대 한 사용자 지정 검색 `CFileDialog` 개체입니다.|  
|[CFileDialog::GetIFileOpenDialog](../Topic/CFileDialog::GetIFileOpenDialog.md)|내부 COM 개체에 대 한 검색은 `CFileDialog` 로 사용 하는  **열기** 파일 대화 상자.|  
|[CFileDialog::GetIFileSaveDialog](../Topic/CFileDialog::GetIFileSaveDialog.md)|내부 COM 개체에 대 한 검색은 `CFileDialog` 로 사용 되는  **저장** 파일 대화 상자.|  
|[CFileDialog::GetNextPathName](../Topic/CFileDialog::GetNextPathName.md)|다음 선택한 파일의 전체 경로 반환합니다.|  
|[CFileDialog::GetOFN](../Topic/CFileDialog::GetOFN.md)|검색은 `OPENFILENAME` 의 구조는 `CFileDialog` 개체입니다.|  
|[CFileDialog::GetPathName](../Topic/CFileDialog::GetPathName.md)|선택한 파일의 전체 경로 반환합니다.|  
|[CFileDialog::GetReadOnlyPref](../Topic/CFileDialog::GetReadOnlyPref.md)|선택한 파일을 읽기 전용 상태로 반환합니다.|  
|[CFileDialog::GetResult](../Topic/CFileDialog::GetResult.md)|사용자는 대화 상자에서 변경한 선택 항목을 가져옵니다.|  
|[CFileDialog::GetResults](../Topic/CFileDialog::GetResults.md)|사용자의 선택 사항을 여러 항목 선택 허용 대화 상자를 가져옵니다.|  
|[CFileDialog::GetSelectedControlItem](../Topic/CFileDialog::GetSelectedControlItem.md)|지정 된 컨테이너 컨트롤 대화 상자에서 특정 항목을 가져옵니다.|  
|[CFileDialog::GetStartPosition](../Topic/CFileDialog::GetStartPosition.md)|파일 이름 목록에 있는 첫 번째 요소의 위치를 반환 합니다.|  
|[CFileDialog::HideControl](../Topic/CFileDialog::HideControl.md)|탐색기 스타일에서 지정 된 컨트롤을 숨기  **열기** 또는  **으로 저장** 공용 대화 상자.|  
|[CFileDialog::IsPickFoldersMode](../Topic/CFileDialog::IsPickFoldersMode.md)|결정은 현재 대화 상자에서 폴더 선택 모드입니다.|  
|[CFileDialog::MakeProminent](../Topic/CFileDialog::MakeProminent.md)|그를 둘러 위치 대화 상자에서 컨트롤을 다른 추가 컨트롤을 비교.|  
|[CFileDialog::RemoveControlItem](../Topic/CFileDialog::RemoveControlItem.md)|컨테이너 컨트롤의 대화 상자에서에서 항목을 제거 합니다.|  
|[CFileDialog::SetCheckButtonState](../Topic/CFileDialog::SetCheckButtonState.md)|확인 단추 \(확인란\)의 현재 상태 대화 상자에서 설정합니다.|  
|[CFileDialog::SetControlItemState](../Topic/CFileDialog::SetControlItemState.md)|컨테이너 컨트롤이 대화 상자에 있는 항목의 현재 상태를 설정 합니다.|  
|[CFileDialog::SetControlItemText](../Topic/CFileDialog::SetControlItemText.md)|컨트롤 항목의 텍스트를 설정합니다.  예를 들어 라디오 단추 또는 메뉴에서 항목을 포함 하는 텍스트입니다.|  
|[CFileDialog::SetControlLabel](../Topic/CFileDialog::SetControlLabel.md)|단추 텍스트는 편집 상자 레이블 등의 컨트롤과 관련 된 텍스트를 설정 합니다.|  
|[CFileDialog::SetControlState](../Topic/CFileDialog::SetControlState.md)|현재 표시 여부를 설정 하 고 지정 된 컨트롤 상태를 사용할 수 있습니다.|  
|[CFileDialog::SetControlText](../Topic/CFileDialog::SetControlText.md)|탐색기 스타일에 지정 된 컨트롤의 텍스트를 설정 하는  **열기**  또는  **으로 저장** 공용 대화 상자.|  
|[CFileDialog::SetDefExt](../Topic/CFileDialog::SetDefExt.md)|탐색기 스타일을 설정 하는 기본 파일 이름 확장명  **열기** 또는  **으로 저장** 공용 대화 상자.|  
|[CFileDialog::SetEditBoxText](../Topic/CFileDialog::SetEditBoxText.md)|현재 텍스트 편집 상자 컨트롤에 설정합니다.|  
|[CFileDialog::SetProperties](../Topic/CFileDialog::SetProperties.md)|항목을 저장 하는 데 기본 값을 정의 하는 속성 저장소를 제공 합니다.|  
|[CFileDialog::SetSelectedControlItem](../Topic/CFileDialog::SetSelectedControlItem.md)|옵션 단추 그룹 또는 대화 상자에 콤보 상자에서 특정 항목의 선택된 된 상태를 설정 합니다.|  
|[CFileDialog::SetTemplate](../Topic/CFileDialog::SetTemplate.md)|대화 상자 템플릿을 설정 하는 `CFileDialog` 개체입니다.|  
|[CFileDialog::StartVisualGroup](../Topic/CFileDialog::StartVisualGroup.md)|비주얼 그룹 대화에서를 선언합니다.  후속 메서드를 호출 하는 "add" 요소만이 그룹에 추가 합니다.|  
|[CFileDialog::UpdateOFNFromShellDialog](../Topic/CFileDialog::UpdateOFNFromShellDialog.md)|저장 된 데이터를 업데이트 하는 `m_ofn` 파일 대화 상자의 현재 상태와 일치 하는 멤버 변수.|  
  
### Protected 메서드  
  
|이름|설명|  
|--------|--------|  
|[CFileDialog::OnButtonClicked](../Topic/CFileDialog::OnButtonClicked.md)|단추를 클릭할 때 호출 됩니다.|  
|[CFileDialog::OnCheckButtonToggled](../Topic/CFileDialog::OnCheckButtonToggled.md)|확인란 선택\/선택 취소 될 때 호출 됩니다.|  
|[CFileDialog::OnControlActivating](../Topic/CFileDialog::OnControlActivating.md)|컨트롤이 활성화 될 때 호출 됩니다.|  
|[CFileDialog::OnFileNameChange](../Topic/CFileDialog::OnFileNameChange.md)|처리 된 `WM_NOTIFY CDN_SELCHANGE` 메시지입니다.|  
|[CFileDialog::OnFileNameOK](../Topic/CFileDialog::OnFileNameOK.md)|대화 상자에 입력 한 파일 이름을 확인 합니다.|  
|[CFileDialog::OnFolderChange](../Topic/CFileDialog::OnFolderChange.md)|처리 된 `WM_NOTIFY CDN_FOLDERCHANGE` 메시지입니다.|  
|[CFileDialog::OnInitDone](../Topic/CFileDialog::OnInitDone.md)|처리 된 `WM_NOTIFY CDN_INITDONE` 메시지입니다.|  
|[CFileDialog::OnItemSelected](../Topic/CFileDialog::OnItemSelected.md)|컨테이너 항목을 선택할 때 호출 됩니다.|  
|[CFileDialog::OnLBSelChangedNotify](../Topic/CFileDialog::OnLBSelChangedNotify.md)|파일 선택 영역을 변경할 때 사용자 지정 작업을 수행할 수 있습니다.|  
|[CFileDialog::OnShareViolation](../Topic/CFileDialog::OnShareViolation.md)|핸들 위반을 공유합니다.|  
|[CFileDialog::OnTypeChange](../Topic/CFileDialog::OnTypeChange.md)|처리 된 `WM_NOTIFY CDN_TYPECHANGE` 메시지입니다.|  
  
### 공용 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CFileDialog::m\_ofn](../Topic/CFileDialog::m_ofn.md)|Windows `OPENFILENAME` 구조체입니다.  액세스 기본 파일 대화 상자 매개 변수를 제공합니다.|  
  
## 설명  
 공용 파일 대화 상자를 사용 하 여 파일 선택 대화 상자에서 예를 들어, 구현할 수  **파일 열기** 및  **으로 저장**을 Windows 표준을 일관 된 방식으로.  
  
 사용할 수 있습니다  [CFileDialog](../../mfc/reference/cfiledialog-class.md) 로 제공 되는 생성자를 또는 사용자 지정 대화 상자 클래스를 파생 시킬 수 있습니다 `CFileDialog` 및 필요에 맞게 생성자를 작성 합니다.  두 경우 모두에서 파생 된 때문에 이러한 대화 상자 표준 MFC 대화 상자와 마찬가지로 동작 합니다의 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md).  `CFileDialog`COMMDLG에 의존합니다.Windows에 포함 된 DLL 파일입니다.  
  
 모양과 기능을 둘 다은 `CFileDialog` 와 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 이전 버전의 Windows에서 다릅니다.  기본 `CFileDialog` 자동으로 새를 사용 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 프로그램이 컴파일될 경우 코드를 변경 하 고 아래에서 실행 하지 않고 스타일 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  사용 된 `bVistaStyle` 이 자동 업데이트를 수동으로 재정의 하려면 생성자에서 매개 변수입니다.  자동 업데이트에 사용자 지정 된 대화 상자입니다.  자신이 새 스타일으로 변환 되지 않습니다.  생성자에 대 한 자세한 내용은 [CFileDialog::CFileDialog](../Topic/CFileDialog::CFileDialog.md).  
  
> [!NOTE]
>  다른 제어 ID 시스템 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 에서 이전 버전의 Windows 사용 하는 경우는 `CFileDialog`.  모든 참조를 업데이트 해야 `CFileDialog` Windows의 이전 버전에서 프로젝트를 이식할 수 있습니다 전에 코드에서 컨트롤입니다.  
  
 일부 `CFileDialog` 에서 메서드 지원 되지 않습니다 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  메서드가 지원 되는지 여부에 대 한 내용은 개별 메서드 항목을 확인 하십시오.  또한 상속 된 다음 함수에서 사용할 수 없는 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  
  
-   [CDialog::OnInitDialog](../Topic/CDialog::OnInitDialog.md)  
  
-   [CDialog::OnSetFont](../Topic/CDialog::OnSetFont.md)  
  
 Windows 메시지에는 `CFileDialog` 클래스를 사용 중인 운영 체제에 따라 달라 집니다.  예를 들어, Windows XP를 지원 하지 않는 [CDialog::OnCancel](../Topic/CDialog::OnCancel.md) 및 [CDialog::OnOK](../Topic/CDialog::OnOK.md) 에 있는 `CFileDialog` 클래스.  그러나 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 를 지원 하지.  메시지가 생성 되 고 수신 되는 순서에 대 한 자세한 내용은  [CFileDialog 샘플: 로깅 이벤트 순서](../../top/visual-cpp-samples.md).  
  
 사용 하는 `CFileDialog` 개체를 사용 하 여 개체를 처음 만들을 `CFileDialog` 생성자입니다.  대화 상자 생성 된 후 설정 하거나 모든 값을 수정할 수는 [CFileDialog::m\_ofn](../Topic/CFileDialog::m_ofn.md) 구조체 값 또는 대화 상자 컨트롤의 상태를 초기화 합니다.  `m_ofn` 구조체 형식인 `OPENFILENAME`.  자세한 내용은  [파일 이름](http://msdn.microsoft.com/library/windows/desktop/ms646839) 에서 구조체의 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 대화 상자의 컨트롤을 초기화 한 후에 호출 된 [CFileDialog::DoModal](../Topic/CFileDialog::DoModal.md) 메서드는 대화 상자를 표시 하려면 상자의 경로 및 파일 이름을 사용자가 입력할 수 있도록 합니다.  `DoModal`사용자가 확인 \(IDOK\) 또는 취소 \(IDCANCEL\) 단추를 클릭 여부를 반환 합니다.  경우 `DoModal` IDOK, 반환 중 하나를 사용할 수 있는 `CFileDialog` 사용자가 추가 정보를 검색할 수 있는 공용 멤버 함수.  
  
> [!NOTE]
>  아래 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]를 여러 번 호출  [IFileDialog::SetFileTypes](http://msdn.microsoft.com/library/windows/desktop/bb775980) 오류가 발생 합니다.  두 번째 호출 `SetFileTypes` 의 인스턴스에 대 한 `CFileDialog` 반환 합니다 `E_UNEXPECTED` 에서 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  일부 `CFileDialog` 메서드 호출 함수 `SetFileTypes`.  예를 들어, 두 호출이 `CFileDialog::DoModal` 의 동일한 인스턴스를 `CFileDialog` 생성  [ASSERT](../Topic/ASSERT%20\(MFC\).md).  
  
 `CFileDialog`공유 위반, 파일 이름 유효성 검사 및 목록 상자 변경 알림 사용자 지정 처리를 수행할 수 있는 몇 가지 보호 된 멤버를 포함 합니다.  이러한 보호 된 멤버는 대부분의 응용 프로그램 기본 처리를 자동으로 수행 되므로 사용 하지 않아도 되는 콜백 함수입니다.  표준 가상 함수 때문에 이러한 함수에 대 한 메시지 맵 엔트리는 필요 하지 않습니다.  
  
 Windows를 사용할 수 있습니다  [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) 함수 대화 상자를 초기화 하는 동안 오류가 발생 여부를 확인 하 고 오류에 대 한 자세한 합니다.  
  
 파괴의 `CFileDialog` 개체는 자동으로 처리 합니다.  호출 하지 않아도 [CDialog::EndDialog](../Topic/CDialog::EndDialog.md).  
  
 여러 파일을 선택할 수 있게 하려면 설정 된 `OFN_ALLOWMULTISELECT` 플래그를 호출 하기 전에 `DoModal`.  파일 이름 여러 개 반환 된 목록을 수용 하기 위해 자신의 파일 이름 버퍼를 제공 해야 합니다.  이렇게 바꾸어 `m_ofn.lpstrFile` 생성 후 버퍼 포인터와 사용자를 할당는 `CFileDialog`를 호출 하기 전에 `DoModal`.  
  
 또한, 설정 해야 `m_ofn.nMaxFile` 포인터가 가리키는 버퍼의 문자 수를 사용 하 여 `m_ofn.lpstrFile`.  선택 하는 파일의 최대 수를 설정 하는 경우 `n`, 필요한 버퍼 크기는 `n * (_MAX_PATH + 1) + 1`.  선택한 위치에 파일이 있는 폴더의 경로를 버퍼에서 반환 된 첫 번째 항목을입니다.  에 대 한 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]\-디렉터리 및 파일 이름 문자열 스타일 대화 상자는 null로 끝나는, 마지막 파일 이름 뒤에 추가 null 문자를 사용 합니다.  이 형식을 공백이 있는 긴 파일 이름을 반환 하는 탐색기 스타일 대화 상자를 있습니다.  이전 스타일 대화 상자에 대 한 디렉터리 및 파일 이름 문자열 공백으로 구분 된 및 짧은 파일 이름을 파일 이름에 공백을 사용 하 여이 함수를 사용 합니다.  
  
 다음 예제에서는 버퍼를 사용 하 여 검색 하 고 여러 개의 파일 이름을 나열 하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFCFiles#23](../../mfc/codesnippet/CPP/cfiledialog-class_1.cpp)]  
  
 파일 이름을 여러 개 선택 하면 사용자에 게 응답의 버퍼 크기를 변경 하려면 새 클래스를 파생 해야 합니다 `CFileDialog` 및 재정의 된 [CFileDialog::OnFileNameChange](../Topic/CFileDialog::OnFileNameChange.md) 메서드.  
  
 새 클래스를 파생 하는 경우 `CFileDialog`, 메시지 맵을 사용 하 여 모든 메시지를 처리할 수 있습니다.  기본 메시지 처리를 확장 하는 클래스를 `CFileDialog`가 새 클래스에 메시지 맵을 추가 하 고 새 메시지에 대 한 멤버 함수를 제공 합니다.  사용자 지정 대화 상자 후크 함수를 제공 하지 않아도 됩니다.  
  
 대화 상자를 사용자 정의 하려면에서 클래스를 파생 합니다. `CFileDialog`, 사용자 지정 대화 상자 템플릿을 제공 하 고 확장된 된 컨트롤에서 알림 메시지를 처리 하는 메시지 맵에 추가 합니다.  기본 클래스에는 처리 되지 않은 메시지를 전달 합니다.  후크 함수를 사용자 지정 하지 않아도 됩니다.  
  
 사용 중인의 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 의 스타일은 `CFileDialog`, 메시지 맵 및 대화 상자 템플릿을 사용할 수 없습니다.  대신 유사한 기능에 대 한 COM 인터페이스를 사용 해야 합니다.  
  
 `CFileDialog`를 사용하는 방법에 대한 자세한 내용은 [일반 대화 상자 클래스](../../mfc/common-dialog-classes.md)를 참조하십시오.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFileDialog`  
  
## 요구 사항  
 **헤더:** afxdlgs.h  
  
## 참고 항목  
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)