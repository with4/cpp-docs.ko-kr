---
title: "Hosting ActiveX Controls Using ATL AXHost | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤[C++], 호스팅"
  - "AXHost method"
  - "Calendar control (ActiveX)"
  - "Calendar control (ActiveX), hosting with ATL AXHost"
  - "CAxWindow2T class"
  - "ActiveX 컨트롤 호스팅"
ms.assetid: 2c1200ec-effb-4814-820a-509519699468
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Hosting ActiveX Controls Using ATL AXHost
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목의 예제를 사용할 수 있는 클래스를 만드는 방법 및 다양 한 ATL 함수를 사용 하 여 ActiveX 컨트롤을 호스팅하는 방법을 보여 줍니다.  또한 컨트롤 및 싱크 이벤트에 액세스 하는 방법을 보여 줍니다 \(사용 하 여  [IDispEventImpl](../atl/reference/idispeventimpl-class.md)\)에서 호스팅되는 컨트롤입니다.  샘플은 주 창이 나 자식 창에서 Calendar 컨트롤을 호스팅합니다.  
  
 정의를 확인할 수 있는 `USE_METHOD` 기호.  1에서 8 사이의 다이 심볼의 값을 변경할 수 있습니다.  기호의 값은 컨트롤이 만들어지는 결정 합니다.  
  
-   짝수 번호의 값을 `USE_METHOD`, 호스트 서브 클래스는 창을 만들 수 있는 호출을 컨트롤 호스트로 변환 하는 예제입니다.  홀수 값을 코드 호스트로 작동 하는 자식 창을 만듭니다.  
  
-   값에 대 한 `USE_METHOD` 1과 4 사이 컨트롤 액세스와 이벤트 싱크 또한 호스트를 만드는 호출에서 수행 됩니다.  5에서 8 사이의 값은 인터페이스용 호스트를 쿼리하고 싱크를 후크합니다.  
  
 다음은 요약입니다.  
  
|USE\_METHOD|호스트|컨트롤 액세스와 이벤트 싱크|함수 설명|  
|-----------------|---------|---------------------|-----------|  
|1|자식 창|1 단계|CreateControlLicEx|  
|2|주 창|1 단계|AtlAxCreateControlLicEx|  
|3|자식 창|1 단계|CreateControlEx|  
|4|주 창|1 단계|AtlAxCreateControlEx|  
|5|자식 창|여러 단계|CreateControlLic|  
|6|주 창|여러 단계|AtlAxCreateControlLic|  
|7|자식 창|여러 단계|CreateControl|  
|8|주 창|여러 단계|AtlAxCreateControl|  
  
 [!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/CPP/hosting-activex-controls-using-atl-axhost_1.cpp)]  
  
## 참고 항목  
 [컨트롤 포함 FAQ](../atl/atl-control-containment-faq.md)   
 [AtlAxCreateControl](../Topic/AtlAxCreateControl.md)   
 [AtlAxCreateControlEx](../Topic/AtlAxCreateControlEx.md)   
 [AtlAxCreateControlLic](../Topic/AtlAxCreateControlLic.md)   
 [AtlAxCreateControlLicEx](../Topic/AtlAxCreateControlLicEx.md)   
 [CAxWindow2T Class](../atl/reference/caxwindow2t-class.md)   
 [IAxWinHostWindowLic Interface](../atl/reference/iaxwinhostwindowlic-interface.md)