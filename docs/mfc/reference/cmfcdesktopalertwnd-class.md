---
title: "CMFCDesktopAlertWnd Class | Microsoft Docs"
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
  - "CMFCDesktopAlertWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDesktopAlertWnd class"
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
caps.latest.revision: 33
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDesktopAlertWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCDesktopAlertWnd` 클래스 이벤트에 대 한 사용자를 알려주는 화면 기능이 표시 되는 모덜리스 대화 상자를 구현 합니다.  
  
## 구문  
  
```  
class CMFCDesktopAlertWnd : public CWnd  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md)|만들고 데스크톱 경고 창을 초기화 합니다.|  
|[CMFCDesktopAlertWnd::GetAnimationSpeed](../Topic/CMFCDesktopAlertWnd::GetAnimationSpeed.md)|애니메이션 속도 반환합니다.|  
|[CMFCDesktopAlertWnd::GetAnimationType](../Topic/CMFCDesktopAlertWnd::GetAnimationType.md)|애니메이션 형식을 반환합니다.|  
|[CMFCDesktopAlertWnd::GetAutoCloseTime](../Topic/CMFCDesktopAlertWnd::GetAutoCloseTime.md)|자동 닫기 제한 시간을 반환합니다.|  
|[CMFCDesktopAlertWnd::GetCaptionHeight](../Topic/CMFCDesktopAlertWnd::GetCaptionHeight.md)|캡션의 높이 반환합니다.|  
|[CMFCDesktopAlertWnd::GetDialogSize](../Topic/CMFCDesktopAlertWnd::GetDialogSize.md)||  
|[CMFCDesktopAlertWnd::GetLastPos](../Topic/CMFCDesktopAlertWnd::GetLastPos.md)|마지막 유효한 위치를 바탕 화면 알림 창이 화면에 반환합니다.|  
|[CMFCDesktopAlertWnd::GetTransparency](../Topic/CMFCDesktopAlertWnd::GetTransparency.md)|투명도 수준을 반환합니다.|  
|[CMFCDesktopAlertWnd::HasSmallCaption](../Topic/CMFCDesktopAlertWnd::HasSmallCaption.md)|바탕 화면 알림 창에 작은 캡션 표시 되는지 여부를 결정 합니다.|  
|[CMFCDesktopAlertWnd::OnBeforeShow](../Topic/CMFCDesktopAlertWnd::OnBeforeShow.md)||  
|[CMFCDesktopAlertWnd::OnClickLinkButton](../Topic/CMFCDesktopAlertWnd::OnClickLinkButton.md)|바탕 화면 알림 메뉴에 있는 연결 단추를 클릭할 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCDesktopAlertWnd::OnCommand](../Topic/CMFCDesktopAlertWnd::OnCommand.md)|자식 컨트롤 알림 메시지를 보낼 때 나는 액셀러레이터 키 입력을 번역 항목 메뉴에서 사용자를 선택 하면 프레임 워크는이 멤버 함수를 호출 합니다.  \(재정의 [CWnd::OnCommand](../Topic/CWnd::OnCommand.md).\)|  
|[CMFCDesktopAlertWnd::OnDraw](../Topic/CMFCDesktopAlertWnd::OnDraw.md)||  
|[CMFCDesktopAlertWnd::ProcessCommand](../Topic/CMFCDesktopAlertWnd::ProcessCommand.md)||  
|[CMFCDesktopAlertWnd::SetAnimationSpeed](../Topic/CMFCDesktopAlertWnd::SetAnimationSpeed.md)|새 애니메이션 속도 설정합니다.|  
|[CMFCDesktopAlertWnd::SetAnimationType](../Topic/CMFCDesktopAlertWnd::SetAnimationType.md)|애니메이션 종류를 설정합니다.|  
|[CMFCDesktopAlertWnd::SetAutoCloseTime](../Topic/CMFCDesktopAlertWnd::SetAutoCloseTime.md)|자동 닫기 제한 시간을 설정합니다.|  
|[CMFCDesktopAlertWnd::SetSmallCaption](../Topic/CMFCDesktopAlertWnd::SetSmallCaption.md)|작고 기본 캡션 간에 전환 합니다.|  
|[CMFCDesktopAlertWnd::SetTransparency](../Topic/CMFCDesktopAlertWnd::SetTransparency.md)|투명도 수준을 설정합니다.|  
  
## 설명  
 바탕 화면 알림 창 투명 하 게 할 수 있습니다. 그리고 애니메이션 효과 나타날 수 있습니다 \(지정 된 지연 시간 후 또는 사용자가 닫기 단추를 클릭 하 여 닫을 때\) 사라질 수 있습니다.  
  
 바탕 화면 알림 창에 메시지 텍스트 \(레이블\), 아이콘, 링크 포함 기본 대화 상자를 포함할 수도 있습니다.  또는 바탕 화면 알림 창에 사용자 지정 대화 상자에서 응용 프로그램의 리소스를 포함할 수 있습니다.  
  
 두 단계에서 바탕 화면 알림 창을 만듭니다.  먼저 생성 하는 생성자를 호출에서 `CMFCDesktopAlertWnd` 개체입니다.  두 번째 호출에서 [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md) 멤버 함수는 창에 첨부 하십시오의 `CMFCDesktopAlertWnd` 개체.  
  
 `CMFCDesktopAlertWnd` 바탕 화면 경고 창의 클라이언트 영역을 채우는 특별 한 자식 대화 상자 개체를 만듭니다.  대화 상자에 배치 된 모든 컨트롤을 소유 합니다.  
  
 팝업 창에 사용자 지정 대화 상자를 표시 하려면 다음과이 같이 하십시오.  
  
1.  `CMFCDesktopAlertDialog`에서 클래스를 파생시킵니다.  
  
2.  자식 대화 상자 템플릿 리소스를 만듭니다.  
  
3.  호출 [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md) 파생된 클래스의 런타임 클래스 정보에 대 한 포인터 및 대화 상자 템플릿 리소스 ID를 사용 합니다.  
  
4.  호스팅된 컨트롤에서 발생 하는 모든 알림을 처리 하는 사용자 지정 대화 상자를 프로그래밍 하거나 직접 이러한 알림을 처리 하는 호스트 컨트롤을 프로그래밍 합니다.  
  
 다음 함수를 사용 하 여 바탕 화면 경고 창의 동작을 제어할 수 있습니다:  
  
-   호출 하 여 애니메이션 형식 설정 [CMFCDesktopAlertWnd::SetAnimationType](../Topic/CMFCDesktopAlertWnd::SetAnimationType.md).  유효한 옵션은 펼쳐지는 밀고 페이드 합니다.  
  
-   호출 하 여 애니메이션 프레임 속도 설정 합니다. [CMFCDesktopAlertWnd::SetAnimationSpeed](../Topic/CMFCDesktopAlertWnd::SetAnimationSpeed.md).  
  
-   호출 하 여 투명도 수준을 설정 [CMFCDesktopAlertWnd::SetTransparency](../Topic/CMFCDesktopAlertWnd::SetTransparency.md).  
  
-   캡션의 크기를 작은 호출 하 여 변경 [CMFCDesktopAlertWnd::SetSmallCaption](../Topic/CMFCDesktopAlertWnd::SetSmallCaption.md).  작은 캡션 높이 7 픽셀입니다.  
  
## 예제  
 다음 예제에서는 다양 한 메서드를 사용 하는 방법의 `CMFCDesktopAlertWnd` 클래스를 구성 하는 `CMFCDesktopAlertWnd` 개체입니다.  이 예제 애니메이션 형식이 설정, 팝업 창의 투명도 설정, 알림 창 작은 캡션 표시 지정 및 알림 창 자동으로 종료 되기 전에 경과 된 시간을 설정 하는 방법을 보여 줍니다.  또한 만들기 및 바탕 화면 경고 창이 초기화 하는 예제입니다.  이 코드 조각에 속하지는  [바탕 화면 경고 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#1](../../mfc/reference/codesnippet/CPP/cmfcdesktopalertwnd-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)  
  
## 요구 사항  
 **헤더:** afxDesktopAlertWnd.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWndInfo Class](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)   
 [CMFCDesktopAlertDialog Class](../../mfc/reference/cmfcdesktopalertdialog-class.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)