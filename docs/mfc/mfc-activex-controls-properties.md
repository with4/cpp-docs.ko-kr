---
title: 'MFC ActiveX 컨트롤: 속성 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
- properties [MFC]
ms.assetid: b678a53c-0d9e-476f-8aa0-23b80baaba46
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac9d9e4f5e7d777bd147ce36e970e7a30fd875b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-activex-controls-properties"></a>MFC ActiveX 컨트롤: 속성
ActiveX 컨트롤은 컨트롤 컨테이너와 통신 하는 이벤트입니다. 컨테이너를 사용 하 여 메서드 및 속성 컨트롤와 통신할 수 있습니다. 메서드 및 속성은 비슷한 목적으로 사용 중인 각각, 멤버 함수 및 c + + 클래스의 멤버 변수입니다. 속성은 ActiveX 컨트롤의 모든 컨테이너에 노출 되는 데이터 멤버입니다. 자동화 클라이언트 및 ActiveX 컨트롤 컨테이너와 같은 ActiveX 컨트롤을 포함 하는 응용 프로그램에 대 한 한 인터페이스를 제공 합니다.  
  
 속성은 특성이 라고도 합니다.  
  
 ActiveX 컨트롤 메서드에 대 한 자세한 내용은 문서 참조 [MFC ActiveX 컨트롤: 메서드](../mfc/mfc-activex-controls-methods.md)합니다.  
  
 ActiveX 컨트롤 재고와 사용자 지정 메서드 및 속성을 모두 구현할 수 있습니다. 클래스 `COleControl` 스톡 속성에 대 한 구현을 제공 합니다. (스톡 속성 목록이 전체 문서를 참조 하십시오. [MFC ActiveX 컨트롤: 스톡 속성 추가](../mfc/mfc-activex-controls-adding-stock-properties.md).) 개발자가 정의한 사용자 지정 속성, ActiveX 컨트롤에 특별 한 기능을 추가 합니다. 자세한 내용은 참조 [MFC ActiveX 컨트롤: 사용자 지정 속성 추가](../mfc/mfc-activex-controls-adding-custom-properties.md)합니다.  
  
 메서드와 마찬가지로 사용자 지정 및 스톡 속성의 기존 멤버 함수로 속성 및 메서드를 처리 하는 디스패치 맵 구성 된 메커니즘을 통해 사용할 수는 `COleControl` 클래스입니다. 또한 이러한 속성에는 컨트롤에 추가 정보를 전달 하는 개발자가 사용 하는 매개 변수가 있을 수 있습니다.  
  
 다음 문서는 ActiveX 컨트롤 속성을 자세히 설명합니다.  
  
-   [MFC ActiveX 컨트롤: 스톡 속성 추가](../mfc/mfc-activex-controls-adding-stock-properties.md)  
  
-   [MFC ActiveX 컨트롤: 사용자 지정 속성 추가](../mfc/mfc-activex-controls-adding-custom-properties.md)  
  
-   [MFC ActiveX 컨트롤: 고급 속성 구현](../mfc/mfc-activex-controls-advanced-property-implementation.md)  
  
-   [MFC ActiveX 컨트롤: 앰비언트 속성 액세스](../mfc/mfc-activex-controls-accessing-ambient-properties.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)

