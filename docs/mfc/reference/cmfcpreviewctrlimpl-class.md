---
title: "CMFCPreviewCtrlImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCPreviewCtrlImpl"
  - "afxwin/CMFCPreviewCtrlImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPreviewCtrlImpl class"
ms.assetid: 06257fa0-54c9-478d-9d68-c9698c3f93ed
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# CMFCPreviewCtrlImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

고급 미리 보기에는 셸에서 제공 호스트 창에 배치 된 창이이 클래스를 구현 합니다.  
  
## 구문  
  
```  
class CMFCPreviewCtrlImpl : public CWnd;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCPreviewCtrlImpl::~CMFCPreviewCtrlImpl](../Topic/CMFCPreviewCtrlImpl::~CMFCPreviewCtrlImpl.md)|미리 보기 컨트롤 개체 destructs.|  
|[CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl](../Topic/CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl.md)|미리 보기 컨트롤 개체를 만듭니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCPreviewCtrlImpl::Create](../Topic/CMFCPreviewCtrlImpl::Create.md)|오버로드.  Windows 창을 만들기 위해 풍부한 미리 보기 처리기가 호출 됩니다.|  
|[CMFCPreviewCtrlImpl::Destroy](../Topic/CMFCPreviewCtrlImpl::Destroy.md)|이 컨트롤을 소멸 하는 데 필요한 경우 고급 미리 보기 처리기가 호출 됩니다.|  
|[CMFCPreviewCtrlImpl::Focus](../Topic/CMFCPreviewCtrlImpl::Focus.md)|이 컨트롤에 입력 포커스를 설정합니다.|  
|[CMFCPreviewCtrlImpl::GetDocument](../Topic/CMFCPreviewCtrlImpl::GetDocument.md)|이 미리 보기 컨트롤에 연결 된 문서를 반환 합니다.|  
|[CMFCPreviewCtrlImpl::Redraw](../Topic/CMFCPreviewCtrlImpl::Redraw.md)|이 컨트롤을 다시 그리도록 지시 합니다.|  
|[CMFCPreviewCtrlImpl::SetDocument](../Topic/CMFCPreviewCtrlImpl::SetDocument.md)|문서 구현 및 미리 보기 컨트롤 간의 관계를 미리 보기 처리기가 호출 됩니다.|  
|[CMFCPreviewCtrlImpl::SetHost](../Topic/CMFCPreviewCtrlImpl::SetHost.md)|이 컨트롤을 새 부모를 설정합니다.|  
|[CMFCPreviewCtrlImpl::SetPreviewVisuals](../Topic/CMFCPreviewCtrlImpl::SetPreviewVisuals.md)|설정의 풍부한 미리 보기 할 때 고급 미리 보기 처리기에서 콘텐츠 호출 됩니다.|  
|[CMFCPreviewCtrlImpl::SetRect](../Topic/CMFCPreviewCtrlImpl::SetRect.md)|이 컨트롤에 대 한 새 경계 사각형을 설정합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCPreviewCtrlImpl::DoPaint](../Topic/CMFCPreviewCtrlImpl::DoPaint.md)|미리 보기를 렌더링 하는 프레임 워크에서 호출 됩니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CMFCPreviewCtrlImpl::m\_clrBackColor](../Topic/CMFCPreviewCtrlImpl::m_clrBackColor.md)|미리 보기 창의 배경색입니다.|  
|[CMFCPreviewCtrlImpl::m\_clrTextColor](../Topic/CMFCPreviewCtrlImpl::m_clrTextColor.md)|미리 보기 창의 텍스트 색입니다.|  
|[CMFCPreviewCtrlImpl::m\_font](../Topic/CMFCPreviewCtrlImpl::m_font.md)|미리 보기 창에서 텍스트를 표시 하는 데 사용 되는 글꼴입니다.|  
|[CMFCPreviewCtrlImpl::m\_pDocument](../Topic/CMFCPreviewCtrlImpl::m_pDocument.md)|컨트롤의 내용이 미리 보기는 문서에 대 한 포인터입니다.|  
  
## 설명  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPreviewCtrlImpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)  
  
## 요구 사항  
 **헤더:** afxwin.h