---
title: "CMiniFrameWnd Class | Microsoft Docs"
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
  - "CMiniFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMiniFrameWnd class"
  - "mini-frame windows"
  - "도구 모음[C++]"
ms.assetid: b8f534ed-0532-4d8e-9657-5595cf677749
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMiniFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 도구 모음을는 일반적으로 발생 하는 반장 프레임 창을 나타냅니다.  
  
## 구문  
  
```  
class CMiniFrameWnd : public CFrameWnd  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMiniFrameWnd::CMiniFrameWnd](../Topic/CMiniFrameWnd::CMiniFrameWnd.md)|`CMiniFrameWnd` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMiniFrameWnd::Create](../Topic/CMiniFrameWnd::Create.md)|생성 된 `CMiniFrameWnd` 개체를 생성 한 후.|  
|[CMiniFrameWnd::CreateEx](../Topic/CMiniFrameWnd::CreateEx.md)|생성 한 `CMiniFrameWnd` \(추가 옵션\)와 개체를 생성 한 후.|  
  
## 설명  
 이러한 미니 프레임 창의 달라도 최소화\/최대화 단추 또는 메뉴와 사용자를 해제 하려면 시스템 메뉴에서 한 번 클릭 하기만 하면 된다는 일반 프레임 창과 마찬가지로 동작 합니다.  
  
 사용 하는 `CMiniFrameWnd` 개체, 개체를 먼저 정의 합니다.  다음 호출의  [만들기](../Topic/CMiniFrameWnd::Create.md) 멤버 함수 미니 프레임 창에 표시 합니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `CMiniFrameWnd` 문서를 참조 하는 개체를  [도킹 및 부동 도구 모음](../../mfc/docking-and-floating-toolbars.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMiniFrameWnd`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)