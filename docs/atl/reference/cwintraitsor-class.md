---
title: "CWinTraitsOR Class | Microsoft Docs"
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
  - "ATL.CWinTraitsOR"
  - "ATL::CWinTraitsOR"
  - "CWinTraitsOR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinTraitsOR class"
  - "window styles, default values for ATL"
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinTraitsOR Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 창 개체를 만들 때 사용 되는 스타일을 표준화 하는 방법을 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template <  
DWORD t_dwStyle= 0,  
DWORDt_dwExStyle= 0,  
class TWinTraits = CControlWinTraits   
>  
class CWinTraitsOR  
```  
  
#### 매개 변수  
 `t_dwStyle`  
 기본 창 스타일입니다.  
  
 `t_dwExStyle`  
 기본 창 스타일을 확장 합니다.  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CWinTraitsOR::GetWndExStyle](../Topic/CWinTraitsOR::GetWndExStyle.md)|검색을 위한 확장된 스타일을 `CWinTraitsOR` 개체입니다.|  
|[CWinTraitsOR::GetWndStyle](../Topic/CWinTraitsOR::GetWndStyle.md)|표준 스타일에 대 한 검색은 `CWinTraitsOR` 개체입니다.|  
  
## 설명  
 이  [창 특성](../../atl/understanding-window-traits.md) 클래스는 ATL 창 개체를 만드는 데 사용 되는 스타일을 표준화 하기 위한 간단한 메서드를 제공 합니다.  이 클래스의 특수화에 템플릿 매개 변수로 사용 하 여  [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 또는 다른 ATL의 창 클래스를 확장 하 고 표준 스타일에 사용할 최소 집합을 지정할 수는 창 클래스의 인스턴스.  
  
 이 템플릿의 특수화를 사용 하는 특정 스타일 창 클래스의 모든 인스턴스를 다른 스타일을 동시에 호출 하 여 인스턴스 당 기준으로 설정할 수 설정 되어 있는지 확인 하려는 경우  [CWindowImpl::Create](../Topic/CWindowImpl::Create.md).  
  
 창 스타일만 다른 스타일이 호출에 지정 된 경우 사용할 기본값을 제공 하려는 경우 `CWindowImpl::Create`를 사용 하 여  [용으로 CWinTraits](../../atl/reference/cwintraits-class.md) 대신 합니다.  
  
## 요구 사항  
 **헤더:**  atlwin.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)   
 [Understanding Window Traits](../../atl/understanding-window-traits.md)