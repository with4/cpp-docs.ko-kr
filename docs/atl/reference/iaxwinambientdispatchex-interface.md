---
title: "IAxWinAmbientDispatchEx Interface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.IAxWinAmbientDispatchEx"
  - "IAxWinAmbientDispatchEx"
  - "ATL::IAxWinAmbientDispatchEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAxWinAmbientDispatchEx interface"
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# IAxWinAmbientDispatchEx Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

호스팅된 컨트롤의 앰비언트 속성을 보충이 인터페이스를 구현합니다.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      MIDL_INTERFACE( "B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5" )  
IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch  
```  
  
## Members  
  
### 메서드  
  
|||  
|-|-|  
|[SetAmbientDispatch](../Topic/IAxWinAmbientDispatchEx::SetAmbientDispatch.md)|이 메서드는 앰비언트 속성 기본 인터페이스와 사용자 정의 인터페이스를 보완 하기 위해 호출 됩니다.|  
  
## 설명  
 ATL 및 호스트 ActiveX 컨트롤, 특히 ActiveX 앰비언트 속성이 있는 컨트롤에 정적으로 링크 된 ATL 응용 프로그램에서이 인터페이스를 포함 합니다.  이 인터페이스는 포함 하지 않음이 어설션이 생성 됩니다: "CComModule::Init 하는 LIBID를 전달할 잊어버리셨습니까?"  
  
 이 인터페이스는 개체 호스팅 ATL의 ActiveX 컨트롤에 의해 노출 됩니다.  파생 된  [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md), `IAxWinAmbientDispatchEx` ATL에서 직접 중 하나를 제공 하는 앰비언트 속성 인터페이스를 보완 하기 위해 사용할 수 있는 메서드를 추가 합니다.  
  
 [사용할 수 있는 클래스](https://msdn.microsoft.com/en-us/library/system.windows.forms.axhost.aspx) 에 대 한 형식 정보를 로드 하려고 `IAxWinAmbientDispatch` 및 `IAxWinAmbientDispatchEx` 코드를 포함 하는 형식 라이브러리에서.  
  
 Atl90.dll을 연결 하는 경우  **사용할 수 있는 클래스** DLL에서 형식 라이브러리에서 형식 정보가 로드 됩니다.  
  
 참조  [사용할 수 있는 호스팅 ActiveX 컨트롤을 사용 하 여 ATL 클래스](../../atl/hosting-activex-controls-using-atl-axhost.md) 에 대 한 자세한 내용은.  
  
## 요구 사항  
 이 인터페이스의 정의 다음 표와 같이 여러 개의 폼에서 사용할 수 있는입니다.  
  
|형식 정의|파일|  
|-----------|--------|  
|IDL|atliface.idl|  
|형식 라이브러리|ATL.dll|  
|C\+\+|atliface.h \(Atlbase.h에 포함 됨\)|  
  
## 참고 항목  
 [IAxWinAmbientDispatch Interface](../../atl/reference/iaxwinambientdispatch-interface.md)