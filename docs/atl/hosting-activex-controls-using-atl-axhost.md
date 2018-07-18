---
title: ATL AXHost를 사용 하 여 ActiveX 컨트롤 호스팅 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow2T class
- Calendar control (ActiveX), hosting with ATL AXHost
- Calendar control (ActiveX)
- ActiveX controls [C++], hosting
- hosting ActiveX controls
- AXHost method
ms.assetid: 2c1200ec-effb-4814-820a-509519699468
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e26fd9e80b96c2b0196e3fd0e11b9c97f0f3bff3
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027208"
---
# <a name="hosting-activex-controls-using-atl-axhost"></a>ATL AXHost를 사용 하 여 ActiveX 컨트롤 호스팅
이 항목의 예제에는 사용할 수 있는 클래스를 만드는 방법 및 다양 한 ATL 함수를 사용 하 여 ActiveX 컨트롤을 호스트 하는 방법을 보여 줍니다. 또한 컨트롤 및 싱크 이벤트를 액세스 하는 방법을 보여 줍니다 (사용 하 여 [IDispEventImpl](../atl/reference/idispeventimpl-class.md))에서 호스트 되는 컨트롤입니다. 주 창 또는 자식 창에서 달력 컨트롤을 호스트 하는 샘플입니다.  
  
 USE_METHOD 기호의 정의 확인 합니다. 1에서 8 사이의 변경 하려면이 기호의 값을 변경할 수 있습니다. 컨트롤은 생성 하는 방법을 결정 하는 기호의 값:  
  
-   짝수 use_method, 창 호스트 서브 클래스를 만들기에 대 한 호출에 대 한 컨트롤 호스트를 변환 합니다. 홀수 번호 값에 대 한 코드는 호스트 역할을 하는 자식 창을 만듭니다.  
  
-   Use_method 1에서 4 사이의 컨트롤에 대 한 액세스를 지원 하므로 이벤트 싱크는 호출에 대 한 호스트를 만들어지는 합니다. 5 ~ 8 사이의 값 인터페이스에 대 한 호스트를 쿼리하고 싱크를 연결 합니다.  
  
다음은 요약입니다.  
  
|USE_METHOD|호스트|액세스 제어와 이벤트 싱크|함수 설명|  
|-----------------|----------|--------------------------------------|---------------------------|  
|1|자식 창|한 단계|CreateControlLicEx|  
|2|주 창|한 단계|AtlAxCreateControlLicEx|  
|3|자식 창|한 단계|CreateControlEx|  
|4|주 창|한 단계|AtlAxCreateControlEx|  
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

