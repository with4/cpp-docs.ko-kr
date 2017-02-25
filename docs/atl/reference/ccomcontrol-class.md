---
title: "CComControl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComControl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ambient properties"
  - "CComControl class"
  - "CComControlBase class, CComControl class"
  - "control flags"
  - "컨트롤[ATL], control helper functions"
  - "컨트롤[ATL], 속성"
  - "스톡 속성, ATL"
ms.assetid: 55368c27-bd16-45a7-b701-edb36157c8e8
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CComControl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 만들기 및 ATL 컨트롤을 관리 하는 방법을 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template <  
class T,  
class WinBase= CWindowImpl< T>   
>  
class ATL_NO_VTABLE CComControl :  
public CComControlBase, public WinBase;  
```  
  
#### 매개 변수  
 `T`  
 컨트롤을 구현 하는 클래스입니다.  
  
 *WinBase*  
 X11 윈도우 화 기능을 구현 하는 기본 클래스입니다.  기본적으로  [CWindowImpl](../../atl/reference/cwindowimpl-class.md).  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CComControl::CComControl](../Topic/CComControl::CComControl.md)|생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComControl::ControlQueryInterface](../Topic/CComControl::ControlQueryInterface.md)|요청 된 인터페이스에 대 한 포인터를 검색합니다.|  
|[CComControl::CreateControlWindow](../Topic/CComControl::CreateControlWindow.md)|창 컨트롤을 만듭니다.|  
|[CComControl::FireOnChanged](../Topic/CComControl::FireOnChanged.md)|컨테이너의 싱크를 컨트롤 속성이 변경 되었음을 알립니다.|  
|[CComControl::FireOnRequestEdit](../Topic/CComControl::FireOnRequestEdit.md)|컨트롤 속성 변경 하 고 개체 진행 방법 싱크가 요청 컨테이너의 싱크를 알립니다.|  
|[CComControl::MessageBox](../Topic/CComControl::MessageBox.md)|만들기, 표시 및 메시지 상자를 작동 하려면이 메서드를 호출 합니다.|  
  
## 설명  
 `CComControl`도우미 함수가 유용한 컨트롤 및 ATL 컨트롤을 필수 데이터 멤버입니다.  표준 컨트롤 및 ATL 컨트롤 마법사를 사용 하 여 DHTML 컨트롤을 만드는 경우 마법사는 자동으로 클래스에서 파생 됩니다 `CComControl`.  `CComControl`대부분의 메서드를 파생 된  [CComControlBase](../../atl/reference/ccomcontrolbase-class.md).  
  
 컨트롤 만들기에 대 한 자세한 내용은  [ATL 자습서](../../atl/active-template-library-atl-tutorial.md).  ATL 프로젝트 마법사에 대 한 자세한 내용은  [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md).  
  
 `CComControl` 메서드 및 데이터 멤버를 참조 하십시오의  [CIRC](../../top/visual-cpp-samples.md) 샘플.  
  
## 상속 계층 구조  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 `CComControl`  
  
## 요구 사항  
 **헤더:**  atlctl.h  
  
## 참고 항목  
 [CWindowImpl Class](../../atl/reference/cwindowimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComControlBase Class](../../atl/reference/ccomcontrolbase-class.md)   
 [CComCompositeControl Class](../../atl/reference/ccomcompositecontrol-class.md)