---
title: "CWndClassInfo Class | Microsoft Docs"
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
  - "CWndClassInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWndClassInfo class"
ms.assetid: c36fe7e1-75f1-4cf5-a06f-9f59c43fe6fb
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWndClassInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 창 클래스 등록에 대 한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CWndClassInfo  
  
```  
  
## Members  
  
### Public 메서드  
  
|||  
|-|-|  
|[등록](../Topic/CWndClassInfo::Register.md)|창 클래스를 등록합니다.|  
  
### 데이터 멤버  
  
|||  
|-|-|  
|[m\_atom](../Topic/CWndClassInfo::m_atom.md)|등록 된 창 클래스를 고유 하 게 식별합니다.|  
|[m\_bSystemCursor](../Topic/CWndClassInfo::m_bSystemCursor.md)|커서 리소스 시스템 커서를 하거나 모듈 리소스에 포함 된 커서를 참조 하는지 여부를 지정 합니다.|  
|[m\_lpszCursorID](../Topic/CWndClassInfo::m_lpszCursorID.md)|커서 리소스의 이름을 지정합니다.|  
|[m\_lpszOrigName](../Topic/CWndClassInfo::m_lpszOrigName.md)|기존 창 클래스의 이름을 포함 합니다.|  
|[m\_szAutoName](../Topic/CWndClassInfo::m_szAutoName.md)|창 클래스는 ATL 생성 이름을 보유 합니다.|  
|[m\_wc](../Topic/CWndClassInfo::m_wc.md)|창 클래스 정보를 유지 한  **WNDCLASSEX** 구조.|  
|[pWndProc](../Topic/CWndClassInfo::pWndProc.md)|기존 창 클래스의 창 프로시저를 가리킵니다.|  
  
## 설명  
 `CWndClassInfo`창 클래스의 정보를 관리합니다.  일반적으로 사용 `CWndClassInfo` 세 가지 매크로 중 하나를 통해 `DECLARE_WND_CLASS`, `DECLARE_WND_CLASS_EX`, 또는 `DECLARE_WND_SUPERCLASS`, 다음 표에 설명 된 대로.  
  
|매크로|설명|  
|---------|--------|  
|[DECLARE\_WND\_CLASS](../Topic/DECLARE_WND_CLASS.md)|`CWndClassInfo`새 창 클래스를 등록합니다.|  
|[DECLARE\_WND\_CLASS\_EX](../Topic/DECLARE_WND_CLASS_EX.md)|`CWndClassInfo`클래스 매개 변수를 포함 하는 새 창 클래스를 등록 합니다.|  
|[DECLARE\_WND\_SUPERCLASS](../Topic/DECLARE_WND_SUPERCLASS.md)|`CWndClassInfo`정보는 기존 클래스를 기반으로 하지만 다른 창 프로시저를 사용 하 여 창 클래스를 등록 합니다.  이 기술은 슈퍼 클 래 싱을 이라고 합니다.|  
  
 기본적으로  [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 포함 된 `DECLARE_WND_CLASS` 매크로 창을 만들려면 새 창 클래스를 기반으로 합니다.  DECLARE\_WND\_CLASS 기본 스타일 및 배경색에 대 한 컨트롤을 제공합니다.  배경색 직접 스타일을 지정 하는 경우 클래스에서 파생 `CWindowImpl` 등의 `DECLARE_WND_CLASS_EX` 매크로 클래스 정의에.  
  
 기존 창 클래스를 기반으로 창을 만들려면 클래스에서 파생 `CWindowImpl` 등의 `DECLARE_WND_SUPERCLASS` 매크로 클래스 정의에.  예를 들면 다음과 같습니다.  
  
 [!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/CPP/cwndclassinfo-class_1.h)]  
  
 창 클래스에 대 한 자세한 내용은  [창 클래스](http://msdn.microsoft.com/library/windows/desktop/ms632596) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 ATL에 대 한 windows 사용에 대 한 자세한 내용은  [ATL 창 클래스](../../atl/atl-window-classes.md).  
  
## 요구 사항  
 **헤더:**  atlwin.h  
  
## 참고 항목  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)