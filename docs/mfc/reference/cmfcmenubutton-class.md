---
title: "CMFCMenuButton 클래스 | Microsoft Docs"
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
  - "CMFCMenuButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCMenuButton 클래스"
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
caps.latest.revision: 32
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCMenuButton 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

팝업 메뉴를 표시 하 고 사용자 메뉴 선택에서 보고서 단추입니다.  
  
## 구문  
  
```  
class CMFCMenuButton : public CMFCButton  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CMFCMenuButton::CMFCMenuButton](../Topic/CMFCMenuButton::CMFCMenuButton.md)|`CMFCMenuButton` 개체를 생성합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCMenuButton::PreTranslateMessage](../Topic/CMFCMenuButton::PreTranslateMessage.md)|창 메시지를 디스패치하기 전에 변환 하는 프레임 워크에서 호출 됩니다.  \(재정의 `CMFCButton::PreTranslateMessage`.\)|  
|[CMFCMenuButton::SizeToContent](../Topic/CMFCMenuButton::SizeToContent.md)|텍스트 및 이미지 크기에 따라 단추 크기를 변경합니다.|  
  
### 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CMFCMenuButton::m\_bOSMenu](../Topic/CMFCMenuButton::m_bOSMenu.md)|시스템 기본 팝업 메뉴를 표시 하거나 사용 여부 지정 [CContextMenuManager::TrackPopupMenu](../Topic/CContextMenuManager::TrackPopupMenu.md).|  
|[CMFCMenuButton::m\_bRightArrow](../Topic/CMFCMenuButton::m_bRightArrow.md)|팝업 메뉴 아래쪽 또는 오른쪽에 있는 단추를 표시할지 여부를 지정 합니다.|  
|[CMFCMenuButton::m\_bStayPressed](../Topic/CMFCMenuButton::m_bStayPressed.md)|사용자는 단추를 해제 한 후 \[메뉴\] 단추 상태 변경 되는지 여부를 지정 합니다.|  
|[CMFCMenuButton::m\_hMenu](../Topic/CMFCMenuButton::m_hMenu.md)|연결 된 Windows 메뉴에 대 한 핸들입니다.|  
|[CMFCMenuButton::m\_nMenuResult](../Topic/CMFCMenuButton::m_nMenuResult.md)|팝업 메뉴에서 사용자가 선택 하는 항목을 나타내는 식별자.|  
  
## 설명  
 `CMFCMenuButton` 클래스에서 파생 되는 [CMFCButton Class](../../mfc/reference/cmfcbutton-class.md) 에서 파생 된 경우에 [CButton Class](../../mfc/reference/cbutton-class.md).  따라서 사용할 수 있습니다 `CMFCMenuButton` 사용 하는 코드에서 `CButton`.  
  
 만들 때의 `CMFCMenuButton`, 팝업 메뉴에 연결 된 핸들을 전달 해야 합니다.  다음으로 함수를 호출 합니다. `CMFCMenuButton::SizeToContent`.  `CMFCMenuButton::SizeToContent`단추 크기는 팝업 창\-즉, 아래쪽 또는 오른쪽에 있는 단추 나타날 위치를 가리키는 화살표가 포함에 충분 한지 확인 합니다.  
  
## 예제  
 다음 예제에서는 단추에 연결 된 메뉴의 핸들을 설정, 텍스트 및 이미지 크기에 따라 단추 크기를 조정 및 프레임 워크에 의해 표시 되는 팝업 메뉴를 설정 하는 방법을 보여 줍니다.  이 코드의 일부인의  [새 컨트롤 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#38](../../mfc/reference/codesnippet/CPP/cmfcmenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#39](../../mfc/reference/codesnippet/CPP/cmfcmenubutton-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)  
  
## 요구 사항  
 **헤더:** afxmenubutton.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCButton Class](../../mfc/reference/cmfcbutton-class.md)