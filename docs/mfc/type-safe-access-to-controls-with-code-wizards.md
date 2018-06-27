---
title: 코드 마법사를 사용 하 여 컨트롤에 대 한 형식이 안전한 액세스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DDX (dialog data exchange), access to controls
- code wizards
- dialog boxes [MFC], access to controls
- dialog box controls [MFC], accessing
ms.assetid: b8874393-ee48-4124-8d78-e3648a7e29b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 88f86a8f22bae990261be5150755a26d50d4bef8
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950463"
---
# <a name="type-safe-access-to-controls-with-code-wizards"></a>코드 마법사를 사용하여 컨트롤에 대한 형식이 안전한 액세스 수행
DDX 기능에 익숙한 경우에 컨트롤 속성을 사용할 수 있습니다는 [멤버 변수 추가 마법사](../ide/add-member-variable-wizard.md) 형식이 안전한 액세스를 만들려고 합니다. 이 방법은 코드 마법사를 사용 하지 않고 컨트롤을 만드는 것 보다 쉽습니다.  
  
 컨트롤의 값에 대 한 액세스를 간단히 원하는 DDX이를 제공 합니다. 컨트롤의 값을 액세스 이상을 하려는 멤버 변수 추가 마법사 사용 하 여 대화 상자 클래스에 해당 클래스의 멤버 변수를 추가 합니다. 이 멤버 변수 컨트롤 속성에 연결 합니다.  
  
 멤버 변수 Value 속성 대신 컨트롤 속성을 가질 수 있습니다. Value 속성 형식을 참조와 같은 컨트롤에서 반환 된 데이터의 `CString` 또는 **int**합니다. 컨트롤 속성에 형식이 같은 MFC 컨트롤 클래스 중 하나는 데이터 멤버를 통해 컨트롤에 직접 액세스할 수 있도록 `CButton` 또는 `CEdit`합니다.  
  
> [!NOTE]
>  지정 된 컨트롤에 대 한 있을 수 있습니다, 원하는 경우 Value 속성 및 최대 컨트롤 속성을 가진 하나의 멤버 변수와 함께 여러 멤버 변수. 여러 개체를 컨트롤 또는 다른 창에 연결 된 메시지 맵에 모호성을 초래 하기 때문에 컨트롤에 매핑되어 MFC 개체를 하나만 포함할 수 있습니다.  
  
 모든 멤버 함수를 호출할 컨트롤 개체에 대 한이 개체를 사용할 수 있습니다. 이러한 호출 대화 상자에서 컨트롤을 영향을 줍니다. 예를 들어, 확인란 컨트롤에 대 한 변수에서 나타내는 *m_Checkbox*, 형식의 `CButton`를 호출할 수 있습니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#52](../mfc/codesnippet/cpp/type-safe-access-to-controls-with-code-wizards_1.cpp)]  
  
 멤버 변수 여기 *m_Checkbox* 멤버 함수로 동일한 용도로 사용 `GetMyCheckbox` 에 표시 된 [컨트롤 없이 코드 마법사에 대 한 형식이 안전한 액세스](../mfc/type-safe-access-to-controls-without-code-wizards.md)합니다. 확인란 자동 확인란이 있는 경우 여전히 해야 처리기 BN_CLICKED 컨트롤 알림 메시지에 대 한 대화 상자 클래스에는 단추를 클릭할 때 합니다.  
  
 컨트롤에 대 한 자세한 내용은 참조 [컨트롤](../mfc/controls-mfc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자에서 컨트롤에 대 한 형식이 안전한 액세스](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)   
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)   
 [코드 마법사를 사용하지 않고 컨트롤에 대한 형식이 안전한 액세스 수행](../mfc/type-safe-access-to-controls-without-code-wizards.md)

