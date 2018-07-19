---
title: 대화 상자 모음 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, control bars
- CDialogBar class [MFC], dialog bars
- control bars [MFC], dialog bars
- dialog bars
- dialog bars [MFC], about dialog bars
ms.assetid: 485c8055-6bb0-4051-8417-dd2971499321
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c7c68ca2725d25b493003ad7d847176c7dd8d17d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348809"
---
# <a name="dialog-bars"></a>대화 상자 모음
대화 상자 막대는 도구 모음, 한 종류의 [컨트롤 막대](../mfc/control-bars.md) 모든 종류의 컨트롤을 포함할 수 있는 합니다. 모덜리스 대화 상자 특성 있기 때문에 [CDialogBar](../mfc/reference/cdialogbar-class.md) 개체 보다 강력한 도구 모음을 제공 합니다.  
  
 몇 가지 주요 차이점이 있습니다 도구 모음 사이 `CDialogBar` 개체입니다. A `CDialogBar` Visual c + + 대화 상자 편집기로 만들 수 있는 및 모든 종류의 Windows 컨트롤을 포함할 수 있는 대화 상자 템플릿 리소스에서 개체가 만들어집니다. 사용자는 컨트롤에서 컨트롤에 탭 이동할 수 있습니다. 및이를 부모 프레임 창의 일부를 사용 하 여 대화 상자 막대를 정렬 하거나 부모 크기를 조정 하는 경우이를 그대로 둘을 맞춤 스타일을 지정할 수 있습니다. 다음 그림에는 다양 한 컨트롤와 함께 대화 상자 모음을 보여 줍니다.  
  
 ![VC 대화 상자 막대](../mfc/media/vc378t1.gif "vc378t1")  
대화 상자 모음  
  
 작업을 다른 측면에서는 `CDialogBar` 개체는 모덜리스 대화 상자를 사용 하는 데와 같습니다. 대화 상자 편집기를 사용 하 여 디자인 하 고 대화 상자 리소스를 만들어야 합니다.  
  
 대화 상자 막대의 장점 중 하나는 단추 이외의 컨트롤을 포함할 수 있다는입니다.  
  
 사용자 고유의 대화 상자 클래스를 파생 시키는 동안 `CDialog`, 대화 상자 막대에 대 한 사용자 지정 클래스 일반적으로 파생 되지 않습니다. 대화 상자 모음 주 창 및 모든 대화 상자 막대 컨트롤 알림 메시지에 대 한 확장을 같은 **BN_CLICKED** 또는 **EN_CHANGE**, 가로 막대형, 주 창 대화의 부모에 전송 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)   
 [샘플](../visual-cpp-samples.md)

