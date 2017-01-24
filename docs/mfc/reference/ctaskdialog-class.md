---
title: "CTaskDialog Class | Microsoft Docs"
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
  - "CTaskDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTaskDialog class"
ms.assetid: 1991ec98-ae56-4483-958b-233809c8c559
caps.latest.revision: 29
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTaskDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

작동 하는 팝업 대화 상자는 메시지 상자를 사용자에 게 추가 정보를 표시할 수 있습니다.  `CTaskDialog` 또한 사용자 로부터 정보를 수집 하는 기능이 포함 되어 있습니다.  
  
## 구문  
  
```  
class CTaskDialog : public CObject  
```  
  
## 멤버  
  
### 생성자  
  
|||  
|-|-|  
|[CTaskDialog::CTaskDialog](../Topic/CTaskDialog::CTaskDialog.md)|`CTaskDialog` 개체를 생성합니다.|  
  
### 메서드  
  
|||  
|-|-|  
|[CTaskDialog::AddCommandControl](../Topic/CTaskDialog::AddCommandControl.md)|명령 단추 컨트롤에 추가 된 `CTaskDialog`.|  
|[CTaskDialog::AddRadioButton](../Topic/CTaskDialog::AddRadioButton.md)|라디오 단추에 추가 된 `CTaskDialog`.|  
|[CTaskDialog::ClickCommandControl](../Topic/CTaskDialog::ClickCommandControl.md)|프로그래밍 방식으로 명령 단추 컨트롤 또는 일반 단추를 클릭합니다.|  
|[CTaskDialog::ClickRadioButton](../Topic/CTaskDialog::ClickRadioButton.md)|프로그래밍 방식으로 라디오 단추를 클릭 합니다.|  
|[CTaskDialog::DoModal](../Topic/CTaskDialog::DoModal.md)|`CTaskDialog`를 표시합니다.|  
|[CTaskDialog::GetCommonButtonCount](../Topic/CTaskDialog::GetCommonButtonCount.md)|사용할 수 있는 일반적인 단추 개수를 검색합니다.|  
|[CTaskDialog::GetCommonButtonFlag](../Topic/CTaskDialog::GetCommonButtonFlag.md)|Windows 단추 일반 단추 형식에 관련 된 표준 변환의 `CTaskDialog` 클래스입니다.|  
|[CTaskDialog::GetCommonButtonId](../Topic/CTaskDialog::GetCommonButtonId.md)|변환 관련 일반 단추 종류 중 하나는 `CTaskDialog` 클래스에는 표준 Windows 단추.|  
|[CTaskDialog::GetOptions](../Topic/CTaskDialog::GetOptions.md)|옵션 플래그에 대 한이 반환 `CTaskDialog`.|  
|[CTaskDialog::GetSelectedCommandControlID](../Topic/CTaskDialog::GetSelectedCommandControlID.md)|선택한 명령 단추 컨트롤을 반환합니다.|  
|[CTaskDialog::GetSelectedRadioButtonID](../Topic/CTaskDialog::GetSelectedRadioButtonID.md)|선택된 된 라디오 단추를 반환합니다.|  
|[CTaskDialog::GetVerificationCheckboxState](../Topic/CTaskDialog::GetVerificationCheckboxState.md)|검증 확인란의 상태를 검색합니다.|  
|[CTaskDialog::IsCommandControlEnabled](../Topic/CTaskDialog::IsCommandControlEnabled.md)|명령 단추 컨트롤 또는 일반적인 단추 사용 가능 여부를 결정 합니다.|  
|[CTaskDialog::IsRadioButtonEnabled](../Topic/CTaskDialog::IsRadioButtonEnabled.md)|라디오 단추를 사용할 수 있는지 여부를 결정 합니다.|  
|[CTaskDialog::IsSupported](../Topic/CTaskDialog::IsSupported.md)|응용 프로그램을 실행 하는 컴퓨터를 지원 하는지 여부를 결정 하는 `CTaskDialog`.|  
|[CTaskDialog::LoadCommandControls](../Topic/CTaskDialog::LoadCommandControls.md)|문자열 테이블에서 데이터를 사용 하 여 명령 단추 컨트롤을 추가 합니다.|  
|[CTaskDialog::LoadRadioButtons](../Topic/CTaskDialog::LoadRadioButtons.md)|문자열 테이블에서 데이터를 사용 하 여 라디오 단추를 추가 합니다.|  
|[CTaskDialog::NavigateTo](../Topic/CTaskDialog::NavigateTo.md)|포커스를 다른 위치로 전송 `CTaskDialog`.|  
|[CTaskDialog::OnCommandControlClick](../Topic/CTaskDialog::OnCommandControlClick.md)|명령 단추 컨트롤을 클릭할 때 프레임 워크가이 메서드를 호출 합니다.|  
|[CTaskDialog::OnCreate](../Topic/CTaskDialog::OnCreate.md)|프레임 워크를 만든 후이 메서드를 호출 하 여 `CTaskDialog`.|  
|[CTaskDialog::OnDestroy](../Topic/CTaskDialog::OnDestroy.md)|프레임 워크를 삭제 하기 전에 바로이 메서드를 호출 하 여 `CTaskDialog`.|  
|[CTaskDialog::OnExpandButtonClick](../Topic/CTaskDialog::OnExpandButtonClick.md)|프레임 워크의 확장 단추를 클릭할 때이 메서드를 호출 합니다.|  
|[CTaskDialog::OnHelp](../Topic/CTaskDialog::OnHelp.md)|프레임 워크는 사용자가 도움말을 요청 하는 경우이 메서드를 호출 합니다.|  
|[CTaskDialog::OnHyperlinkClick](../Topic/CTaskDialog::OnHyperlinkClick.md)|사용자가 하이퍼링크를 클릭 하면 프레임 워크가이 메서드를 호출 합니다.|  
|[CTaskDialog::OnInit](../Topic/CTaskDialog::OnInit.md)|이 메서드를 호출 하는 프레임 워크 때의 `CTaskDialog` 초기화 됩니다.|  
|[CTaskDialog::OnNavigatePage](../Topic/CTaskDialog::OnNavigatePage.md)|프레임 워크 사용자 관련 컨트롤에 포커스가 이동 하면이 메서드를 호출 하 여 `CTaskDialog`.|  
|[CTaskDialog::OnRadioButtonClick](../Topic/CTaskDialog::OnRadioButtonClick.md)|사용자가 라디오 단추 컨트롤을 선택 하면 프레임 워크가이 메서드를 호출 합니다.|  
|[CTaskDialog::OnTimer](../Topic/CTaskDialog::OnTimer.md)|프레임 워크는 타이머가 만료 될 때이 메서드를 호출 합니다.|  
|[CTaskDialog::OnVerificationCheckboxClick](../Topic/CTaskDialog::OnVerificationCheckboxClick.md)|사용자 확인 확인란을 클릭 하면 프레임 워크가이 메서드를 호출 합니다.|  
|[CTaskDialog::RemoveAllCommandControls](../Topic/CTaskDialog::RemoveAllCommandControls.md)|모든 명령 컨트롤에서 제거 된 `CTaskDialog`.|  
|[CTaskDialog::RemoveAllRadioButtons](../Topic/CTaskDialog::RemoveAllRadioButtons.md)|제거에서 모든 라디오 단추는 `CTaskDialog`.|  
|[CTaskDialog::SetCommandControlOptions](../Topic/CTaskDialog::SetCommandControlOptions.md)|명령 단추 컨트롤에 업데이트 된 `CTaskDialog`.|  
|[CTaskDialog::SetCommonButtonOptions](../Topic/CTaskDialog::SetCommonButtonOptions.md)|하위 집합을 사용 하 고 UAC 권한 상승을 요구 하는 일반적인 단추를 업데이트 합니다.|  
|[CTaskDialog::SetCommonButtons](../Topic/CTaskDialog::SetCommonButtons.md)|일반적인 단추에 추가 된 `CTaskDialog`.|  
|[CTaskDialog::SetContent](../Topic/CTaskDialog::SetContent.md)|내용의 업데이트는 `CTaskDialog`.|  
|[CTaskDialog::SetDefaultCommandControl](../Topic/CTaskDialog::SetDefaultCommandControl.md)|기본 명령 단추 컨트롤을 지정합니다.|  
|[CTaskDialog::SetDefaultRadioButton](../Topic/CTaskDialog::SetDefaultRadioButton.md)|기본 라디오 단추를 지정합니다.|  
|[CTaskDialog::SetDialogWidth](../Topic/CTaskDialog::SetDialogWidth.md)|너비를 조정 하는 `CTaskDialog`.|  
|[CTaskDialog::SetExpansionArea](../Topic/CTaskDialog::SetExpansionArea.md)|확장 영역을 업데이트는 `CTaskDialog`.|  
|[CTaskDialog::SetFooterIcon](../Topic/CTaskDialog::SetFooterIcon.md)|바닥글 아이콘에 대 한 업데이트는 `CTaskDialog`.|  
|[CTaskDialog::SetFooterText](../Topic/CTaskDialog::SetFooterText.md)|바닥글의 업데이트는 `CTaskDialog`.|  
|[CTaskDialog::SetMainIcon](../Topic/CTaskDialog::SetMainIcon.md)|기본 아이콘의 업데이트는 `CTaskDialog`.|  
|[CTaskDialog::SetMainInstruction](../Topic/CTaskDialog::SetMainInstruction.md)|기본 지침의 업데이트는 `CTaskDialog`.|  
|[CTaskDialog::SetOptions](../Topic/CTaskDialog::SetOptions.md)|구성 옵션에는 `CTaskDialog`.|  
|[CTaskDialog::SetProgressBarMarquee](../Topic/CTaskDialog::SetProgressBarMarquee.md)|움직이는 텍스트 표시줄에 구성의 `CTaskDialog` 하 고 대화 상자에 추가 합니다.|  
|[CTaskDialog::SetProgressBarPosition](../Topic/CTaskDialog::SetProgressBarPosition.md)|진행률 표시줄의 위치를 조정 합니다.|  
|[CTaskDialog::SetProgressBarRange](../Topic/CTaskDialog::SetProgressBarRange.md)|진행률 표시줄의 범위를 조정합니다.|  
|[CTaskDialog::SetProgressBarState](../Topic/CTaskDialog::SetProgressBarState.md)|진행률 표시줄의 상태를 설정 하 고 표시에 `CTaskDialog`.|  
|[CTaskDialog::SetRadioButtonOptions](../Topic/CTaskDialog::SetRadioButtonOptions.md)|라디오 단추를 사용할 수 있거나.|  
|[CTaskDialog::SetVerificationCheckbox](../Topic/CTaskDialog::SetVerificationCheckbox.md)|확인 확인란의 선택된 상태를 설정합니다.|  
|[CTaskDialog::SetVerificationCheckboxText](../Topic/CTaskDialog::SetVerificationCheckboxText.md)|검증 확인란의 오른쪽에 텍스트를 설정합니다.|  
|[CTaskDialog::SetWindowTitle](../Topic/CTaskDialog::SetWindowTitle.md)|제목을 설정 하는 `CTaskDialog`.|  
|[CTaskDialog::ShowDialog](../Topic/CTaskDialog::ShowDialog.md)|만들고 표시 하는 `CTaskDialog`.|  
|[CTaskDialog::TaskDialogCallback](../Topic/CTaskDialog::TaskDialogCallback.md)|프레임 워크는 다양 한 Windows 메시지에 호출합니다.|  
  
### 데이터 멤버  
  
|||  
|-|-|  
|`m_aButtons`|명령 단추 컨트롤에 대 한 배열에 `CTaskDialog`.|  
|`m_aRadioButtons`|배열에 대 한 라디오 단추 컨트롤의 `CTaskDialog`.|  
|`m_bVerified`|`TRUE`나타내는 확인 확인란을 선택 합니다.  `FALSE`이 아님을 나타냅니다.|  
|`m_footerIcon`|아이콘의 바닥글에서의 `CTaskDialog`.|  
|`m_hWnd`|에 대 한 창 핸들은 `CTaskDialog`.|  
|`m_mainIcon`|기본 아이콘은 `CTaskDialog`.|  
|`m_nButtonDisabled`|일반적인 단추를 나타내는 마스크를 사용할 수 없습니다.|  
|`m_nButtonElevation`|일반적인 단추를 나타내는 마스크 UAC 권한 상승이 필요 합니다.|  
|`m_nButtonId`|선택한 명령의 단추 컨트롤의 ID입니다.|  
|`m_nCommonButton`|에 일반적인 단추를 나타내는 마스크 표시는 `CTaskDialog`.|  
|`m_nDefaultCommandControl`|명령 단추의 ID를 제어 하는 선택 된 경우에 `CTaskDialog` 표시 됩니다.|  
|`m_nDefaultRadioButton`|라디오 버튼의 ID를 제어 하는 선택 된 경우에 `CTaskDialog` 표시 됩니다.|  
|`m_nFlags`|옵션을 나타내는 마스크는 `CTaskDialog`.|  
|`m_nProgressPos`|진행률 표시줄의 현재 위치입니다.  이 값은 `m_nProgressRangeMin`와 `m_nProgressRangeMax` 사이의 값이어야 합니다.|  
|`m_nProgressRangeMax`|진행률 표시줄의 최대 값입니다.|  
|`m_nProgressRangeMin`|진행률 표시줄의 최소값입니다.|  
|`m_nProgressState`|진행률 표시줄의 상태입니다.  자세한 내용은 [CTaskDialog::SetProgressBarState](../Topic/CTaskDialog::SetProgressBarState.md)를 참조하십시오.|  
|`m_nRadioId`|선택된 된 라디오 단추 컨트롤의 ID입니다.|  
|`m_nWidth`|`CTaskDialog`의 너비\(픽셀\)입니다.|  
|`m_strCollapse`|문자열은 `CTaskDialog` 확장 된 정보를 숨기면 확장 상자 오른쪽에 표시 됩니다.|  
|`m_strContent`|콘텐츠 문자열에는 `CTaskDialog`.|  
|`m_strExpand`|문자열은 `CTaskDialog` 확장 된 정보가 표시 될 때 확장 상자 오른쪽에 표시 됩니다.|  
|`m_strFooter`|바닥글의 `CTaskDialog`.|  
|`m_strInformation`|에 대 한 상세 정보는 `CTaskDialog`.|  
|`m_strMainInstruction`|기본 명령에는 `CTaskDialog`.|  
|`m_strTitle`|`CTaskDialog`의 제목입니다.|  
|`m_strVerification`|문자열에는 `CTaskDialog` 확인 확인란 오른쪽에 표시 됩니다.|  
  
## 설명  
 `CTaskDialog` 클래스 표준 Windows 메시지 상자를 대체 하며 사용자 로부터 정보를 수집 하는 새 컨트롤과 같은 추가 기능이 있습니다.  MFC 라이브러리에서이 클래스는 [!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)].  `CTaskDialog` 부터 사용할 수 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  표시할 수 없습니다. 이전 버전의 Windows는 `CTaskDialog` 개체입니다.  사용 `CTaskDialog::IsSupported` 런타임 시 사용자가 현재 작업 대화 상자를 표시할 수 있는지 여부를 확인 합니다.  표준 Windows 메시지 상자에서 계속 지원 [!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)].  
  
 `CTaskDialog` 만 하면 응용 프로그램이 유니코드 라이브러리를 사용 하 여 빌드할 때 사용할 수 있습니다.  
  
 `CTaskDialog` 서로 다른 두 가지 생성자가 있습니다.  한 생성자는 최대 6 개의 일반 단추 컨트롤 및 두 개의 명령 단추를 지정할 수 있습니다.  만든 후 추가 명령 단추를 추가할 수 있습니다를 `CTaskDialog`.  명령 단추, 두 번째 생성자를 지원 하지 않습니다 있지만 무제한 일반 단추 컨트롤을 추가할 수 있습니다.  생성자에 대 한 자세한 내용은 [CTaskDialog::CTaskDialog](../Topic/CTaskDialog::CTaskDialog.md).  
  
 다음 이미지는 샘플입니다 `CTaskDialog` 일부 컨트롤의 위치를 보여 줍니다.  
  
 ![CTaskDialog의 예](../../mfc/reference/media/ctaskdialogsample.png "CTaskDialogSample")  
CTaskDialog 샘플  
  
## 요구 사항  
 **최소 운영 체제:** [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
 **헤더:** afxtaskdialog.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [연습: 응용 프로그램에 CTaskDialog 추가](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)