---
title: "CMFCTabDropTarget Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCTabDropTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTabDropTarget class"
ms.assetid: 9777b7b6-10da-4c4b-b1d1-7ea795b0f1cb
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMFCTabDropTarget Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

탭 컨트롤 및 OLE 라이브러리 간의 통신 메커니즘을 제공합니다.  
  
## 구문  
  
```  
class CMFCTabDropTarget : public COleDropTarget  
```  
  
## Members  
  
### Public 생성자  
  
|||  
|-|-|  
|Name|설명|  
|`CMFCTabDropTarget::CMFCTabDropTarget`|기본 생성자입니다.|  
  
### Public 메서드  
  
|||  
|-|-|  
|Name|설명|  
|[CMFCTabDropTarget::OnDragEnter](../Topic/CMFCTabDropTarget::OnDragEnter.md)|사용자 탭 창으로 개체를 끌 때 프레임 워크에 의해 호출 됩니다.  \(재정의 [COleDropTarget::OnDragEnter](../Topic/COleDropTarget::OnDragEnter.md).\)|  
|[CMFCTabDropTarget::OnDragLeave](../Topic/CMFCTabDropTarget::OnDragLeave.md)|사용자가 포커스가 탭 창 외부에서 개체를 끌 때 프레임 워크에 의해 호출 됩니다.  \(재정의 [COleDropTarget::OnDragLeave](../Topic/COleDropTarget::OnDragLeave.md).\)|  
|[CMFCTabDropTarget::OnDragOver](../Topic/CMFCTabDropTarget::OnDragOver.md)|사용자가 포커스가 탭 창으로 개체를 끌 때 프레임 워크에 의해 호출 됩니다.  \(재정의 [COleDropTarget::OnDragOver](../Topic/COleDropTarget::OnDragOver.md).\)|  
|[CMFCTabDropTarget::OnDropEx](../Topic/CMFCTabDropTarget::OnDropEx.md)|끌기 작업 끝에 마우스 단추를 놓을 때 프레임 워크에 의해 호출 됩니다.  \(재정의 [COleDropTarget::OnDropEx](../Topic/COleDropTarget::OnDropEx.md).\)|  
|[CMFCTabDropTarget::Register](../Topic/CMFCTabDropTarget::Register.md)|하나는 OLE 끌어서 놓기 작업의 대상으로 컨트롤을 등록 합니다.|  
  
### 설명  
 끌어서 놓기 지원에이 클래스는 `CMFCBaseTabCtrl` 클래스입니다.  OLE 라이브러리를 사용 하 여 응용 프로그램을 초기화 하는 경우는 [AfxOleInit](../Topic/AfxOleInit.md) 함수를 `CMFCBaseTabCtrl` 개체를 등록 자체에 대 한 끌어서 놓기 작업.  
  
 `CMFCTabDropTarget` 경우 끌기 작업을 활성 커서 아래 있는 탭 하 여 기본 클래스의 클래스를 확장 합니다.  끌어서 놓기 작업에 대 한 자세한 내용은  [끌어서 놓기 \(OLE\)](../../mfc/drag-and-drop-ole.md).  
  
## 예제  
 생성 하는 다음 예제는 `CMFCTabDropTarget` 개체를 사용 하 고 해당 `Register` 메서드.  
  
 [!code-cpp[NVC_MFC_RibbonApp#39](../../mfc/reference/codesnippet/CPP/cmfctabdroptarget-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [COleDropTarget](../../mfc/reference/coledroptarget-class.md)  
  
 [CMFCTabDropTarget](../../mfc/reference/cmfctabdroptarget-class.md)  
  
## 요구 사항  
 **헤더:** afxbasetabctrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [끌어서 놓기 \(OLE\)](../../mfc/drag-and-drop-ole.md)