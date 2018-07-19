---
title: 속성 시트를 사용 하 여 응용 프로그램에서 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog templates [MFC], property sheets
- dialog resources
- property pages [MFC], property sheets
- DoModal method property sheets
- AddPage method [MFC]
- property sheets, about property sheets
- Create method [MFC], property sheets
- CPropertyPage class [MFC], styles
ms.assetid: 240654d4-152b-4e3f-af7b-44234339206e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74e63faf5b1cac5e0cb841a28fd59ecee47c9970
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383895"
---
# <a name="using-property-sheets-in-your-application"></a>응용 프로그램에서 속성 시트 사용
응용 프로그램에서 속성 시트를 사용 하려면 다음 단계를 수행 합니다.  
  
1.  각 속성 페이지 대화 상자 템플릿 리소스를 만듭니다. 사용자 수로 전환 하 한 페이지에서 다른 레이아웃을 각 페이지와 가능한 일관 되 게 하므로 염두에서에 둬야 합니다.  
  
     모든 페이지에 대 한 대화 상자 템플릿 동일한 크기 일 필요가 없습니다. 프레임 워크는 가장 큰 페이지의 크기를 사용 하 여 속성 페이지에 대 한 속성 시트에 할당할 공간 크기를 결정 합니다.  
  
     속성 페이지 대화 상자 템플릿 리소스를 만들 때 대화 속성 속성 시트에서 다음과 같은 스타일을 지정 해야 합니다.  
  
    -   설정의 **캡션** 편집 상자에는 **일반** 이 페이지에 대 한 탭에 표시할 텍스트를 페이지입니다.  
  
    -   설정의 **스타일** 목록 상자에는 **스타일** 페이징을 **자식**합니다.  
  
    -   설정의 **테두리** 목록 상자에는 **스타일** 페이징을 **Thin**합니다.  
  
    -   확인는 **Titlebar** 확인란은 **스타일** 페이지를 선택 합니다.  
  
    -   확인는 **비활성화 된** 확인란은 **기타 스타일** 페이지를 선택 합니다.  
  
2.  만들기는 [CPropertyPage](../mfc/reference/cpropertypage-class.md)-각 속성 페이지 대화 상자 템플릿에 해당 하는 클래스를 파생 합니다. 참조 [클래스 추가](../ide/adding-a-class-visual-cpp.md)합니다. 선택 `CPropertyPage` 기본 클래스로 합니다.  
  
3.  이 속성 페이지에 대 한 값을 보유할 변수 멤버를 만듭니다. 속성 페이지에 멤버 변수를 추가 하기 위한 프로세스가 같습니다 정확 하 게 대화 상자에 멤버 변수 추가 속성 페이지에는 특수 한 대화 상자 이므로 합니다. 자세한 내용은 참조 [대화 상자 컨트롤에 대 한 멤버 변수 정의](../windows/defining-member-variables-for-dialog-controls.md)합니다.  
  
4.  생성 된 [CPropertySheet](../mfc/reference/cpropertysheet-class.md) 소스 코드에서 개체입니다. 생성 하는 일반적으로 `CPropertySheet` 속성 시트를 표시 하는 명령에 대 한 처리기에서 개체입니다. 이 개체는 전체 속성 시트를 나타냅니다. 모달 속성 시트를 만드는 경우는 [DoModal](../mfc/reference/cpropertysheet-class.md#domodal) 기본적으로 세 명령 단추를 제공 하는 함수, 프레임 워크: 확인, 취소 및 적용. 프레임 워크 사용 하 여 만든 모덜리스 속성 시트에 대 한 명령 단추가 만듭니다는 [만들기](../mfc/reference/cpropertysheet-class.md#create) 함수입니다. 클래스를 파생 해야 `CPropertySheet` (미리 보기 창) 등의 다른 컨트롤을 추가 하거나 모덜리스 속성 시트를 표시 하는 경우가 있습니다. 이 단계는 속성 시트를 사용할 수 있는 모든 기본 컨트롤을 포함 하지 않는 모덜리스 속성 시트의 경우 필요 합니다.  
  
5.  속성 시트에 추가할 각 페이지에서 다음을 수행 합니다.  
  
    -   각각에 대해 하나의 개체를 생성할 `CPropertyPage`-이 프로세스의 앞부분에서 만든 클래스를 파생 합니다.  
  
    -   호출 [CPropertySheet::AddPage](../mfc/reference/cpropertysheet-class.md#addpage) 각 페이지에 대 한 합니다.  
  
     가 만드는 개체 일반적으로 `CPropertySheet` 도 만듭니다는 `CPropertyPage` 이 단계에서는 개체입니다. 그러나 구현 하는 경우는 `CPropertySheet`-파생 클래스를 포함할 수 있습니다는 `CPropertyPage` 개체에 `CPropertySheet` 개체와 호출 `AddPage` 에서 각 페이지에 대 한는 `CPropertySheet`-클래스 생성자를 파생 합니다. `AddPage` 추가 `CPropertyPage` 페이지의 속성 시트의 변수에 개체 이지만 실제로 해당 페이지에 대 한 창을 만들지 않습니다. 따라서 필요한 경우가 아니라면 호출 하는 속성 시트 창 만들 때까지 대기 하도록 `AddPage`; 호출할 수 있습니다 `AddPage` 속성 시트의 생성자에서 합니다.  
  
     기본적으로 속성 시트 속성 시트의 단일 행에 들어가는 것 보다 더 많은 탭에 여러 행에는 탭 스택 됩니다. 호출 스택 사용 하지 않으려면 [CPropertySheet::EnableStackedTabs](../mfc/reference/cpropertysheet-class.md#enablestackedtabs) 로 설정 하는 매개 변수와 함께 **FALSE**합니다. 호출 해야 `EnableStackedTabs` 속성 시트를 만들 때.  
  
6.  호출 [CPropertySheet::DoModal](../mfc/reference/cpropertysheet-class.md#domodal) 또는 [만들기](../mfc/reference/cpropertysheet-class.md#create) 속성 시트를 표시 합니다. 호출 `DoModal` 모달 대화 상자로 속성 시트를 만들려고 합니다. 호출 **만들기** 모덜리스 대화 상자로 속성 시트를 만들려고 합니다.  
  
7.  속성 페이지 및 속성 시트의 소유자 간에 데이터를 교환 합니다. 이 문서에 설명 되어 [데이터 교환](../mfc/exchanging-data.md)합니다.  
  
 속성 시트를 사용 하는 방법의 예를 들어 MFC 일반 샘플을 참조 하십시오. [PROPDLG](../visual-cpp-samples.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 시트](../mfc/property-sheets-mfc.md)

