---
title: "CBitmapButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CBitmapButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "비트맵, button controls"
  - "단추, 비트맵"
  - "CBitmapButton class"
ms.assetid: 9ad6cb45-c3c4-4fb1-96d3-1fe3df7bbcfc
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBitmapButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비트맵 이미지 대신 텍스트를 표시 하는 누름 단추 컨트롤을 만듭니다.  
  
## 구문  
  
```  
class CBitmapButton : public CButton  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CBitmapButton::CBitmapButton](../Topic/CBitmapButton::CBitmapButton.md)|`CBitmapButton` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CBitmapButton::AutoLoad](../Topic/CBitmapButton::AutoLoad.md)|단추 대화 상자에 있는 개체의 연결을 `CBitmapButton` 클래스 이름으로 bitmap\(s\)를 로드 및 비트맵에 맞게 단추 크기를 조정 합니다.|  
|[CBitmapButton::LoadBitmaps](../Topic/CBitmapButton::LoadBitmaps.md)|응용 프로그램의 리소스 파일에서 하나 이상의 명명 된 비트맵 리소스를 로드 하 고 비트맵 개체에 연결 된 개체를 초기화 합니다.|  
|[CBitmapButton::SizeToContent](../Topic/CBitmapButton::SizeToContent.md)|비트맵에 맞게 단추 크기를 조정 합니다.|  
  
## 설명  
 `CBitmapButton`이미지 단추를 담당할 수 있습니다 서로 다른 상태를 포함 하는 최대 4 개의 비트맵 개체를 포함: 업 \(또는 보통\), 아래쪽 \(또는 선택한\) 포커스 및 사용 하지 않도록 설정 합니다.  첫 번째 비트맵만입니다. 나머지는 선택적입니다.  
  
 단추 비트맵 이미지의 테두리는 이미지 뿐 아니라 이미지를 포함.  일반적으로 테두리 단추 상태 표시에서 부품을 재생 합니다.  예를 들어, 비트맵에 포커스가 있는 상태 같은 테두리 또는 테두리를 굵은 실선을 파선된 사각형 오목 하지만 최신 상태에 대 한 일반적입니다.  일반적으로 사용 안 함 상태에 대 한 최신 상태에 있지만 낮은 대비 \(예: 흐리게 또는 회색으로 표시 되는 메뉴 선택\) 있는 비트맵을 비슷합니다.  
  
 모든 크기의 이러한 비트맵 되지만 같은 크기의 비트맵에 대 한 최신 상태 처럼 모두 처리 됩니다.  
  
 다양 한 응용 프로그램은 비트맵 이미지의 다양 한 조합을 요구합니다.  
  
|위쪽 화살표|아래로|Focused|Disabled|Application|  
|------------|---------|-------------|--------------|-----------------|  
|×||||비트맵|  
|×|×|||단추 없이  **WS\_TABSTOP** 스타일|  
|×|×|×|×|모든 상태의 단추|  
|×|×|×||단추와  **WS\_TABSTOP** 스타일|  
  
 비트맵 단추 컨트롤을 만들 때 설정 된  **BS\_OWNERDRAW** 소유자가 그린 단추 임을 지정 하는 스타일.  그러면 보내려면 Windows는 `WM_MEASUREITEM` 및 `WM_DRAWITEM` 메시지 단추. 이러한 메시지를 처리 하 고 모양 단추를 관리 하는 프레임 워크.  
  
### 창의 클라이언트 영역에 비트맵 단추 컨트롤을 만들려면  
  
1.  1 ~ 4 단추 비트맵 이미지를 만듭니다.  
  
2.  생성 된  [CBitmapButton](../Topic/CBitmapButton::CBitmapButton.md) 개체입니다.  
  
3.  호출 된  [만들기](../Topic/CButton::Create.md) Windows 단추 컨트롤을 만들고 연결할 수 있는 함수는 `CBitmapButton` 개체.  
  
4.  호출의  [LoadBitmaps](../Topic/CBitmapButton::LoadBitmaps.md) 멤버 함수는 비트맵 단추를 생성 후 비트맵 리소스를 로드 합니다.  
  
### 비트맵 단추 컨트롤을 대화 상자에 포함.  
  
1.  1 ~ 4 단추 비트맵 이미지를 만듭니다.  
  
2.  대화 상자 템플릿을 비트맵 단추를 나타낼 위치에 배치 하는 소유자 그리기 단추를 만듭니다.  단추는 서식 파일에서의 크기는 중요 하지 않습니다.  
  
3.  캡션 단추의 값을 설정 "**MYIMAGE**" 단추 심볼을 정의 하 고  **IDC\_MYIMAGE**.  
  
4.  응용 프로그램의 리소스 스크립트에 게 이미지의 각 단추에 대 한 ID 생성 한 문자 "U", "D," 추가 하 여 만든 "F" 또는 "X" \(위로, 아래로, 포커스 및 비활성화에 대 한\) 단추 캡션에 사용 되는 문자열을 3 단계에서.  단추 캡션에 대 한 "**MYIMAGE**," Id 됩니다 예를 들어, "**MYIMAGEU**," "**MYIMAGED**," "**MYIMAGEF**," 및 "**MYIMAGEX**." 사용자  **해야** ID를 큰따옴표 내에 비트맵을 지정 합니다.  그렇지 않으면 리소스 편집기 정수 리소스에 할당 됩니다 및 MFC 이미지를 로드 하는 동안 실패 합니다.  
  
5.  응용 프로그램의 대화 상자 클래스에 \(에서 파생 된 `CDialog`\), 추가 `CBitmapButton` 구성원 개체입니다.  
  
6.  에 `CDialog` 개체의  [OnInitDialog](../Topic/CDialog::OnInitDialog.md) 루틴을 호출의 `CBitmapButton` 개체의  [자동 로드](../Topic/CBitmapButton::AutoLoad.md) 매개 변수로 단추의 컨트롤 ID를 사용 하 여 작동 하는 `CDialog` 개체의  **이** 포인터.  
  
 같은 Windows 알림 메시지를 처리 하려는 경우  **BN\_CLICKED**, 비트맵 단추 컨트롤을 해당 부모에서 보낸 \(일반적으로 클래스에서 파생 된  **CDialog\)**, 추가 `CDialog`\-각 메시지에 대해 메시지 맵 개체 항목과 메시지 처리기 멤버 함수를 파생 합니다.  알림을 보낸는 `CBitmapButton` 개체는 동일 보낸는  [CButton](../../mfc/reference/cbutton-class.md) 개체.  
  
 클래스  [CToolBar](../../mfc/reference/ctoolbar-class.md) 비트맵 단추에 다른 방법을 사용 합니다.  
  
 에 대 한 자세한 내용은 `CBitmapButton`를 참조 하십시오[컨트롤](../../mfc/controls-mfc.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CBitmapButton`  
  
## 요구 사항  
 **헤더:**  afxext.h  
  
## 참고 항목  
 [CTRLTEST MFC 샘플](../../top/visual-cpp-samples.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)