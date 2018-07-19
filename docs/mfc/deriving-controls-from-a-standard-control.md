---
title: 표준 컨트롤에서 컨트롤 파생 시키기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- standard controls [MFC], deriving controls from
- common controls [MFC], deriving from
- derived controls
- controls [MFC], derived
- Windows common controls [MFC], deriving from
- standard controls
ms.assetid: a6f84315-7007-4e0e-8576-78be81254802
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d4ae7fb09e1f453b6d7bc82a7fb038567809f872
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932249"
---
# <a name="deriving-controls-from-a-standard-control"></a>표준 컨트롤에서 컨트롤 파생시키기
마찬가지로 [CWnd](../mfc/reference/cwnd-class.md)-파생 클래스를 기존 컨트롤 클래스에서 새 클래스를 파생 하 여 컨트롤의 동작을 수정할 수 있습니다.  
  
### <a name="to-create-a-derived-control-class"></a>파생된 컨트롤 클래스를 만들려면  
  
1.  기존 컨트롤 클래스에서 클래스를 파생 하 고 필요에 따라 재정의 `Create` 멤버 함수는 기본 클래스에 필요한 인수 제공 되도록 `Create` 함수입니다.  
  
2.  메시지 처리기 멤버 함수 및 특정 Windows 메시지에 대 한 응답으로 컨트롤의 동작을 수정 하는 메시지 맵 항목을 제공 합니다. 참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)합니다.  
  
3.  (선택 사항) 컨트롤의 기능을 확장 하는 새 멤버 함수를 제공 합니다.  
  
 파생된 된 컨트롤을 사용 하 여 대화 상자에서 추가 작업이 필요 합니다. 대화 상자에서 컨트롤의 위치와 형식 대화 상자 템플릿 리소스에서 일반적으로 지정 됩니다. 파생된 컨트롤 클래스를 만들 경우 리소스 컴파일러 파생 된 클래스에 대해 알고 있으므로 대화 상자 템플릿에서 지정할 수 없습니다.  
  
#### <a name="to-place-your-derived-control-in-a-dialog-box"></a>대화 상자에서 파생 된 컨트롤을 배치 하려면  
  
1.  파생 된 대화 상자 클래스의 선언에서 파생 된 컨트롤 클래스의 개체를 포함 합니다.  
  
2.  재정의 `OnInitDialog` 멤버 함수를 호출 하 여 대화 상자 클래스에는 `SubclassDlgItem` 파생 컨트롤 멤버 함수입니다.  
  
 `SubclassDlgItem` "동적으로 서브 클래스" 컨트롤이 대화 상자 템플릿에서 생성 합니다. 컨트롤은 동적으로 하위 클래스에서는 있습니다 Windows에 후크를 사용자의 응용 프로그램 내에서 일부 메시지를 처리 다음 Windows에 로그온 할 나머지 메시지를 전달 합니다. 자세한 내용은 참조는 [SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem) 클래스의 멤버 함수 `CWnd` 에 *MFC 참조*합니다. 다음 예제에서는 재정의 작성 하는 방법을 보여 줍니다. `OnInitDialog` 호출할 `SubclassDlgItem`:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#3](../mfc/codesnippet/cpp/deriving-controls-from-a-standard-control_1.cpp)]  
  
 파생된 컨트롤은 대화 상자 클래스에 포함 되므로, 대화 상자를 생성 하 고 대화 상자 소멸 될 때 소멸 됩니다 생성 될 됩니다. 이 코드의 예제를 비교 [컨트롤 By 손 추가](../mfc/adding-controls-by-hand.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컨트롤 만들기 및 사용](../mfc/making-and-using-controls.md)   
 [컨트롤](../mfc/controls-mfc.md)

