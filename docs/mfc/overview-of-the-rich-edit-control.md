---
title: "Rich Edit 컨트롤의 개요 | Microsoft Docs"
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
- rich edit controls [MFC]
ms.assetid: ad589b9f-a3fd-4820-bf1f-6b1965997e68
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bffab7b72e99dc6587f1d2cbff84407949dd374b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="overview-of-the-rich-edit-control"></a>Rich Edit 컨트롤의 개요
> [!IMPORTANT]
>  Rich edit 컨트롤을 사용 하는 대화 상자에서 경우 (응용 프로그램 SDI, MDI, 인지에 관계 없이 대화 상자 기반 또는)를 호출 해야 [AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit) 대화 상자가 표시 되 면 합니다. 이 함수를 호출할 수 있는 일반적인 위치는 프로그램의 `InitInstance` 멤버 함수입니다. 대화 상자를 처음 사용할 때만 표시 하는 각 시간에 대해 호출할 필요가 없습니다. 호출할 필요가 없습니다 `AfxInitRichEdit` 사용 하는 경우 `CRichEditView`합니다.  
  
 Rich edit 컨트롤 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) 텍스트 서식 지정에 대 한 프로그래밍 인터페이스를 제공 합니다. 그러나 응용 프로그램 사용자에 게 형식 지정 작업을 제공 하는 데 필요한 사용자 인터페이스 구성 요소를 구현 해야 합니다. 즉, rich edit 컨트롤 지원 선택한 텍스트의 문자 또는 단락 특성을 변경 합니다. 특성은 문자의 몇 가지 예 굵게, 기울임꼴, 글꼴 패밀리 및 글꼴 크기입니다. 단락 특성의 예로 맞춤, 여백 및 탭 정지를 들 수 있습니다. 그러나 되기 사용자 인터페이스를 제공 하 여 도구 모음 단추, 메뉴 항목 또는 서식 문자 대화 상자. 현재 선택 된 특성에 대 한 서식 있는 편집 컨트롤을 쿼리 하는 함수도 있습니다. 사용 하 여 이러한 함수는 특성에 대 한 현재 설정을 표시 하려면 예를 들어 선택 영역에 굵게 표시 된 문자 특성을 서식 지정 명령이 UI에 확인 표시를 설정 합니다.  
  
 문자 및 단락 서식 지정에 대 한 자세한 내용은 참조 하십시오. [문자 서식](../mfc/character-formatting-in-rich-edit-controls.md) 및 [단락 서식을](../mfc/paragraph-formatting-in-rich-edit-controls.md) 이 항목의 뒷부분에 나오는 합니다.  
  
 서식 있는 편집 작업 및 다중 행 편집 컨트롤 함께 사용 하는 알림 메시지의 거의 모든 컨트롤 지원 합니다. 따라서 응용 프로그램을 이미 사용 하 여 편집 컨트롤 변경 발생할 수 있는 쉽게 풍부한을 사용 하는 컨트롤을 편집 합니다. 추가 메시지 및 알림 기능이 풍부한에 고유한 편집 컨트롤에 액세스 하려면 응용 프로그램을 사용 하도록 설정 합니다. 편집 컨트롤에 대 한 정보를 참조 하십시오. [CEdit](../mfc/reference/cedit-class.md)합니다.  
  
 알림에 대 한 자세한 내용은 참조 하십시오. [서식 있는 편집 컨트롤에서 알림](../mfc/notifications-from-a-rich-edit-control.md) 이 항목의 뒷부분에 나오는 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

