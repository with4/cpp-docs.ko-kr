---
title: "MFC ActiveX 컨트롤: 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], methods
ms.assetid: e20271de-6ffa-4ba0-848b-bafe6c9e510c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8e3b343b13118930612e4adfed4c33a65a9e7be8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-methods"></a>MFC ActiveX 컨트롤: 메서드
ActiveX 컨트롤 자체와 해당 제어 컨테이너 간에 통신 하는 이벤트를 발생 시킵니다. 컨테이너는 메서드 및 속성을 사용 하 여 컨트롤과 통신할 수 있습니다. 메서드는 함수 라고도 합니다.  
  
 메서드 및 속성은 자동화 클라이언트 및 ActiveX 컨트롤 컨테이너와 같은 다른 응용 프로그램에서 사용 하기 위해 내보낸된 인터페이스를 제공합니다. ActiveX 컨트롤 속성에 대 한 자세한 내용은 문서 참조 [MFC ActiveX 컨트롤: 속성](../mfc/mfc-activex-controls-properties.md)합니다.  
  
 메서드는 c + + 클래스의 멤버 함수에 용도가 유사 합니다. 두 가지 방법으로 컨트롤을 구현할 수 메서드의: 주식형 및 사용자 지정 합니다. 스톡 이벤트, 메서드 주식 비슷합니다는를 [COleControl](../mfc/reference/colecontrol-class.md) 구현을 제공 합니다. 주식 메서드에 대 한 자세한 내용은 문서 참조 [MFC ActiveX 컨트롤: 스톡 메서드 추가](../mfc/mfc-activex-controls-adding-stock-methods.md)합니다. 개발자가 정의한 사용자 지정 메서드를 컨트롤의 추가 사용자 지정을 허용 합니다. 자세한 내용은 문서 참조 [MFC ActiveX 컨트롤: 사용자 지정 메서드 추가](../mfc/mfc-activex-controls-adding-custom-methods.md)합니다.  
  
 Microsoft Foundation 클래스 라이브러리 (MFC) 주식형 및 사용자 지정 메서드를 지원 하기 위해 컨트롤 수 있는 메커니즘을 구현 합니다. 첫 번째 부분은 클래스 `COleControl`합니다. 파생 된 `CWnd`, `COleControl` 멤버 함수는 모든 ActiveX 컨트롤에 공통 된 스톡 메서드를 지원 합니다. 이 메커니즘의 두 번째 부분은 디스패치 맵입니다. 디스패치 맵 메시지 맵을;에 대해 비슷합니다. 그러나 함수에는 Windows 메시지 ID를 매핑할 대신 디스패치 맵 가상 멤버 함수를를 매핑합니다 IDispatch ID.  
  
 다양 한 방법의 올바르게 지원 하도록 컨트롤에 대 한 동급 디스패치 맵은 선언 해야 합니다. 이 컨트롤 클래스 헤더에 있는 코드의 다음 줄에 의해 수행 됩니다 (합니다. H) 파일:  
  
 [!code-cpp[NVC_MFC_AxUI#13](../mfc/codesnippet/cpp/mfc-activex-controls-methods_1.h)]  
  
 디스패치 맵의 주요 목적은 (예: 컨테이너) 외부 호출자와 메서드를 구현 하는 컨트롤의 클래스의 멤버 함수에서 사용 하는 메서드 이름 간의 관계를 설정 하는 것입니다. 컨트롤의 구현에서 정의 되어야 하는 데 필요한 디스패치 맵와 선언 (합니다. Cpp) 합니다. 다음 코드 줄에 디스패치 맵을 정의합니다.  
  
 [!code-cpp[NVC_MFC_AxUI#14](../mfc/codesnippet/cpp/mfc-activex-controls-methods_2.cpp)]  
[!code-cpp[NVC_MFC_AxUI#15](../mfc/codesnippet/cpp/mfc-activex-controls-methods_3.cpp)]  
  
 사용 하는 경우는 [MFC ActiveX 컨트롤 마법사](../mfc/reference/mfc-activex-control-wizard.md) 프로젝트를 만들려면이 줄 된 자동으로 추가 합니다. MFC ActiveX 컨트롤 마법사, 사용 되지 않은 경우이 코드를 수동으로 추가 해야 있습니다.  
  
 다음 문서 방법이 자세히 설명합니다.  
  
-   [MFC ActiveX 컨트롤: 스톡 메서드 추가](../mfc/mfc-activex-controls-adding-stock-methods.md)  
  
-   [MFC ActiveX 컨트롤: 사용자 지정 메서드 추가](../mfc/mfc-activex-controls-adding-custom-methods.md)  
  
-   [MFC ActiveX 컨트롤: 메서드에서 오류 코드 반환](../mfc/mfc-activex-controls-returning-error-codes-from-a-method.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)

