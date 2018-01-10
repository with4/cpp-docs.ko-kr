---
title: "그래픽 개체를 선택 하 여 장치 컨텍스트로 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- graphic objects [MFC], selecting into device context
- SelectObject method [MFC]
- GDI objects [MFC], device contexts
- lifetime, graphic objects [MFC]
- device contexts, selecting graphic objects into
- device contexts, graphic objects [MFC]
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5909625b816deb1303821aaec4034fa24f29be5f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="selecting-a-graphic-object-into-a-device-context"></a>그래픽 개체를 선택하여 장치 컨텍스트로 넣기
이 항목 창 디바이스 컨텍스트에서 그래픽 개체를 사용 하 여에 적용 됩니다. 후 [그리기 개체를 만들](../mfc/one-stage-and-two-stage-construction-of-objects.md), 여기에 저장 된 기본 개체 대신 장치 컨텍스트로 선택 해야 합니다.  
  
 [!code-cpp[NVC_MFCDocViewSDI#7](../mfc/codesnippet/cpp/selecting-a-graphic-object-into-a-device-context_1.cpp)]  
  
## <a name="lifetime-of-graphic-objects"></a>그래픽 개체의 수명  
 반환 되는 그래픽 개체 [SelectObject](../mfc/reference/cdc-class.md#selectobject) "임시"입니다. 에 의해 삭제 됩니다, 즉는 [OnIdle](../mfc/reference/cwinapp-class.md#onidle) 클래스의 멤버 함수 `CWinApp` 다음에 프로그램이 가져옵니다 유휴 시간입니다. 반환 되는 개체를 사용 하 여으로 `SelectObject` 제어 기본 메시지 루프를 반환 하지 않고는 단일 함수에서 아무런 문제가 해야 합니다.  
  
### <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [그래픽 개체](../mfc/graphic-objects.md)  
  
-   [1 단계 및 2 단계 그래픽 개체 생성](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [장치 컨텍스트](../mfc/device-contexts.md)  
  
-   [뷰에 그리기](../mfc/drawing-in-a-view.md)  
  
## <a name="see-also"></a>참고 항목  
 [그래픽 개체](../mfc/graphic-objects.md)

