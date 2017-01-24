---
title: "IAxWinAmbientDispatch Interface | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IAxWinAmbientDispatch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAxWinAmbientDispatch interface"
ms.assetid: 55ba6f7b-7a3c-4792-ae47-c8a84b683ca9
caps.latest.revision: 24
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IAxWinAmbientDispatch Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 인터페이스는 호스팅된 컨트롤 또는 컨테이너의 특성을 지정 하는 방법을 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
interface IAxWinAmbientDispatch : IDispatch  
  
```  
  
## Members  
  
### 메서드  
  
|||  
|-|-|  
|[get\_AllowContextMenu](../Topic/IAxWinAmbientDispatch::get_AllowContextMenu.md)|**컨텍스트 메뉴 사용** 속성이 호스팅된 컨트롤 자체 컨텍스트 메뉴를 표시할 수 있는지 여부를 지정 합니다.|  
|[get\_AllowShowUI](../Topic/IAxWinAmbientDispatch::get_AllowShowUI.md)|**AllowShowUI** 속성이 호스팅된 컨트롤 자체 사용자 인터페이스를 표시할 수 있는지 여부를 지정 합니다.|  
|[get\_AllowWindowlessActivation](../Topic/IAxWinAmbientDispatch::get_AllowWindowlessActivation.md)|**AllowWindowlessActivation** 속성 컨테이너는 창 없는 활성화를 허용 하는지 여부를 지정 합니다.|  
|[get\_BackColor](../Topic/IAxWinAmbientDispatch::get_BackColor.md)|`BackColor` 속성 컨테이너의 앰비언트 배경색을 지정 합니다.|  
|[get\_DisplayAsDefault](../Topic/IAxWinAmbientDispatch::get_DisplayAsDefault.md)|**DisplayAsDefault** 앰비언트 속성이 기본 컨트롤 인지 확인 하려면 컨트롤을 사용할 수 있습니다.|  
|[get\_DocHostDoubleClickFlags](../Topic/IAxWinAmbientDispatch::get_DocHostDoubleClickFlags.md)|**DocHostDoubleClickFlags** 속성 지정 작업 수행에 대 한 응답을 두 번 클릭 해야 합니다.|  
|[get\_DocHostFlags](../Topic/IAxWinAmbientDispatch::get_DocHostFlags.md)|**DocHostFlags** 속성 호스트 개체의 사용자 인터페이스 기능을 지정 합니다.|  
|[get\_Font](../Topic/IAxWinAmbientDispatch::get_Font.md)|**글꼴** 속성은 컨테이너의 앰비언트 글꼴을 지정 합니다.|  
|[get\_ForeColor](../Topic/IAxWinAmbientDispatch::get_ForeColor.md)|`ForeColor` 속성 컨테이너의 앰비언트 전경색을 지정 합니다.|  
|[get\_LocaleID](../Topic/IAxWinAmbientDispatch::get_LocaleID.md)|**LocaleID** 속성은 컨테이너의 앰비언트 로캘 ID를 지정 합니다.|  
|[get\_MessageReflect](../Topic/IAxWinAmbientDispatch::get_MessageReflect.md)|**MessageReflect** 앰비언트 속성 컨테이너 호스팅된 컨트롤에 메시지를 반영 합니다 여부를 지정 합니다.|  
|[get\_OptionKeyPath](../Topic/IAxWinAmbientDispatch::get_OptionKeyPath.md)|**OptionKeyPath** 속성 사용자 설정 레지스트리 키 경로 지정 합니다.|  
|[get\_ShowGrabHandles](../Topic/IAxWinAmbientDispatch::get_ShowGrabHandles.md)|**ShowGrabHandles** 앰비언트 속성 컨트롤 자체 잡기 핸들을 그리는 해야 하는 경우를 찾을 수 있습니다.|  
|[get\_ShowHatching](../Topic/IAxWinAmbientDispatch::get_ShowHatching.md)|**ShowHatching** 앰비언트 속성 컨트롤 자체 부 화 그리는 해야 하는 경우를 찾을 수 있습니다.|  
|[get\_UserMode](../Topic/IAxWinAmbientDispatch::get_UserMode.md)|**UserMode** 속성은 컨테이너의 앰비언트 사용자 모드를 지정 합니다.|  
|[put\_AllowContextMenu](../Topic/IAxWinAmbientDispatch::put_AllowContextMenu.md)|**컨텍스트 메뉴 사용** 속성이 호스팅된 컨트롤 자체 컨텍스트 메뉴를 표시할 수 있는지 여부를 지정 합니다.|  
|[put\_AllowShowUI](../Topic/IAxWinAmbientDispatch::put_AllowShowUI.md)|**AllowShowUI** 속성이 호스팅된 컨트롤 자체 사용자 인터페이스를 표시할 수 있는지 여부를 지정 합니다.|  
|[put\_AllowWindowlessActivation](../Topic/IAxWinAmbientDispatch::put_AllowWindowlessActivation.md)|**AllowWindowlessActivation** 속성 컨테이너는 창 없는 활성화를 허용 하는지 여부를 지정 합니다.|  
|[put\_BackColor](../Topic/IAxWinAmbientDispatch::put_BackColor.md)|`BackColor` 속성 컨테이너의 앰비언트 배경색을 지정 합니다.|  
|[put\_DisplayAsDefault](../Topic/IAxWinAmbientDispatch::put_DisplayAsDefault.md)|**DisplayAsDefault** 앰비언트 속성이 기본 컨트롤 인지 확인 하려면 컨트롤을 사용할 수 있습니다.|  
|[put\_DocHostDoubleClickFlags](../Topic/IAxWinAmbientDispatch::put_DocHostDoubleClickFlags.md)|**DocHostDoubleClickFlags** 속성 지정 작업 수행에 대 한 응답을 두 번 클릭 해야 합니다.|  
|[put\_DocHostFlags](../Topic/IAxWinAmbientDispatch::put_DocHostFlags.md)|**DocHostFlags** 속성 호스트 개체의 사용자 인터페이스 기능을 지정 합니다.|  
|[put\_Font](../Topic/IAxWinAmbientDispatch::put_Font.md)|**글꼴** 속성은 컨테이너의 앰비언트 글꼴을 지정 합니다.|  
|[put\_ForeColor](../Topic/IAxWinAmbientDispatch::put_ForeColor.md)|`ForeColor` 속성 컨테이너의 앰비언트 전경색을 지정 합니다.|  
|[put\_LocaleID](../Topic/IAxWinAmbientDispatch::put_LocaleID.md)|**LocaleID** 속성은 컨테이너의 앰비언트 로캘 ID를 지정 합니다.|  
|[put\_MessageReflect](../Topic/IAxWinAmbientDispatch::put_MessageReflect.md)|**MessageReflect** 앰비언트 속성 컨테이너 호스팅된 컨트롤에 메시지를 반영 합니다 여부를 지정 합니다.|  
|[put\_OptionKeyPath](../Topic/IAxWinAmbientDispatch::put_OptionKeyPath.md)|**OptionKeyPath** 속성 사용자 설정 레지스트리 키 경로 지정 합니다.|  
|[put\_UserMode](../Topic/IAxWinAmbientDispatch::put_UserMode.md)|**UserMode** 속성은 컨테이너의 앰비언트 사용자 모드를 지정 합니다.|  
  
## 설명  
 이 인터페이스는 개체 호스팅 ATL의 ActiveX 컨트롤에 의해 노출 됩니다.  호스팅된 컨트롤에 앰비언트 속성을 사용할 수 있는 설정 또는 기타 컨테이너의 동작을 지정 하려면이 인터페이스에서 메서드를 호출 합니다.  제공한 속성을 보완 하기 위해 `IAxWinAmbientDispatch`를 사용 하 여  [IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md).  
  
 [사용할 수 있는 클래스](https://msdn.microsoft.com/en-us/library/system.windows.forms.axhost.aspx) 에 대 한 형식 정보를 로드 하려고 `IAxWinAmbientDispatch` 및 `IAxWinAmbientDispatchEx` 코드를 포함 하는 형식 라이브러리에서.  
  
 Atl90.dll을 연결 하는 경우  **사용할 수 있는 클래스** 형식 정보에서 typelib DLL에 로드 됩니다.  
  
 참조  [사용할 수 있는 호스팅 ActiveX 컨트롤을 사용 하 여 ATL 클래스](../../atl/hosting-activex-controls-using-atl-axhost.md) 에 대 한 자세한 내용은.  
  
## 요구 사항  
 이 인터페이스의 정의 아래 표와 같이 여러 개의 폼에서 사용할 수 있는입니다.  
  
|형식 정의|파일|  
|-----------|--------|  
|IDL|atliface.idl|  
|형식 라이브러리|ATL.dll|  
|C\+\+|atliface.h \(Atlbase.h에 포함 됨\)|  
  
## 참고 항목  
 [IAxWinAmbientDispatchEx Interface](../../atl/reference/iaxwinambientdispatchex-interface.md)   
 [IAxWinHostWindow Interface](../../atl/reference/iaxwinhostwindow-interface.md)   
 [CAxWindow::QueryHost](../Topic/CAxWindow::QueryHost.md)   
 [AtlAxGetHost](../Topic/AtlAxGetHost.md)