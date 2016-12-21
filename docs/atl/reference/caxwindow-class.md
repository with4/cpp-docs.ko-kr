---
title: "CAxWindow Class | Microsoft Docs"
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
  - "CAxWindowT"
  - "CAxWindow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, ActiveX 컨트롤 호스팅"
  - "CAxWindow class"
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAxWindow Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 ActiveX 컨트롤을 호스팅하는 창을 조작 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CAxWindow : public CWindow  
  
```  
  
## Members  
  
### 메서드  
  
|||  
|-|-|  
|[AttachControl](../Topic/CAxWindow::AttachControl.md)|기존 ActiveX 컨트롤에 연결 된 `CAxWindow` 개체입니다.|  
|[CAxWindow](../Topic/CAxWindow::CAxWindow.md)|`CAxWindow` 개체를 생성합니다.|  
|[CreateControl](../Topic/CAxWindow::CreateControl.md)|ActiveX 컨트롤은 초기화를 만들고 호스트에 있는 `CAxWindow` 창.|  
|[CreateControlEx](../Topic/CAxWindow::CreateControlEx.md)|ActiveX 컨트롤을 만들고 컨트롤의 인터페이스 포인터 \(또는 포인터\)를 검색 합니다.|  
|[GetWndClassName](../Topic/CAxWindow::GetWndClassName.md)|\(정적\) 미리 정의 된 클래스 이름을 검색 하는 `CAxWindow` 개체입니다.|  
|[QueryControl](../Topic/CAxWindow::QueryControl.md)|검색 된  **IUnknown** ActiveX 호스팅되는 컨트롤의.|  
|[QueryHost](../Topic/CAxWindow::QueryHost.md)|검색 된  **IUnknown** 의 포인터는 `CAxWindow` 개체.|  
|[SetExternalDispatch](../Topic/CAxWindow::SetExternalDispatch.md)|외부 디스패치 인터페이스를 사용 하 여 설정 하는 `CAxWindow` 개체입니다.|  
|[SetExternalUIHandler](../Topic/CAxWindow::SetExternalUIHandler.md)|외부 설정  **IDocHostUIHandler** 인터페이스를 사용 하는 `CAxWindow` 개체입니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[연산자 \=](../Topic/CAxWindow::operator%20=.md)|할당 된  **HWND**  기존**CAxWindow** 개체입니다.|  
  
## 설명  
 이 ActiveX 컨트롤 호스트 창을 조작 하는 방법을 제공 합니다.  호스팅에 의해 제공 됩니다 "**AtlAxWin80"**에 의해 래핑되는 `CAxWindow`.  
  
 클래스 `CAxWindow` 의 특수화로 구현 되는 `CAxWindowT` 클래스입니다.  이 특수화로 선언 됩니다.  
  
 `typedef CAxWindowT<CWindow> CAxWindow;`  
  
 기본 클래스를 변경 하는 경우 사용할 수 있습니다 `CAxWindowT` 및 새 기본 클래스를 템플릿 인수로 지정 합니다.  
  
## 요구 사항  
 **헤더:** atlwin.h  
  
## 참고 항목  
 [ATLCON 샘플](../../top/visual-cpp-samples.md)   
 [CWindow Class](../../atl/reference/cwindow-class.md)   
 [합성 컨트롤 기본 사항](../../atl/atl-composite-control-fundamentals.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [컨트롤 포함 FAQ](../../atl/atl-control-containment-faq.md)