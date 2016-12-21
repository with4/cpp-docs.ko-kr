---
title: "COleIPFrameWnd Class | Microsoft Docs"
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
  - "COleIPFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleIPFrameWnd class"
  - "in-place editing"
  - "OLE, 편집"
  - "OLE, in-place activation"
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleIPFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

응용 프로그램의 현재 위치에서 편집 창에 대 한 자료입니다.  
  
## 구문  
  
```  
class COleIPFrameWnd : public CFrameWnd  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleIPFrameWnd::COleIPFrameWnd](../Topic/COleIPFrameWnd::COleIPFrameWnd.md)|`COleIPFrameWnd` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleIPFrameWnd::OnCreateControlBars](../Topic/COleIPFrameWnd::OnCreateControlBars.md)|항목이 내부 편집을 위해 활성화 될 때 프레임 워크에 의해 호출 됩니다.|  
|[COleIPFrameWnd::RepositionFrame](../Topic/COleIPFrameWnd::RepositionFrame.md)|현재 위치에서 편집 창 위치를 프레임 워크에서 호출 됩니다.|  
  
## 설명  
 이 클래스를 만들고 막대가 문서 창 컨테이너 응용 프로그램 내에서 위치를 제어 합니다.  또한 포함 된에서 생성 된 알림 처리  [COleResizeBar](../../mfc/reference/coleresizebar-class.md) 개체를 현재 위치에서 편집 창 크기가 조정 될 때.  
  
 사용에 대 한 자세한 내용은 `COleIPFrameWnd`, 문서를 참조 하십시오.  [정품](../../mfc/activation-cpp.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `COleIPFrameWnd`  
  
## 요구 사항  
 **헤더:**  afxole.h  
  
## 참고 항목  
 [HIERSVR MFC 샘플](../../top/visual-cpp-samples.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)