---
title: "IAxWinHostWindow Interface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IAxWinHostWindow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAxWinHostWindow interface"
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# IAxWinHostWindow Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 인터페이스 컨트롤과 해당 호스트 개체를 조작 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
interface IAxWinHostWindow : IUnknown  
  
```  
  
## Members  
  
### 메서드  
  
|||  
|-|-|  
|[AttachControl](../Topic/IAxWinHostWindow::AttachControl.md)|기존 컨트롤의 호스트 개체에 연결합니다.|  
|[CreateControl](../Topic/IAxWinHostWindow::CreateControl.md)|컨트롤을 만들고이 호스트 개체에 연결 합니다.|  
|[CreateControlEx](../Topic/IAxWinHostWindow::CreateControlEx.md)|컨트롤을 만들고,이 호스트 개체에 연결 필요에 따라 이벤트 처리기를 설정 합니다.|  
|[QueryControl](../Topic/IAxWinHostWindow::QueryControl.md)|호스팅된 컨트롤에 대 한 인터페이스 포인터를 반환합니다.|  
|[SetExternalDispatch](../Topic/IAxWinHostWindow::SetExternalDispatch.md)|외부 설정 `IDispatch` 인터페이스.|  
|[SetExternalUIHandler](../Topic/IAxWinHostWindow::SetExternalUIHandler.md)|외부 설정 `IDocHostUIHandlerDispatch` 인터페이스.|  
  
## 설명  
 이 인터페이스는 개체 호스팅 ATL의 ActiveX 컨트롤에 의해 노출 됩니다.  만들기 및\/또는 컨트롤에 호스팅된 컨트롤에서 인터페이스를 가져올 수 또는 웹 브라우저를 호스팅하는 경우 외부 dispinterface 또는 사용에 대 한 UI 처리기를 설정 하려면 호스트 개체에 연결 하기 위해이 인터페이스의 메서드를 호출 합니다.  
  
## 요구 사항  
 이 인터페이스의 정의 아래와 같이 C\+\+, IDL로 사용할입니다.  
  
|형식 정의|파일|  
|-----------|--------|  
|IDL|ATLIFace.idl|  
|C\+\+|ATLIFace.h \(Atlbase.h에 포함 됨\)|  
  
## 참고 항목  
 [IAxWinAmbientDispatch Interface](../../atl/reference/iaxwinambientdispatch-interface.md)   
 [CAxWindow::QueryHost](../Topic/CAxWindow::QueryHost.md)   
 [AtlAxGetHost](../Topic/AtlAxGetHost.md)