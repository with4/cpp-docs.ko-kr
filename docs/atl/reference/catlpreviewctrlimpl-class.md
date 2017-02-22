---
title: "CAtlPreviewCtrlImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "atlpreviewctrlimpl/ATL::CAtlPreviewCtrlImpl"
  - "CAtlPreviewCtrlImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlPreviewCtrlImpl class"
ms.assetid: 39b3299e-07e4-4abc-9b6e-b54bfa3b0802
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CAtlPreviewCtrlImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 ATL 고급 미리 보기에는 셸에서 제공 호스트 창에 배치 된 창입니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
class CAtlPreviewCtrlImpl : public CWindowImpl<CAtlPreviewCtrlImpl>, public IPreviewCtrl;  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CAtlPreviewCtrlImpl::~CAtlPreviewCtrlImpl](../Topic/CAtlPreviewCtrlImpl::~CAtlPreviewCtrlImpl.md)|미리 보기 컨트롤 개체 destructs.|  
|[CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl](../Topic/CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl.md)|미리 보기 컨트롤 개체를 만듭니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CAtlPreviewCtrlImpl::Create](../Topic/CAtlPreviewCtrlImpl::Create.md)|Windows 창을 만들기 위해 풍부한 미리 보기 처리기가 호출 됩니다.|  
|[CAtlPreviewCtrlImpl::Destroy](../Topic/CAtlPreviewCtrlImpl::Destroy.md)|이 컨트롤을 소멸 하는 데 필요한 경우 고급 미리 보기 처리기가 호출 됩니다.|  
|[CAtlPreviewCtrlImpl::Focus](../Topic/CAtlPreviewCtrlImpl::Focus.md)|이 컨트롤에 입력 포커스를 설정합니다.|  
|[CAtlPreviewCtrlImpl::OnPaint](../Topic/CAtlPreviewCtrlImpl::OnPaint.md)|WM\_PAINT 메시지를 처리합니다.|  
|[CAtlPreviewCtrlImpl::Redraw](../Topic/CAtlPreviewCtrlImpl::Redraw.md)|이 컨트롤을 다시 그리도록 지시 합니다.|  
|[CAtlPreviewCtrlImpl::SetHost](../Topic/CAtlPreviewCtrlImpl::SetHost.md)|이 컨트롤을 새 부모를 설정합니다.|  
|[CAtlPreviewCtrlImpl::SetPreviewVisuals](../Topic/CAtlPreviewCtrlImpl::SetPreviewVisuals.md)|설정의 풍부한 미리 보기 할 때 고급 미리 보기 처리기에서 콘텐츠 호출 됩니다.|  
|[CAtlPreviewCtrlImpl::SetRect](../Topic/CAtlPreviewCtrlImpl::SetRect.md)|이 컨트롤에 대 한 새 경계 사각형을 설정합니다.|  
  
### Protected 메서드  
  
|이름|설명|  
|--------|--------|  
|[CAtlPreviewCtrlImpl::DoPaint](../Topic/CAtlPreviewCtrlImpl::DoPaint.md)|미리 보기를 렌더링 하는 프레임 워크에서 호출 됩니다.|  
  
### 보호 된 상수  
  
|이름|설명|  
|--------|--------|  
|[CAtlPreviewCtrlImpl::m\_plf](../Topic/CAtlPreviewCtrlImpl::m_plf.md)|미리 보기 창에서 텍스트를 표시 하는 데 사용 되는 글꼴입니다.|  
  
### 보호된 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CAtlPreviewCtrlImpl::m\_clrBack](../Topic/CAtlPreviewCtrlImpl::m_clrBack.md)|미리 보기 창의 배경색입니다.|  
|[CAtlPreviewCtrlImpl::m\_clrText](../Topic/CAtlPreviewCtrlImpl::m_clrText.md)|미리 보기 창의 텍스트 색입니다.|  
  
## 설명  
  
## 상속 계층 구조  
 `TBase`  
  
 `ATL::CMessageMap`  
  
 `ATL::CWindowImplRoot<TBase>`  
  
 `ATL::CWindowImplBaseT<TBase,TWinTraits>`  
  
 [ATL::CWindowImpl \<CAtlPreviewCtrlImpl\>](../../atl/reference/cwindowimpl-class.md)  
  
 `IPreviewCtrl`  
  
 `ATL::CAtlPreviewCtrlImpl`  
  
## 요구 사항  
 **헤더:**  atlpreviewctrlimpl.h  
  
## 참고 항목  
 [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md)