---
title: "CMFCSpinButtonCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCSpinButtonCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCSpinButtonCtrl class"
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CMFCSpinButtonCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCSpinButtonCtrl` 클래스 스핀 단추 컨트롤을 그리는 비주얼 관리자를 지원 합니다.  
  
## 구문  
  
```  
class CMFCSpinButtonCtrl : public CSpinButtonCtrl  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|`CMFCSpinButtonCtrl::CMFCSpinButtonCtrl`|기본 생성자입니다.|  
|`CMFCSpinButtonCtrl::~CMFCSpinButtonCtrl`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCSpinButtonCtrl::OnDraw](../Topic/CMFCSpinButtonCtrl::OnDraw.md)|현재 스핀 단추 컨트롤을 다시 그립니다.|  
  
## 설명  
 모든 인스턴스는 비주얼 관리자를 사용 하 여 응용 프로그램에서 스핀 단추 컨트롤을 그리는 데 대체는 `CSpinButtonCtrl` 클래스에 `CMFCSpinButtonCtrl` 클래스.  
  
## 예제  
 다음 예제에서는 개체를 만드는 방법을 보여 줍니다.을 `CMFCSpinButtonCtrl` 클래스를 사용 하 고 해당 `Create` 메서드.  
  
 [!code-cpp[NVC_MFC_RibbonApp#25](../../mfc/reference/codesnippet/CPP/cmfcspinbuttonctrl-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)  
  
 [CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)  
  
## 요구 사항  
 **헤더:** afxspinbuttonctrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md)