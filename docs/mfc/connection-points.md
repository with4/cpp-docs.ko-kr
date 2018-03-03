---
title: "연결 지점 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IConnectionPoint
dev_langs:
- C++
helpviewer_keywords:
- IConnectionPoint interface
- connections, connection points
- OLE COM connection points
- MFC COM, connection points
- COM, connection points
- interfaces, IConnectionPoint
- MFC, COM support
- connection points [MFC]
- CCmdTarget class [MFC], and connection points
- sinks, connection points
ms.assetid: bc9fd7c7-8df6-4752-ac8c-0b177442c88d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0d8bbb131aa5d4ce1b12cba84c3928b80a8b2a7e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="connection-points"></a>연결 지점
이 문서에서는 연결 지점 (이전의 OLE 연결점)를 구현 하는 방법을 설명 하는 MFC 클래스를 사용 하 여 `CCmdTarget` 및 `CConnectionPoint`합니다.  
  
 이전에 구성 요소 개체 모델 (COM) 정의 하는 일반 메커니즘 (**iunknown:: Queryinterface**) 사용할 수 있는 개체를 구현 하 고 인터페이스의 기능을 노출 합니다. 그러나 특정 인터페이스를 호출 기능을 노출 하는 개체를 사용할 수 있는 해당 메커니즘 정의 되지 않았습니다. COM 개체에 어떻게 들어오는 포인터를 정의 하는, 즉 (해당 개체의 인터페이스에 대 한 포인터)를 처리 하지만 송신 인터페이스 (다른 개체의 인터페이스에 개체를 보유 하는 포인터)에 대 한 명시적 모델과 되지 않았습니다. COM에는 모델 연결 지점 이라는이 기능을 지원 합니다.  
  
 연결에는 두 부분이: 원본과 인터페이스를 구현 하는 개체 인터페이스를 호출 하는 개체는 싱크 라는 합니다. 연결 점은 원본에 의해 노출 되는 인터페이스입니다. 연결점을 표시 함으로써 소스 싱크를 자체 (원본)에 대 한 연결을 설정할 수 있습니다. 연결을 통해 지점 메커니즘 (의 **IConnectionPoint** 인터페이스)를 싱크 인터페이스에 대 한 포인터는 원본 개체에 전달 됩니다. 이 포인터는 멤버 함수는 집합의 싱크 구현에 대 한 액세스를 사용 하 여 소스를 제공합니다. 예를 들어 싱크에 의해 구현 된 이벤트를 발생 시키는 소스 싱크 구현의 적절 한 메서드를 호출할 수 있습니다. 다음 그림에는 연결 방법을 보여 줍니다. 위에서 설명한 지점입니다.  
  
 ![연결 지점 구현](../mfc/media/vc37lh1.gif "vc37lh1")  
구현된 연결 지점  
  
 MFC에이 모델을 구현 하는 [CConnectionPoint](../mfc/reference/cconnectionpoint-class.md) 및 [CCmdTarget](../mfc/reference/ccmdtarget-class.md) 클래스입니다. 클래스에서 파생 된 **CConnectionPoint** 구현는 **IConnectionPoint** 인터페이스를 다른 개체에 대 한 연결 지점을 노출 하는 데 사용 합니다. 클래스에서 파생 된 `CCmdTarget` 구현는 **IConnectionPointContainer** 인터페이스를 사용할 수 있는 연결 지점 개체의 모든 열거 하거나 특정 연결 지점을 찾을 수 있습니다.  
  
 클래스에서 구현 된 각 연결 지점에 대 한 연결 지점을 구현 하는 연결 부분이 선언 해야 합니다. 하나 이상의 연결점을 구현 하는 경우에 클래스에도 단일 연결 맵을 선언 해야 합니다. 연결 맵을 ActiveX 컨트롤에서 지 원하는 연결 지점의 테이블입니다.  
  
 다음 예에서는 간단한 연결 맵과 한 연결점을 보여 줍니다. 첫 번째 예제에서는 연결 맵 및 포인트를 선언합니다. 두 번째 예제는 맵과 연결 지점을 구현합니다. `CMyClass` 이어야 합니다는 `CCmdTarget`-클래스를 파생 합니다. 첫 번째 예제에서 코드에에서 삽입 됩니다 클래스 선언에서는 **보호** 섹션:  
  
 [!code-cpp[NVC_MFCConnectionPoints#1](../mfc/codesnippet/cpp/connection-points_1.h)]  
  
 `BEGIN_CONNECTION_PART` 및 **END_CONNECTION_PART** 매크로 포함 된 클래스를 선언 `XSampleConnPt` (에서 파생 된 `CConnectionPoint`),이 특정 연결 지점 구현 합니다. 재정의 하려는 경우 `CConnectionPoint` 멤버 함수 또는 자신만의 멤버 함수를 추가, 이러한 두 매크로 사이 선언 합니다. 예를 들어는 `CONNECTION_IID` 매크로 재정의 `CConnectionPoint::GetIID` 이러한 두 매크로 사이 배치 하는 경우 멤버 함수입니다.  
  
 두 번째 예제에서 코드는 컨트롤 구현 파일 (.cpp 파일)에 삽입 됩니다. 이 코드는 연결점을 포함 하 여 연결 맵을 구현 `SampleConnPt`:  
  
 [!code-cpp[NVC_MFCConnectionPoints#2](../mfc/codesnippet/cpp/connection-points_2.cpp)]  
  
 클래스에 둘 이상의 연결이 차례로 추가 삽입 하는 경우 `CONNECTION_PART` 간에 매크로 `BEGIN_CONNECTION_MAP` 및 `END_CONNECTION_MAP` 매크로입니다.  
  
 에 대 한 호출을 마지막으로 추가 `EnableConnections` 클래스의 생성자입니다. 예:  
  
 [!code-cpp[NVC_MFCConnectionPoints#3](../mfc/codesnippet/cpp/connection-points_3.cpp)]  
  
 이 코드에 삽입 되 면 프로그램 `CCmdTarget`-파생된 클래스에 대 한 연결 지점을 노출 된 **ISampleSink** 인터페이스입니다. 다음 그림에서는이 예제를 보여 줍니다.  
  
 ![MFC를 사용 하 여 구현 된 연결 지점](../mfc/media/vc37lh2.gif "vc37lh2")  
MFC를 사용 하 여 구현 하는 연결 지점  
  
 일반적으로 연결점 지원 "멀티 캐스팅" — 동일한 인터페이스에 연결 된 여러 개의 싱크를 브로드캐스트하는 기능입니다. 다음 예제에서는 부분을 보여 줍니다. 각 싱크는 연결 지점에서 반복 하 여 멀티 캐스트 하는 방법:  
  
 [!code-cpp[NVC_MFCConnectionPoints#4](../mfc/codesnippet/cpp/connection-points_4.cpp)]  
  
 연결의 현재 집합을 검색 하는이 예제는 `SampleConnPt` 연결점을 호출 하 여 `CConnectionPoint::GetConnections`합니다. 연결 및 호출을 반복 **ISampleSink::SinkFunc** 모든 활성 연결 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC COM](../mfc/mfc-com.md)

