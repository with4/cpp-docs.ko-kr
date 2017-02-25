---
title: "CMDIChildWnd Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMDIChildWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "자식 창, CMDIChildWnd class"
  - "CMDIChildWnd class"
  - "MDI[C++], 자식 창"
  - "windows [C++], MDI"
ms.assetid: 6d07f5d4-9a3e-4723-9fa5-e65bb669fdd5
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMDIChildWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

창을 관리 하는 멤버와 함께 다중 문서 인터페이스 \(MDI\) 자식 창, Windows의 기능을 제공 합니다.  
  
## 구문  
  
```  
class CMDIChildWnd : public CFrameWnd  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMDIChildWnd::CMDIChildWnd](../Topic/CMDIChildWnd::CMDIChildWnd.md)|`CMDIChildWnd` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMDIChildWnd::Create](../Topic/CMDIChildWnd::Create.md)|관련 된 Windows MDI 자식 창을 만듭니다는 `CMDIChildWnd` 개체입니다.|  
|[CMDIChildWnd::GetMDIFrame](../Topic/CMDIChildWnd::GetMDIFrame.md)|MDI 클라이언트 창이 MDI 프레임의 부모를 반환합니다.|  
|[CMDIChildWnd::MDIActivate](../Topic/CMDIChildWnd::MDIActivate.md)|이 MDI 자식 창이 활성화 됩니다.|  
|[CMDIChildWnd::MDIDestroy](../Topic/CMDIChildWnd::MDIDestroy.md)|이 MDI 자식 창이 소멸 됩니다.|  
|[CMDIChildWnd::MDIMaximize](../Topic/CMDIChildWnd::MDIMaximize.md)|이 MDI 자식 창을 최대화합니다.|  
|[CMDIChildWnd::MDIRestore](../Topic/CMDIChildWnd::MDIRestore.md)|이 MDI 자식 창 최대화 또는 최소화 된 크기를 복원합니다.|  
|[CMDIChildWnd::SetHandles](../Topic/CMDIChildWnd::SetHandles.md)|메뉴와 액셀러레이터 리소스에 대 한 핸들을 설정합니다.|  
  
## 설명  
 MDI 자식 창 MDI 프레임 창 안에 대신 바탕 화면에 표시 된다는 처럼 일반적인 프레임 창, MDI 자식 창에서 찾습니다.  MDI 자식 창 메뉴 모음 자체의 하지는 않지만 대신 MDI 프레임 창의 메뉴를 공유 합니다.  프레임 워크는 자동으로 현재 활성 상태인 MDI 자식 창을 나타내는 MDI 프레임 메뉴를 변경 합니다.  
  
 유용한 MDI 자식 창 응용 프로그램을 만들려면이 클래스에서 파생 `CMDIChildWnd`.  응용 프로그램에 데이터를 저장 하는 파생된 클래스에 멤버 변수를 추가 합니다.  메시지 창으로 전달 되는 경우 수행할 작업을 지정할 수 있는 파생된 클래스의 메시지 처리기 멤버 함수를 구현 하 고 메시지를 매핑합니다.  
  
 MDI 자식 창 만드는 데는 다음 세 가지가 있습니다.  
  
-   직접 사용 하 여 만드는  **만들기**.  
  
-   직접 사용 하 여 만드는 `LoadFrame`.  
  
-   직접 문서 템플릿을 통해 만드는지 않습니다.  
  
 호출 하기 전에  **만들기** 또는 `LoadFrame`, C\+\+를 사용 하 여 힙에 프레임 창 개체를 생성 해야  **새** 연산자.  호출 하기 전에  **만들기** 창 클래스를 등록할 수도 있습니다는  [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) 프레임 클래스 및 아이콘 스타일을 설정 하는 전역 함수입니다.  
  
 사용 된  **만들기** 프레임 생성 매개 변수는 즉시 인수를 전달 하려면 함수.  
  
 `LoadFrame`보다 적은 인수가 필요  **만들기**, 대신 프레임의 캡션, 아이콘, 액셀러레이터 테이블 및 메뉴를 비롯 하 여 리소스에서 대부분의 기본값을 검색 합니다.  에 액세스할 수 `LoadFrame`, 이러한 리소스는 동일한 리소스 ID에 있어야 합니다 \(예를 들어,  **IDR\_MAINFRAME**\).  
  
 경우는 `CMDIChildWnd` 개체 보기 및 문서를 포함, 직접 대신 프레임 워크는 프로그래머에 의해 직접 만들어진 없습니다.  `CDocTemplate` 개체 총괄 프레임의 작성, 포함 하는 뷰를 만들고 뷰의 해당 문서에 연결 합니다.  매개 변수는 `CDocTemplate` 생성자를 지정 하는 `CRuntimeClass` \(문서, 프레임 및 보기\)의 세 가지 클래스와 관련.  A `CRuntimeClass` 개체 \(예를 들어, 새 파일 명령 또는 MDI 창 새로 만들기 명령을 사용 하 여\) 사용자가 지정 된 경우 새 프레임을 동적으로 만드는 프레임 워크에서 사용 됩니다.  
  
 프레임 창 클래스에서 파생 된 `CMDIChildWnd` 를 선언 합니다. `DECLARE_DYNCREATE` 위를 `RUNTIME_CLASS` 메커니즘이 제대로 작동 하려면.  
  
 `CMDIChildWnd` 클래스를 상속 하는 기본 구현에서 많은 `CFrameWnd`.  이러한 기능의 자세한 목록을 참조 하십시오의  [CFrameWnd](../../mfc/reference/cframewnd-class.md) 클래스를 설명 합니다.  `CMDIChildWnd` 클래스에 다음과 같은 추가 기능이 있습니다.  
  
-   함께에서 있는 `CMultiDocTemplate` 클래스, 여러 `CMDIChildWnd` 문서 템플릿에서 개체 공유 같은 메뉴, Windows 시스템 리소스를 저장 합니다.  
  
-   MDI 프레임 창 메뉴에서 현재 활성 MDI 자식 창 메뉴를 완전히 대체 하 고 현재 활성 MDI 자식 창의 캡션을 MDI 프레임 창 캡션을 추가 됩니다.  MDI 프레임 창 함께에서 구현 된 MDI 자식 창 기능에 대 한 추가 예제를 참조 하십시오의 `CMDIFrameWnd` 클래스를 설명 합니다.  
  
 C \+ \+를 사용 하지 않는  **삭제** 프레임 창을 소멸 하는 연산자입니다.  대신 `CWnd::DestroyWindow`를 사용하십시오.  `CFrameWnd` 구현 `PostNcDestroy` 창이 소멸 될 때 C\+\+ 개체를 삭제 합니다.  사용자는 기본 프레임 창의 닫을 때 `OnClose` 처리기를 호출 하는 `DestroyWindow`.  
  
 에 대 한 자세한 내용은 `CMDIChildWnd`를 참조 하십시오  [프레임 Windows](../../mfc/frame-windows.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIChildWnd`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [MFC MDI 샘플](../../top/visual-cpp-samples.md)   
 [MFC 샘플 MDIDOCVW](../../top/visual-cpp-samples.md)   
 [MFC SNAPVW 샘플](../../top/visual-cpp-samples.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd Class](../../mfc/reference/cmdiframewnd-class.md)