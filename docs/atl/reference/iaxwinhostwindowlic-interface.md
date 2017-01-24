---
title: "IAxWinHostWindowLic Interface | Microsoft Docs"
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
  - "IAxWinHostWindowLic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAxWinHostWindowLic interface"
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IAxWinHostWindowLic Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 인터페이스 사용이 허가 된 컨트롤 및 해당 호스트 개체를 조작 하기 위한 메서드를 제공 합니다.  
  
## 구문  
  
```  
  
interface IAxWinHostWindowLic : IAxWinHostWindow  
  
```  
  
## Members  
  
### 메서드  
  
|||  
|-|-|  
|[CreateControlLic](../Topic/IAxWinHostWindowLic::CreateControlLic.md)|사용이 허가 된 컨트롤을 만들고이 호스트 개체에 연결.|  
|[CreateControlLicEx](../Topic/IAxWinHostWindowLic::CreateControlLicEx.md)|라이센스가 있는 컨트롤 호스트 개체를 연결 만들고 필요에 따라 이벤트 처리기를 설정 합니다.|  
  
## 설명  
 `IAxWinHostWindowLic`상속  [IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) 및 사용이 허가 된 컨트롤의 작성을 지 원하는 메서드를 추가 합니다.  
  
 참조  [사용할 수 있는 호스팅 ActiveX 컨트롤을 사용 하 여 ATL 클래스](../../atl/hosting-activex-controls-using-atl-axhost.md) 이 인터페이스의 멤버를 사용 하는 샘플에 대 한.  
  
## 요구 사항  
 이 인터페이스의 정의 아래와 같이 C\+\+, IDL로 사용할입니다.  
  
|형식 정의|파일|  
|-----------|--------|  
|IDL|ATLIFace.idl|  
|C\+\+|ATLIFace.h \(Atlbase.h에 포함 됨\)|