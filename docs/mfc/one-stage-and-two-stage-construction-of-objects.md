---
title: 1 단계 및 2 단계 개체 생성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], creating graphic objects
- object creation [MFC], graphic objects
- objects [MFC], graphic objects
- one-stage and two-stage construction of objects [MFC]
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c53f99932887acad4d2eab5c15ed73b66b359fd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="one-stage-and-two-stage-construction-of-objects"></a>1단계 및 2단계 개체 생성
펜과 브러시와 같은 그래픽 개체를 만들기 위한 다음 두 가지 기술 중 하나를 선택을 해야 합니다.  
  
-   *1 단계 생성*: 생성 및 모든는 생성자를 사용 하 여 한 단계에서 개체를 초기화 합니다.  
  
-   *2 단계 생성*: 생성 및 별도의 두 단계로 개체를 초기화 합니다. 생성자는 개체를 만들고 초기화 함수를 초기화 합니다.  
  
 2 단계 생성이 항상 안전 합니다. 1 단계 생성의 생성자에 잘못 된 인수를 제공 하거나 메모리 할당에 실패 하는 경우 예외를 throw 수 없습니다. 오류를 확인 해야 하지만 2 단계 생성 하 여 해당 문제를 금지 합니다. 두 경우 모두 개체를 소멸는 프로세스와 동일 합니다.  
  
> [!NOTE]
>  이러한 기술은 모든 개체 그래픽 개체 뿐 아니라 만들기에 적용 됩니다.  
  
## <a name="example-of-both-construction-techniques"></a>두 가지 방법 모두 생성의 예  
 간단한 다음 예에서는 두 방법 모두 펜 개체 생성을 보여 줍니다.  
  
 [!code-cpp[NVC_MFCDocViewSDI#6](../mfc/codesnippet/cpp/one-stage-and-two-stage-construction-of-objects_1.cpp)]  
  
### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아보려는 항목  
  
-   [그래픽 개체](../mfc/graphic-objects.md)  
  
-   [그래픽 개체를 선택 하 여 장치 컨텍스트로](../mfc/selecting-a-graphic-object-into-a-device-context.md)  
  
-   [장치 컨텍스트](../mfc/device-contexts.md)  
  
-   [뷰에 그리기](../mfc/drawing-in-a-view.md)  
  
## <a name="see-also"></a>참고 항목  
 [그래픽 개체](../mfc/graphic-objects.md)

