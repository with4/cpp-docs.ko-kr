---
title: "CToolBar Class | Microsoft Docs"
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
  - "CToolBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "비트맵[C++], button controls"
  - "단추[C++], MFC toolbars"
  - "control bars [C++], CToolBar class"
  - "CToolBar class"
  - "도구 모음[C++], CToolBar class"
  - "Windows common controls [C++], CToolBar class"
  - "Windows toolbar common controls [C++]"
ms.assetid: e868da26-5e07-4607-9651-e2f863ad9059
caps.latest.revision: 26
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CToolBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비트맵 단추와 옵션 구분 행이 있는 컨트롤 막대입니다.  
  
## 구문  
  
```  
class CToolBar : public CControlBar  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CToolBar::CToolBar](../Topic/CToolBar::CToolBar.md)|`CToolBar` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CToolBar::CommandToIndex](../Topic/CToolBar::CommandToIndex.md)|단추에 지정 된 명령 ID의 인덱스를 반환합니다.|  
|[CToolBar::Create](../Topic/CToolBar::Create.md)|Windows 도구 모음을 만들고이에 연결 된 `CToolBar` 개체입니다.|  
|[CToolBar::CreateEx](../Topic/CToolBar::CreateEx.md)|생성 한 `CToolBar` 개체에 포함 된 추가 스타일 `CToolBarCtrl` 개체.|  
|[CToolBar::GetButtonInfo](../Topic/CToolBar::GetButtonInfo.md)|ID, 스타일 및 단추 이미지 개수를 검색합니다.|  
|[CToolBar::GetButtonStyle](../Topic/CToolBar::GetButtonStyle.md)|단추의 스타일을 검색합니다.|  
|[CToolBar::GetButtonText](../Topic/CToolBar::GetButtonText.md)|단추에 나타나는 텍스트를 검색 합니다.|  
|[CToolBar::GetItemID](../Topic/CToolBar::GetItemID.md)|명령 단추 또는 구분 기호를 지정 된 인덱스의 ID를 반환합니다.|  
|[CToolBar::GetItemRect](../Topic/CToolBar::GetItemRect.md)|지정 된 인덱스에 있는 항목에 대 한 표시 영역을 검색합니다.|  
|[CToolBar::GetToolBarCtrl](../Topic/CToolBar::GetToolBarCtrl.md)|내부 공용 컨트롤에 직접 액세스할 수 있습니다.|  
|[CToolBar::LoadBitmap](../Topic/CToolBar::LoadBitmap.md)|비트맵 단추 이미지가 포함 된 비트맵을 로드 합니다.|  
|[CToolBar::LoadToolBar](../Topic/CToolBar::LoadToolBar.md)|리소스 편집기로 만든 도구 모음 리소스를 로드 합니다.|  
|[CToolBar::SetBitmap](../Topic/CToolBar::SetBitmap.md)|비트맵 이미지를 설정합니다.|  
|[CToolBar::SetButtonInfo](../Topic/CToolBar::SetButtonInfo.md)|ID, 스타일 및 단추 이미지 개수를 설정합니다.|  
|[CToolBar::SetButtons](../Topic/CToolBar::SetButtons.md)|스타일 및 색인의 단추 비트맵 이미지 설정 단추를.|  
|[CToolBar::SetButtonStyle](../Topic/CToolBar::SetButtonStyle.md)|단추의 스타일을 설정합니다.|  
|[CToolBar::SetButtonText](../Topic/CToolBar::SetButtonText.md)|단추에 나타나는 텍스트를 설정 합니다.|  
|[CToolBar::SetHeight](../Topic/CToolBar::SetHeight.md)|도구 모음의 높이 설정합니다.|  
|[CToolBar::SetSizes](../Topic/CToolBar::SetSizes.md)|단추 및 해당 비트맵의 크기를 설정합니다.|  
  
## 설명  
 단추가 누름 단추, 확인란 단추, 라디오 단추와 같이 작동할 수 있습니다.  `CToolBar`개체는 클래스에서 파생 된 프레임 창 개체의 일반적으로 포함 된 구성원  [CFrameWnd](../../mfc/reference/cframewnd-class.md) 또는  [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md).  
  
 [CToolBar::GetToolBarCtrl](../Topic/CToolBar::GetToolBarCtrl.md), 멤버 함수는 새 MFC 4.0 도구 모음 사용자 지정 및 추가 기능에 대 한 Windows 공용 컨트롤 지원 기능을 사용할 수 있습니다.  `CToolBar`멤버 함수 대부분의 공용 Windows 컨트롤의 기능을 지정합니다. 그러나 호출 하면 `GetToolBarCtrl`, 도구 모음을 Windows 95\/98 도구 모음의 특징을 더 많이 제공할 수 있습니다.  호출 하면 `GetToolBarCtrl`에 대 한 참조를 반환 합니다는 `CToolBarCtrl` 개체.  참조  [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) Windows 공용 컨트롤을 사용 하 여 도구 모음을 디자인 하는 방법에 대 한 자세한 내용은.  공용 컨트롤에 대 한 자세한 내용은  [공용 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb775493) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Visual C\+\+에서는 두 가지 방법으로 도구 모음을 만들 수 있습니다.  리소스 편집기를 사용 하 여 도구 모음 리소스를 만들려면 다음과이 같이 하십시오.  
  
1.  도구 모음 리소스를 만듭니다.  
  
2.  생성 된 `CToolBar` 개체입니다.  
  
3.  호출 하는  [만들기](../Topic/CToolBar::Create.md) \(또는  [CreateEx](../Topic/CToolBar::CreateEx.md)\) Windows 도구 모음을 만들고 연결할 수 있는 함수는 `CToolBar` 개체.  
  
4.  호출  [LoadToolBar](../Topic/CToolBar::LoadToolBar.md) 도구 모음 리소스를 로드 합니다.  
  
 계정 이름이 없는 경우에는 아래 단계를 수행합니다.  
  
1.  생성 된 `CToolBar` 개체입니다.  
  
2.  호출 하는  [만들기](../Topic/CToolBar::Create.md) \(또는  [CreateEx](../Topic/CToolBar::CreateEx.md)\) Windows 도구 모음을 만들고 연결할 수 있는 함수는 `CToolBar` 개체.  
  
3.  호출  [LoadBitmap](../Topic/CToolBar::LoadBitmap.md) 도구 모음 단추 이미지가 포함 된 비트맵을 로드할 수 있습니다.  
  
4.  호출  [위해 SetButtons](../Topic/CToolBar::SetButtons.md) 단추 스타일을 설정 하 고 각 단추 비트맵에서 이미지에 연결 합니다.  
  
 모든 단추 이미지 도구 모음에 각 단추 마다 이미지가 하나씩 있어야 하는 하나의 비트맵에서 가져온 것입니다.  모든 이미지는 동일한 크기 여야 합니다. 기본값은 16 픽셀로 및 높은 15 픽셀입니다.  이미지는 비트맵에 나란히 있어야 합니다.  
  
 `SetButtons` 함수는 컨트롤 Id의 배열에서 요소의 개수를 지정 하는 정수 배열에 대 한 포인터를 사용 합니다.  각 단추의 ID 배열의 해당 요소 값을 설정 하는 기능과 각 단추 비트맵에 있는 단추 이미지의 위치를 지정 하는 이미지 인덱스를 지정 합니다.  배열 요소에 값이 있는 경우  **ID\_SEPARATOR**, 이미지 인덱스를 지정 합니다.  
  
 비트맵에서 이미지의 순서는 일반적으로 화면에 그리는 되었지만 사용할 수 있습니다 순서입니다는  [SetButtonInfo](../Topic/CToolBar::SetButtonInfo.md) 함수 관계 이미지 순서와 그리기 순서를 변경할 수 있습니다.  
  
 도구 모음에서 단추를 모두 동일한 크기입니다.  구입처에 24 x 22 픽셀은 기본값인  *소프트웨어 디자인에 대 한 Windows 인터페이스 지침*.  모든 이미지 및 단추 크기 사이 추가 공백은 이미지 주위에 테두리를 만드는 데 사용 됩니다.  
  
 각 단추 이미지가 있습니다.  다양 한 상태의 단추 및 스타일 \(누름된, 다운, 사용 안 함, 사용 안 함, 비활성화\)에서 해당 이미지 생성 됩니다.  비트맵 색상 수 있지만 검정 및 회색 음영 이미지에 최상의 결과 얻을 수 있습니다.  
  
> [!WARNING]
>  `CToolBar`16 색 최대 비트맵을 지원합니다.  이미지 도구 모음 편집기에 로드할 때 Visual Studio 자동으로 필요한 경우 이미지를 16 색 비트맵으로 변환 하 고 이미지 변환 된 경우 경고 메시지가 표시 됩니다.  이미지 \(이미지를 편집 하는 외부 편집기 사용\) 16 개 이상의 색을 사용 하는 경우 응용 프로그램이 예기치 않게 동작할 수 있습니다.  
  
 도구 모음 단추 누름 단추는 기본적으로 모방 합니다.  그러나 도구 모음 단추 또한 라디오 단추 또는 확인란 단추 모방 수 있습니다.  확인란 단추 있는 세 가지 상태: 선택 된 지워지고 확정.  라디오 단추 한 두 가지 상태: 선택 및 선택 취소 합니다.  
  
 배열을 가리키는 없이 개별 단추나 스타일 구분 기호를 설정 하려면 호출  [GetButtonStyle](../Topic/CToolBar::GetButtonStyle.md) 스타일을 검색 하 고 호출을  [SetButtonStyle](../Topic/CToolBar::SetButtonStyle.md) 대신 `SetButtons`.  `SetButtonStyle`런타임에 단추의 스타일을 변경 하려는 경우 가장 유용 합니다.  
  
 단추에 텍스트를 할당할 호출  [GetButtonText](../Topic/CToolBar::GetButtonText.md) 단추를 표시 하 고 호출 하는 텍스트를 검색 하려면  [SetButtonText](../Topic/CToolBar::SetButtonText.md) 텍스트를 설정 합니다.  
  
 스타일 지정 확인란 단추를 만들려면  **TBBS\_CHECKBOX** 또는 사용 하는 `CCmdUI` 개체의 `SetCheck` 멤버 함수에는 `ON_UPDATE_COMMAND_UI` 처리기.  호출 `SetCheck` 누름 단추 확인란 단추로 바뀝니다.  전달 `SetCheck` 0 인수 체크, 또는 2에 대 한 확인 되지 않은, 1에 대 한 확정.  
  
 라디오 단추를 만들려면 호출을  [CCmdUI](../../mfc/reference/ccmdui-class.md) 개체의  [SetRadio](../Topic/CCmdUI::SetRadio.md) 에서 멤버 함수는 `ON_UPDATE_COMMAND_UI` 처리기.  전달 `SetRadio` 0의 인수에 대 한 선택 또는 체크에 대해 0이 아닌.  상호 배타적인 라디오 그룹 동작을 제공 하려면 해야 `ON_UPDATE_COMMAND_UI` 모든 그룹에서 단추에 대 한 처리기입니다.  
  
 사용에 대 한 자세한 내용은 `CToolBar`, 문서를 참조 하십시오.  [MFC 도구 모음 구현](../../mfc/mfc-toolbar-implementation.md) 및  [기술 참고 31: 컨트롤 막대](../../mfc/tn031-control-bars.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CToolBar`  
  
## 요구 사항  
 **헤더:**  afxext.h  
  
## 참고 항목  
 [CTRLBARS MFC 샘플](../../top/visual-cpp-samples.md)   
 [MFC 샘플 DLGCBR32](../../top/visual-cpp-samples.md)   
 [MFC DOCKTOOL 샘플](../../top/visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl Class](../../mfc/reference/ctoolbarctrl-class.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [CToolBar::Create](../Topic/CToolBar::Create.md)   
 [CToolBar::LoadBitmap](../Topic/CToolBar::LoadBitmap.md)   
 [CToolBar::SetButtons](../Topic/CToolBar::SetButtons.md)   
 [CCmdUI::SetCheck](../Topic/CCmdUI::SetCheck.md)   
 [CCmdUI::SetRadio](../Topic/CCmdUI::SetRadio.md)