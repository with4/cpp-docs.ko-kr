---
title: "ATL 사용할 수 있는 클래스를 사용 하 여 ActiveX 컨트롤 호스팅 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CAxWindow2T class
- Calendar control (ActiveX), hosting with ATL AXHost
- Calendar control (ActiveX)
- ActiveX controls [C++], hosting
- hosting ActiveX controls
- AXHost method
ms.assetid: 2c1200ec-effb-4814-820a-509519699468
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2aac8a8b9cbf0b72378a286943faa6e36a8f3f74
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="hosting-activex-controls-using-atl-axhost"></a>ATL 사용할 수 있는 클래스를 사용 하 여 ActiveX 컨트롤 호스팅
이 항목의 예제를 사용할 수 있는 클래스를 만드는 방법 및 다양 한 ATL 함수를 사용 하 여 ActiveX 컨트롤을 호스트 하는 방법을 보여 줍니다. 제어 및 싱크 이벤트에 액세스 하는 방법도 보여 줍니다 (사용 하 여 [IDispEventImpl](../atl/reference/idispeventimpl-class.md))에서 호스팅되는 컨트롤입니다. 샘플은 Calendar 컨트롤을 나 자식 창 주 창에 호스팅합니다.  
  
 정의 확인할 수는 `USE_METHOD` 기호입니다. 1에서 8 사이의 변경 하려면이 기호의 값을 변경할 수 있습니다. 기호 값 컨트롤은 생성 하는 방법을 결정 합니다.  
  
-   값이 짝수 `USE_METHOD`, 창 호스트 서브 클래스를 만들기에 대 한 호출 호스트 제어도 변환 합니다. 홀수 번호 값에 대 한 코드는 호스트 역할을 하는 자식 창을 만듭니다.  
  
-   값에 대 한 `USE_METHOD` 1에서 4 사이의 컨트롤에 액세스 하 고 이벤트 싱크.dgml 파일을 호스트 하는 호출에서 수행 됩니다. 5에서 8 사이의 값 인터페이스에 대 한 호스트를 쿼리하고 싱크를 연결 합니다.  
  
 다음은 요약입니다.  
  
|USE_METHOD|호스트|액세스 제어와 이벤트 싱크|함수 설명|  
|-----------------|----------|--------------------------------------|---------------------------|  
|1|자식 창|한 번|CreateControlLicEx|  
|2|주 창|한 번|AtlAxCreateControlLicEx|  
|3|자식 창|한 번|CreateControlEx|  
|4|주 창|한 번|AtlAxCreateControlEx|  
|5|자식 창|여러 단계|CreateControlLic|  
|6|주 창|여러 단계|AtlAxCreateControlLic|  
|7|자식 창|여러 단계|CreateControl|  
|9|주 창|여러 단계|AtlAxCreateControl|  
  
 [!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/cpp/hosting-activex-controls-using-atl-axhost_1.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [컨트롤 포함 FAQ](../atl/atl-control-containment-faq.md)   
 [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)   
 [AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)   
 [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)   
 [AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)   
 [CAxWindow2T 클래스](../atl/reference/caxwindow2t-class.md)   
 [IAxWinHostWindowLic 인터페이스](../atl/reference/iaxwinhostwindowlic-interface.md)

