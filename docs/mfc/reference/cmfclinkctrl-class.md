---
title: "CMFCLinkCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCLinkCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCLinkCtrl class"
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CMFCLinkCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCLinkCtrl` 클래스 단추를 하이퍼링크로 표시 하 고 단추를 클릭할 때 링크의 대상에 호출 합니다.  
  
## 구문  
  
```  
class CMFCLinkCtrl : public CMFCButton  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCLinkCtrl::SetURL](../Topic/CMFCLinkCtrl::SetURL.md)|단추 텍스트에 지정 된 URL을 표시합니다.|  
|[CMFCLinkCtrl::SetURLPrefix](../Topic/CMFCLinkCtrl::SetURLPrefix.md)|암시적 프로토콜 설정 \(예를 들어, "http:"\)의 URL입니다.|  
|[CMFCLinkCtrl::SizeToContent](../Topic/CMFCLinkCtrl::SizeToContent.md)|단추 텍스트 또는 비트맵을 포함 하는 단추 크기를 조정 합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCLinkCtrl::OnDrawFocusRect](../Topic/CMFCLinkCtrl::OnDrawFocusRect.md)|단추에 포커스를 그리기 전에 프레임 워크에서 호출 됩니다.|  
  
## 설명  
 파생 된 단추를 클릭할 때의 `CMFCLinkCtrl` 클래스 프레임 워크 전달 단추를 URL 매개 변수로 `ShellExecute` 메서드.  그런 다음 `ShellExecute` 메서드는 대상 URL 엽니다.  
  
## 예제  
 크기를 설정 하는 방법 다음 예제는 `CMFCLinkCtrl` 개체 및 도구 설명에 url을 설정 하는 방법에 `CMFCLinkCtrl` 개체.  이 이때의 일부인의  [새 컨트롤 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#9](../../mfc/reference/codesnippet/CPP/cmfclinkctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#10](../../mfc/reference/codesnippet/CPP/cmfclinkctrl-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)  
  
## 요구 사항  
 **헤더:** afxlinkctrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CLinkCtrl Class](../../mfc/reference/clinkctrl-class.md)   
 [CMFCButton Class](../../mfc/reference/cmfcbutton-class.md)