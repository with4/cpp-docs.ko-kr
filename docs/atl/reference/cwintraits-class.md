---
title: "CWinTraits Class | Microsoft Docs"
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
  - "CWinTraits"
  - "CMDIChildWinTraits"
  - "ATL.CWinTraits"
  - "CFrameWinTraits"
  - "ATL::CWinTraits"
  - "CControlWinTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CControlWinTraits class"
  - "CFrameWinTraits class"
  - "CMDIChildWinTraits class"
  - "CWinTraits class"
  - "window styles, default values for ATL"
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 창 개체를 만들 때 사용 되는 스타일을 표준화 하는 방법을 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template <  
DWORD t_dwStyle= 0,  
DWORD t_dwExStyle= 0  
>  
class CWinTraits  
```  
  
#### 매개 변수  
 `t_dwStyle`  
 기본 표준 창 스타일입니다.  
  
 `t_dwExStyle`  
 기본 창 스타일을 확장 합니다.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CWinTraits::GetWndExStyle](../Topic/CWinTraits::GetWndExStyle.md)|\(정적\) 검색을 위한 확장된 스타일을 `CWinTraits` 개체입니다.|  
|[CWinTraits::GetWndStyle](../Topic/CWinTraits::GetWndStyle.md)|\(정적\) 표준 스타일에 대 한 검색은 `CWinTraits` 개체입니다.|  
  
## 설명  
 이  [창 특성](../../atl/understanding-window-traits.md) 클래스는 ATL 창 개체를 만드는 데 사용 되는 스타일을 표준화 하기 위한 간단한 메서드를 제공 합니다.  이 클래스의 특수화에 템플릿 매개 변수로 사용 하 여  [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 또는 ATL의 창 클래스 사용에 대 한 기본 확장 하 고 표준 스타일을 지정 하는 다른 창 클래스의 인스턴스.  
  
 창 스타일만 다른 스타일이 호출에 지정 된 경우 사용할 기본값을 제공 하려는 경우이 서식 파일 사용  [CWindowImpl::Create](../Topic/CWindowImpl::Create.md).  
  
 ATL 창 스타일 조합을 자주 사용 하는이 서식 파일의 세 가지 미리 정의 된 특수화를 제공합니다.  
  
 `CControlWinTraits`  
 표준 컨트롤 창에 대 한 설계.  다음은 표준 스타일에 사용 됩니다:  **WS\_CHILD**,  **WS\_VISIBLE**,  **WS\_CLIPCHILDREN**, 및  **WS\_CLIPSIBLINGS**.  없음 확장된 스타일입니다.  
  
 `CFrameWinTraits`  
 표준 프레임 창에 대 한 설계.  표준 스타일을 포함:  **WS\_OVERLAPPEDWINDOW**,  **WS\_CLIPCHILDREN**, 및  **WS\_CLIPSIBLINGS**.  확장된 스타일 포함:  **WS\_EX\_APPWINDOW** 및  **WS\_EX\_WINDOWEDGE**.  
  
 `CMDIChildWinTraits`  
 표준 MDI 자식 창에 대 한 설계.  표준 스타일을 포함:  **WS\_OVERLAPPEDWINDOW**,  **WS\_CHILD**,  **WS\_VISIBLE**,  **WS\_CLIPCHILDREN**, 및  **WS\_CLIPSIBLINGS**.  확장된 스타일 포함:  **WS\_EX\_MDICHILD**.  
  
 인스턴스 당 기준으로 설정 될 수 있는 다른 스타일을 허용 하면서 창 클래스의 모든 인스턴스 사용에 대 한 특정 스타일에 설정 되어 있는지 확인 하려는 경우  [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md) 대신 합니다.  
  
## 요구 사항  
 **헤더:**  atlwin.h  
  
## 참고 항목  
 [Class Members](http://msdn.microsoft.com/ko-kr/dbe6a147-3f01-4aea-a3fb-fe6ebadc31f8)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Understanding Window Traits](../../atl/understanding-window-traits.md)