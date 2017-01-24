---
title: "CContainedWindowT Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CContainedWindow"
  - "CContainedWindowT"
  - "ATL.CContainedWindowT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CContainedWindow class"
  - "CContainedWindowT class"
  - "contained windows"
ms.assetid: cde0ca36-9347-4068-995a-d294dae57ca9
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CContainedWindowT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 다른 개체에 포함 된 창을 구현 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template <  
class TBase= CWindow,  
class TWinTraits= CControlWinTraits   
>  
class CContainedWindowT :  
public TBase  
```  
  
#### 매개 변수  
 *TBase*  
 새 클래스의 기본 클래스입니다.  기본 기본 클래스인 `CWindow`.  
  
 `TWinTraits`  
 창 스타일을 정의 하는 특성 클래스입니다.  기본값은 `CControlWinTraits`입니다.  
  
> [!NOTE]
>  [CContainedWindow](../Topic/CContainedWindow.md) 의 특수화 된 `CContainedWindowT`.  사용할 기본 클래스 또는 특성을 변경 하려는 경우 `CContainedWindowT` 직접.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CContainedWindowT::CContainedWindowT](../Topic/CContainedWindowT::CContainedWindowT.md)|생성자입니다.  지정 메시지 맵에 포함 된 창의 메시지를 처리 하는 데이터 멤버를 초기화 합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CContainedWindowT::Create](../Topic/CContainedWindowT::Create.md)|창을 만듭니다.|  
|[CContainedWindowT::DefWindowProc](../Topic/CContainedWindowT::DefWindowProc.md)|기본 메시지 처리를 제공합니다.|  
|[CContainedWindowT::GetCurrentMessage](../Topic/CContainedWindowT::GetCurrentMessage.md)|현재 메시지를 반환합니다.|  
|[CContainedWindowT::RegisterWndSuperclass](../Topic/CContainedWindowT::RegisterWndSuperclass.md)|포함 된 창의 창 클래스를 등록 합니다.|  
|[CContainedWindowT::SubclassWindow](../Topic/CContainedWindowT::SubclassWindow.md)|창을 서브 클래스입니다.|  
|[CContainedWindowT::SwitchMessageMap](../Topic/CContainedWindowT::SwitchMessageMap.md)|변경 내용이 포함 된 창의 메시지를 처리 하는 메시지 맵을 사용 합니다.|  
|[CContainedWindowT::UnsubclassWindow](../Topic/CContainedWindowT::UnsubclassWindow.md)|이전에 서브클래싱된 창을 복원 합니다.|  
|[CContainedWindowT::WindowProc](../Topic/CContainedWindowT::WindowProc.md)|\(정적\) 포함 된 창에 보내는 메시지를 처리 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CContainedWindowT::m\_dwMsgMapID](../Topic/CContainedWindowT::m_dwMsgMapID.md)|식별 어떤 메시지 맵에 포함 된 창의 메시지를 처리 합니다.|  
|[CContainedWindowT::m\_lpszClassName](../Topic/CContainedWindowT::m_lpszClassName.md)|새 창 클래스 기반이 될 기존 창 클래스의 이름을 지정 합니다.|  
|[CContainedWindowT::m\_pfnSuperWindowProc](../Topic/CContainedWindowT::m_pfnSuperWindowProc.md)|창 클래스의 원본 창 프로시저를 가리킵니다.|  
|[CContainedWindowT::m\_pObject](../Topic/CContainedWindowT::m_pObject.md)|포함 된 개체를 가리킵니다.|  
  
## 설명  
 `CContainedWindowT`다른 개체에 포함 된 창을 구현 합니다.  `CContainedWindowT`창 프로시저 사용 메시지 매핑 직접 메시지를 적절 한 처리기에 포함 된 개체에서의 수입니다.  구성 하는 경우는 `CContainedWindowT` 개체를 지정 하는 메시지 맵을 사용 해야 합니다.  
  
 `CContainedWindowT`새 창 슈퍼 클 래 싱으로 기존 창 클래스를 만들 수 있습니다.  **만들기** 메서드는 먼저 기존 클래스를 기반으로 하지만 사용 하는 창 클래스 등록 `CContainedWindowT::WindowProc`.  **만들기** 다음이 새 창 클래스를 기반으로 하는 창을 만듭니다.  각 인스턴스의 `CContainedWindowT` 다른 창 클래스를 슈퍼 클래스에 있습니다.  
  
 `CContainedWindowT`창 서브클래싱도 지원합니다.  `SubclassWindow` 메서드는 기존 창에 연결 된 `CContainedWindowT` 개체 및 창 프로시저에 변경 `CContainedWindowT::WindowProc`.  각 인스턴스의 `CContainedWindowT` 는 다른 창을 서브 클래스 수 있습니다.  
  
> [!NOTE]
>  제공에 대 한 `CContainedWindowT` 개체, 프로시저 호출  **만들기** 또는 `SubclassWindow`.  모두 같은 개체의 메서드를 호출 해야 합니다.  
  
 사용 하는 경우는  **추가 컨트롤을 기반으로** 옵션 ATL 프로젝트 마법사에서 마법사가 자동으로 추가 합니다는 `CContainedWindowT` 컨트롤을 구현 하는 클래스의 데이터 멤버로.  다음 예제에서는 포함 된 창의 선언 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_ATL_Windowing#38](../../atl/codesnippet/CPP/ccontainedwindowt-class_1.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#39](../../atl/codesnippet/CPP/ccontainedwindowt-class_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#40](../../atl/codesnippet/CPP/ccontainedwindowt-class_3.h)]  
  
|추가 정보|참조|  
|-----------|--------|  
|컨트롤 만들기|[ATL 자습서](../../atl/active-template-library-atl-tutorial.md)|  
|ATL에서 창을 사용 하 여|[ATL 창 클래스](../../atl/atl-window-classes.md)|  
|ATL 프로젝트 마법사|[ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)|  
|Windows|[Windows](http://msdn.microsoft.com/library/windows/desktop/ms632595) 및 다음 항목에는[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]|  
  
## 상속 계층 구조  
 `TBase`  
  
 `CContainedWindowT`  
  
## 요구 사항  
 **헤더:**  atlwin.h  
  
## 참고 항목  
 [CWindow Class](../../atl/reference/cwindow-class.md)   
 [CWindowImpl Class](../../atl/reference/cwindowimpl-class.md)   
 [CMessageMap Class](../../atl/reference/cmessagemap-class.md)   
 [BEGIN\_MSG\_MAP](../Topic/BEGIN_MSG_MAP.md)   
 [ALT\_MSG\_MAP](../Topic/ALT_MSG_MAP.md)   
 [Class Overview](../../atl/atl-class-overview.md)