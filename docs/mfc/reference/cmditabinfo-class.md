---
title: "CMDITabInfo Class | Microsoft Docs"
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
  - "CMDITabInfo"
  - "CMDITabInfo.CMDITabInfo"
  - "CMDITabInfo::CMDITabInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMDITabInfo class"
  - "CMDITabInfo class, 생성자"
ms.assetid: 988ae1b7-4f7f-4239-b88f-7e28b3291c5e
caps.latest.revision: 37
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMDITabInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMDITabInfo` 클래스에 매개 변수를 전달 하는 데 사용 [CMDIFrameWndEx::EnableMDITabbedGroups](../Topic/CMDIFrameWndEx::EnableMDITabbedGroups.md) 메서드.  그룹 탭 MDI의 동작을 제어 하려면이 클래스의 멤버 집합  
  
## 구문  
  
```  
class CMDITabInfo   
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|`CMDITabInfo::CMDITabInfo`|기본 생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMDITabInfo::Serialize](../Topic/CMDITabInfo::Serialize.md)|읽거나 또는 보관 파일에이 개체를 씁니다.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CMDITabInfo::m\_bActiveTabCloseButton;](../Topic/CMDITabInfo::m_bActiveTabCloseButton;.md)|지정 여부는  **닫기** 단추 활성 탭의 레이블에 표시 됩니다.|  
|[CMDITabInfo::m\_bAutoColor](../Topic/CMDITabInfo::m_bAutoColor.md)|MDI 탭 색을 지정 합니다.|  
|[CMDITabInfo::m\_bDocumentMenu](../Topic/CMDITabInfo::m_bDocumentMenu.md)|탭 그룹 열었던된 문서 목록을 표시 하거나 스크롤 단추를 표시 하는 팝업 메뉴를 표시할지 여부를 지정 합니다.|  
|[CMDITabInfo::m\_bEnableTabSwap](../Topic/CMDITabInfo::m_bEnableTabSwap.md)|사용자 탭의 위치를 드래그 하 여 바꿀 수 있습니다 여부를 지정 합니다.|  
|[CMDITabInfo::m\_bFlatFrame](../Topic/CMDITabInfo::m_bFlatFrame.md)|탭 플랫 프레임 있는지 여부를 지정 합니다.|  
|[CMDITabInfo::m\_bTabCloseButton](../Topic/CMDITabInfo::m_bTabCloseButton.md)|각 탭의 레이블이 표시 되는지 여부를 지정 하는  **닫기** 단추.|  
|[CMDITabInfo::m\_bTabCustomTooltips](../Topic/CMDITabInfo::m_bTabCustomTooltips.md)|사용자 지정 도구 설명을 사용할 수 있는지 여부를 지정 합니다.|  
|[CMDITabInfo::m\_bTabIcons](../Topic/CMDITabInfo::m_bTabIcons.md)|MDI 탭에 아이콘을 표시할지 여부를 지정 합니다.|  
|[CMDITabInfo::m\_nTabBorderSize](../Topic/CMDITabInfo::m_nTabBorderSize.md)|각 탭 창 테두리 크기를 지정합니다.|  
|[CMDITabInfo::m\_style](../Topic/CMDITabInfo::m_style.md)|탭 레이블 스타일을 지정합니다.|  
|[CMDITabInfo::m\_tabLocation](../Topic/CMDITabInfo::m_tabLocation.md)|탭 레이블 위쪽 또는 페이지의 아래쪽에 있는 지 여부를 지정 합니다.|  
  
## 설명  
 이 클래스는 프레임 워크의 MDI 탭 그룹의 매개 변수를 지정 합니다.  
  
## 예제  
 다음 예제에 다양 한 멤버 변수의 값을 설정 하는 방법 `CMDITabInfo` 클래스입니다.  
  
 [!code-cpp[NVC_MFC_MDITab#1](../../mfc/reference/codesnippet/CPP/cmditabinfo-class_1.cpp)]  
  
## 상속 계층 구조  
 [CMDITabInfo](../../mfc/reference/cmditabinfo-class.md)  
  
## 요구 사항  
 **헤더:** afxmdiclientareawnd.h  
  
## 참고 항목  
 [CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)   
 [MDI 탭 그룹](../../mfc/mdi-tabbed-groups.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)