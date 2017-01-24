---
title: "CMDIFrameWnd Class | Microsoft Docs"
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
  - "CMDIFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMDIFrameWnd class"
  - "MDI frame windows"
ms.assetid: fa8736e6-511b-4c51-8b4d-eba78378aeb9
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMDIFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

창을 관리 하는 멤버와 함께 다중 문서 인터페이스 \(MDI\) 프레임 창에는 Windows의 기능을 제공 합니다.  
  
## 구문  
  
```  
class CMDIFrameWnd : public CFrameWnd  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMDIFrameWnd::CMDIFrameWnd](../Topic/CMDIFrameWnd::CMDIFrameWnd.md)|`CMDIFrameWnd`를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMDIFrameWnd::CreateClient](../Topic/CMDIFrameWnd::CreateClient.md)|Windows를 만드는  **MDICLIENT** 이 창 `CMDIFrameWnd`.  호출는 `OnCreate` 멤버 함수를 `CWnd`.|  
|[CMDIFrameWnd::CreateNewChild](../Topic/CMDIFrameWnd::CreateNewChild.md)|새 자식 창을 만듭니다.|  
|[CMDIFrameWnd::GetWindowMenuPopup](../Topic/CMDIFrameWnd::GetWindowMenuPopup.md)|창 팝업 메뉴를 반환합니다.|  
|[CMDIFrameWnd::MDIActivate](../Topic/CMDIFrameWnd::MDIActivate.md)|다른 MDI 자식 창을 활성화합니다.|  
|[CMDIFrameWnd::MDICascade](../Topic/CMDIFrameWnd::MDICascade.md)|종속 연결 된 형식의 모든 자식 창을 정렬합니다.|  
|[CMDIFrameWnd::MDIGetActive](../Topic/CMDIFrameWnd::MDIGetActive.md)|자식 최대화 되어 있는지 나타내는 플래그와 함께 현재 MDI 자식 창에서 검색 합니다.|  
|[CMDIFrameWnd::MDIIconArrange](../Topic/CMDIFrameWnd::MDIIconArrange.md)|최소화 된 문서 자식 창을 모두 정렬합니다.|  
|[CMDIFrameWnd::MDIMaximize](../Topic/CMDIFrameWnd::MDIMaximize.md)|MDI 자식 창을 최대화합니다.|  
|[CMDIFrameWnd::MDINext](../Topic/CMDIFrameWnd::MDINext.md)|자식 창이 현재 활성화 된 자식 창 바로 뒤를 활성화 한 뒤 모든 자식 창은 현재 활성화 된 자식 창 배치 합니다.|  
|[CMDIFrameWnd::MDIPrev](../Topic/CMDIFrameWnd::MDIPrev.md)|이전 자식 창을 활성화 하 고 현재 활성화 된 자식 창 바로 뒤에 배치 합니다.|  
|[CMDIFrameWnd::MDIRestore](../Topic/CMDIFrameWnd::MDIRestore.md)|MDI 자식 창 최대화 또는 최소화 된 크기를 복원합니다.|  
|[CMDIFrameWnd::MDISetMenu](../Topic/CMDIFrameWnd::MDISetMenu.md)|MDI 프레임 창의 메뉴 또는 팝업 메뉴 창에서 대체합니다.|  
|[CMDIFrameWnd::MDITile](../Topic/CMDIFrameWnd::MDITile.md)|모든 자식 창을 타일 형식에서 배열입니다.|  
  
## 설명  
 유용한 MDI 프레임 창 응용 프로그램을 만들려면이 클래스에서 파생 `CMDIFrameWnd`.  응용 프로그램에 데이터를 저장 하는 파생된 클래스에 멤버 변수를 추가 합니다.  메시지 창으로 전달 되는 경우 수행할 작업을 지정할 수 있는 파생된 클래스의 메시지 처리기 멤버 함수를 구현 하 고 메시지를 매핑합니다.  
  
 MDI 프레임 창을 호출 하 여 만들 수 있습니다는  [만들기](../Topic/CFrameWnd::Create.md) 또는  [LoadFrame](../Topic/CFrameWnd::LoadFrame.md) 멤버 함수를 `CFrameWnd`.  
  
 호출 하기 전에  **만들기** 또는 `LoadFrame`, C\+\+를 사용 하 여 힙에 프레임 창 개체를 생성 해야  **새** 연산자.  호출 하기 전에  **만들기** 창 클래스를 등록할 수도 있습니다는  [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) 프레임 클래스 및 아이콘 스타일을 설정 하는 전역 함수입니다.  
  
 사용 된  **만들기** 프레임 생성 매개 변수는 즉시 인수를 전달 하려면 함수.  
  
 `LoadFrame`보다 적은 인수가 필요  **만들기**, 대신 프레임의 캡션, 아이콘, 액셀러레이터 테이블 및 메뉴를 비롯 하 여 리소스에서 대부분의 기본값을 검색 합니다.  액세스 하 여 `LoadFrame`, 이러한 리소스는 동일한 리소스 ID에 있어야 합니다 \(예를 들어,  **IDR\_MAINFRAME**\).  
  
 하지만  **MDIFrameWnd** 에서 파생 된 `CFrameWnd`, 프레임 창 클래스에서 파생 된 `CMDIFrameWnd` 을 선언 해야 하지 `DECLARE_DYNCREATE`.  
  
 `CMDIFrameWnd` 클래스를 상속 하는 기본 구현에서 많은 `CFrameWnd`.  이러한 기능의 자세한 목록을 참조 하십시오의  [CFrameWnd](../../mfc/reference/cframewnd-class.md) 클래스를 설명 합니다.  `CMDIFrameWnd` 클래스에 다음과 같은 추가 기능이 있습니다.  
  
-   MDI 프레임 창 관리는  **MDICLIENT** 창의 컨트롤 막대와 함께에서 위치 합니다.  MDI 클라이언트 창이 MDI 자식 프레임 창의 직계 부모입니다.  **WS\_HSCROLL** 및  **WS\_VSCROLL** 창 스타일 지정은 `CMDIFrameWnd` MDI 클라이언트 창에 적용 대신 주 프레임 창을 스크롤하여 MDI 클라이언트 영역 \(에서 마찬가지로 Windows 프로그램 관리자, 예를 들어\) 볼 수 있도록.  
  
-   MDI 프레임 창은 활성 MDI 자식 창이 있는 경우 메뉴 표시줄로 사용 되는 기본 메뉴를 소유 합니다.  활성화 된 MDI 자식 때 MDI 프레임 창의 메뉴 표시줄 MDI 자식 창 메뉴에서 자동으로 바뀝니다.  
  
-   있을 경우 MDI 프레임 창은 현재 MDI 자식 창 함께에서 작동 합니다.  예를 들어, 명령 메시지 전에 MDI 프레임 창은 현재 MDI 자식 위임 됩니다.  
  
-   MDI 프레임 창은 다음 표준 창 메뉴 명령에 대 한 기본 처리기가 있습니다.  
  
    -   **ID\_WINDOW\_TILE\_VERT**  
  
    -   **ID\_WINDOW\_TILE\_HORZ**  
  
    -   **ID\_WINDOW\_CASCADE**  
  
    -   **ID\_WINDOW\_ARRANGE**  
  
-   MDI 프레임 창에도 구현 했습니다  **ID\_WINDOW\_NEW**, 새 프레임 및 보기는 현재 문서를 만듭니다.  응용 프로그램이 MDI 창 처리를 사용자 지정 하려면이 기본 명령 구현을 재정의할 수 있습니다.  
  
 C \+ \+를 사용 하지 않는  **삭제** 프레임 창을 소멸 하는 연산자입니다.  대신 `CWnd::DestroyWindow`를 사용하십시오.  `CFrameWnd` 구현 `PostNcDestroy` 창이 소멸 될 때 C\+\+ 개체를 삭제 합니다.  사용자는 기본 프레임 창의 닫을 때 `OnClose` 처리기를 호출 하는 `DestroyWindow`.  
  
 에 대 한 자세한 내용은 `CMDIFrameWnd`를 참조 하십시오  [프레임 Windows](../../mfc/frame-windows.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIFrameWnd`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [MFC MDI 샘플](../../top/visual-cpp-samples.md)   
 [MFC 샘플 MDIDOCVW](../../top/visual-cpp-samples.md)   
 [MFC SNAPVW 샘플](../../top/visual-cpp-samples.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CMDIChildWnd Class](../../mfc/reference/cmdichildwnd-class.md)