---
title: 'MFC ActiveX 컨트롤: 글꼴 사용 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- OnFontChanged
- HeadingFont
- InternalFont
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], MFC ActiveX controls fonts
- OnDraw method, MFC ActiveX controls
- InternalFont method [MFC]
- SetFont method [MFC]
- OnFontChanged method [MFC]
- IPropertyNotifySink class [MFC]
- MFC ActiveX controls [MFC], fonts
- Stock Font property [MFC]
- HeadingFont property [MFC]
- GetFont method [MFC]
- SelectStockFont method [MFC]
- fonts [MFC], ActiveX controls
ms.assetid: 7c51d602-3f5a-481d-84d1-a5d8a3a71761
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7f5d1475412de736970d0ae36a39540121bfbc01
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930717"
---
# <a name="mfc-activex-controls-using-fonts"></a>MFC ActiveX 컨트롤: 글꼴 사용
텍스트를 표시 하는 ActiveX 컨트롤 글꼴 속성을 변경 하 여 텍스트 모양을 변경 하려면 컨트롤 사용자를 허용할 수 있습니다. 글꼴 속성 글꼴 개체로 구현 되 고 두 가지 형식 중 하나일 수 있습니다: 주식 또는 사용자 지정 합니다. 스톡 글꼴 속성은 속성 추가 마법사를 사용 하 여 추가할 수 있는 미리 글꼴 속성입니다. 사용자 지정 글꼴 속성은 하지 미리 및 속성의 동작과 사용 컨트롤 개발자가 결정 합니다.  
  
 이 문서에서는 다음 항목을 다룹니다.  
  
-   [스톡 글꼴 속성을 사용 하 여](#_core_using_the_stock_font_property)  
  
-   [컨트롤에서 사용자 지정 글꼴 속성을 사용 하 여](#_core_implementing_a_custom_font_property)  
  
##  <a name="_core_using_the_stock_font_property"></a> 스톡 글꼴 속성을 사용 하 여  
 클래스에 의해 스톡 글꼴 속성은 미리 [COleControl](../mfc/reference/colecontrol-class.md)합니다. 또한 표준 글꼴 속성 페이지를 사용할 수 있는 사용자가 font 개체 이름, 크기, 스타일 등의 다양 한 특성을 변경할 수 있도록 이기도 합니다.  
  
 Font 개체를 통해 액세스는 [GetFont](../mfc/reference/colecontrol-class.md#getfont), [SetFont](../mfc/reference/colecontrol-class.md#setfont), 및 [InternalGetFont](../mfc/reference/colecontrol-class.md#internalgetfont) 의 기능 `COleControl`합니다. 컨트롤 사용자가 글꼴 개체를 통해 액세스할는 `GetFont` 및 `SetFont` 동일한 방식으로 다른 Get/Set 속성의 함수입니다. Font 개체에 대 한 액세스 컨트롤 내에서 필요한 경우 사용 된 `InternalGetFont` 함수입니다.  
  
 에 설명 된 대로 [MFC ActiveX 컨트롤: 속성](../mfc/mfc-activex-controls-properties.md), 스톡 속성 추가 되어 쉽게는 [속성 추가 마법사](../ide/names-add-property-wizard.md)합니다. Font 속성을 선택 하 고 속성 추가 마법사는 컨트롤에 스톡 글꼴 항목을 자동으로 삽입 합니다.  
  
#### <a name="to-add-the-stock-font-property-using-the-add-property-wizard"></a>속성 추가 마법사를 사용 하 여 스톡 글꼴 속성을 추가 하려면  
  
1.  컨트롤의 프로젝트를 로드합니다.  
  
2.  클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.  
  
3.  컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.  
  
4.  바로 가기 메뉴에서 클릭 **추가** 클릭 하 고 **속성 추가**합니다.  
  
     속성 추가 마법사가 열립니다.  
  
5.  에 **속성 이름** 상자 **글꼴**합니다.  
  
6.  **마침**을 클릭합니다.  
  
 속성 추가 마법사 컨트롤 클래스 구현 파일에 있는 컨트롤의 디스패치 맵에 다음 줄을 추가 합니다.  
  
 [!code-cpp[NVC_MFC_AxFont#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_1.cpp)]  
  
 또한 속성 추가 마법사는 컨트롤에 다음 줄을 추가합니다. IDL 파일:  
  
 [!code-cpp[NVC_MFC_AxFont#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_2.idl)]  
  
 주식 Caption 속성은 스톡 글꼴 속성 정보를 사용 하 여 그릴 수 있는 텍스트 속성의 예입니다. 스톡 글꼴 속성에 사용 되는 것과 유사한 단계를 사용 컨트롤에 스톡 Caption 속성을 추가 합니다.  
  
#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>스톡 속성 추가 마법사를 사용 하 여 Caption 속성을 추가 하려면  
  
1.  컨트롤의 프로젝트를 로드합니다.  
  
2.  클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.  
  
3.  컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.  
  
4.  바로 가기 메뉴에서 클릭 **추가** 클릭 하 고 **속성 추가**합니다.  
  
     속성 추가 마법사가 열립니다.  
  
5.  에 **속성 이름** 상자 **캡션**합니다.  
  
6.  **마침**을 클릭합니다.  
  
 속성 추가 마법사 컨트롤 클래스 구현 파일에 있는 컨트롤의 디스패치 맵에 다음 줄을 추가 합니다.  
  
 [!code-cpp[NVC_MFC_AxFont#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_3.cpp)]  
  
##  <a name="_core_modifying_the_ondraw_function"></a> OnDraw 함수 수정  
 기본 구현은 `OnDraw` Windows 시스템 글꼴을 사용 하 여 모든 텍스트 컨트롤에 표시 합니다. 이 수정 해야 한다는 의미는 `OnDraw` 장치 컨텍스트로 font 개체를 선택 하 여 코드입니다. 이 작업을 수행 하려면 호출 [COleControl::SelectStockFont](../mfc/reference/colecontrol-class.md#selectstockfont) 다음 예제와 같이 컨트롤의 장치 컨텍스트를 전달 합니다.  
  
 [!code-cpp[NVC_MFC_AxFont#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_4.cpp)]  
  
 이후에 `OnDraw` 함수 font 개체를 사용 하도록 수정 되었습니다, 컨트롤 내에서 모든 텍스트 컨트롤의 스톡 글꼴 속성에서 특성으로 표시 됩니다.  
  
##  <a name="_core_using_custom_font_properties_in_your_control"></a> 컨트롤에서 사용자 지정 글꼴 속성을 사용 하 여  
 스톡 글꼴 속성 외에 ActiveX 컨트롤에는 사용자 지정 글꼴 속성이 있을 수 있습니다. 사용자 지정 글꼴 속성을 추가 하려면 다음을 수행 해야 합니다.  
  
-   속성 추가 마법사를 사용 하 여 사용자 지정 글꼴 속성을 구현 합니다.  
  
-   [글꼴 알림 처리](#_core_processing_font_notifications)합니다.  
  
-   [새 글꼴 알림 인터페이스 구현](#_core_implementing_a_new_font_notification_interface)합니다.  
  
###  <a name="_core_implementing_a_custom_font_property"></a> 사용자 지정 글꼴 속성 구현  
 사용자 지정 글꼴 속성을 구현 하려면 속성을 추가 하 고 코드에 약간의 수정 후에 속성 추가 마법사를 사용 합니다. 다음 섹션에서는 사용자 지정을 추가 하는 방법에 설명 `HeadingFont` 샘플 컨트롤에는 속성입니다.  
  
##### <a name="to-add-the-custom-font-property-using-the-add-property-wizard"></a>속성 추가 마법사를 사용 하 여 사용자 지정 글꼴 속성을 추가 하려면  
  
1.  컨트롤의 프로젝트를 로드합니다.  
  
2.  클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.  
  
3.  컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.  
  
4.  바로 가기 메뉴에서 클릭 **추가** 클릭 하 고 **속성 추가**합니다.  
  
     속성 추가 마법사가 열립니다.  
  
5.  에 **속성 이름** 상자는 속성에 대 한 이름을 입력 합니다. 이 예제에서는 **HeadingFont**합니다.  
  
6.  **구현 형식**에서 **Get/Set 메서드**를 클릭합니다.  
  
7.  에 **속성 형식** 상자 **IDispatch\***  속성의 형식에 대 한 합니다.  
  
8.  **마침**을 클릭합니다.  
  
 속성 추가 마법사에 추가 하는 코드 만듭니다는 `HeadingFont` 사용자 지정 속성을는 `CSampleCtrl` 클래스 및 샘플. IDL 파일입니다. 때문에 `HeadingFont` Get/Set 속성 형식인 속성 추가 마법사는 `CSampleCtrl` 는 DISP_PROPERTY_EX_ID 포함 하도록 클래스의 디스패치 맵[DISP_PROPERTY_EX](../mfc/reference/dispatch-maps.md#disp_property_ex) 매크로 항목:  
  
 [!code-cpp[NVC_MFC_AxFont#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_5.cpp)]  
  
 DISP_PROPERTY_EX 매크로 연결는 `HeadingFont` 속성 이름을 해당 `CSampleCtrl` 클래스 Get 및 Set 메서드, `GetHeadingFont` 및 `SetHeadingFont`합니다. 속성 값의 형식은 지정 합니다. 이 경우 VT_FONT입니다.  
  
 속성 추가 마법사는 또한 선언이 컨트롤 헤더 파일에 추가 (합니다. H)에 `GetHeadingFont` 및 `SetHeadingFont` 함수 및 해당 함수 템플릿 컨트롤 구현 파일에 추가 (합니다. CPP):  
  
 [!code-cpp[NVC_MFC_AxFont#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_6.cpp)]  
  
 마지막으로 속성 추가 마법사는 컨트롤을 수정합니다. 에 대 한 항목을 추가 하 여 IDL 파일에서 `HeadingFont` 속성:  
  
 [!code-cpp[NVC_MFC_AxFont#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_7.idl)]  
  
### <a name="modifications-to-the-control-code"></a>제어 코드를 수정  
 이제를 추가한 후는 `HeadingFont` 컨트롤에 속성을 완벽 하 게 새 속성을 지원 하려면 컨트롤 헤더 파일과 구현 파일에 일부 변경 내용을 확인 해야 합니다.  
  
 컨트롤 헤더 파일에 (합니다. H) 보호 된 멤버 변수의 다음 선언을 추가 합니다.  
  
 [!code-cpp[NVC_MFC_AxFont#8](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_8.h)]  
  
 컨트롤 구현 파일에서 (합니다. CPP)에서 다음을 수행 합니다.  
  
-   초기화 *m_fontHeading* 제어 생성자에서 합니다.  
  
     [!code-cpp[NVC_MFC_AxFont#9](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_9.cpp)]  
  
-   글꼴의 기본 특성을 포함 하는 정적 FONTDESC 구조체를 선언 합니다.  
  
     [!code-cpp[NVC_MFC_AxFont#10](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_10.cpp)]  
  
-   컨트롤에서 `DoPropExchange` 멤버 함수를 호출을 추가 `PX_Font` 함수입니다. 초기화 및 지 속성 사용자 지정 글꼴 속성을 제공합니다.  
  
     [!code-cpp[NVC_MFC_AxFont#11](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_11.cpp)]  
  
-   컨트롤을 구현 완료 `GetHeadingFont` 멤버 함수입니다.  
  
     [!code-cpp[NVC_MFC_AxFont#12](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_12.cpp)]  
  
-   컨트롤을 구현 완료 `SetHeadingFont` 멤버 함수입니다.  
  
     [!code-cpp[NVC_MFC_AxFont#13](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_13.cpp)]  
  
-   해당 컨트롤의 `OnDraw` 멤버 함수를 정의 이전에 선택한 글꼴을 보유할 변수로 대체 합니다.  
  
     [!code-cpp[NVC_MFC_AxFont#14](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_14.cpp)]  
  
-   해당 컨트롤의 `OnDraw` 멤버 함수는 글꼴에 사용할 경우 언제 든 지 다음 줄을 추가 하 여 장치 컨텍스트로 사용자 지정 글꼴을 선택 합니다.  
  
     [!code-cpp[NVC_MFC_AxFont#15](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_15.cpp)]  
  
-   해당 컨트롤의 `OnDraw` 멤버 함수를 글꼴 사용 된 후에 다음 줄을 추가 하 여 디바이스 컨텍스트로 다시 이전 글꼴을 선택 합니다.  
  
     [!code-cpp[NVC_MFC_AxFont#16](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_16.cpp)]  
  
 사용자 지정 글꼴 속성을 구현한 후 컨트롤의 현재 글꼴을 변경 하려면 사용자가 컨트롤을 표준 Font 속성 페이지 구현 되어야 합니다. 표준 Font 속성 페이지에 대 한 속성 페이지 ID를 추가 하려면 BEGIN_PROPPAGEIDS 매크로 뒤에 다음 줄을 삽입 합니다.  
  
 [!code-cpp[NVC_MFC_AxFont#17](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_17.cpp)]  
  
 또한 BEGIN_PROPPAGEIDS 매크로의 count 매개 변수 1 씩 증가 시켜야 합니다. 다음 줄에서는 이 작업을 보여 줍니다.  
  
 [!code-cpp[NVC_MFC_AxFont#18](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_18.cpp)]  
  
 이러한 변경 내용을 적용 된 후 추가 기능을 포함 하도록 전체 프로젝트를 다시 작성 합니다.  
  
###  <a name="_core_processing_font_notifications"></a> 글꼴 알림 처리  
 대부분의 경우에서 컨트롤 font 개체의 특성 최근에 수정 되었다면 알고 있어야 합니다. 각 font 개체는 수의 멤버 함수를 호출 하 여 변경 될 때 알림을 제공 하는 `IFontNotification` 에서 구현 된 인터페이스 `COleControl`합니다.  
  
 해당 알림을 처리 하는 컨트롤 스톡 글꼴 속성을 사용할 경우의 `OnFontChanged` 의 멤버 함수 `COleControl`합니다. 사용자 지정 글꼴 속성을 추가 하면 동일한 구현을 사용 되도록 할 수 있습니다. 이전 섹션의 예제에서는이 작업을 수행 했습니다 전달 하 여 &*m_xFontNotification* 초기화할 때는 *m_fontHeading* 멤버 변수입니다.  
  
 ![여러 글꼴 개체 인터페이스 구현](../mfc/media/vc373q1.gif "vc373q1")  
여러 글꼴 개체 인터페이스 구현  
  
 위 그림에서는 실선 글꼴 두 개체를 모두의 동일한 구현을 사용 하는 표시 `IFontNotification`합니다. 글꼴 변경 구분 하려는 경우이 인해 문제가 발생할 수 있습니다.  
  
 컨트롤의 글꼴 개체 알림 간을 서로 구별 하는 한 가지 방법은 별도의 구현을 만드는 것은 `IFontNotification` 컨트롤에서 각 font 개체에 대 한 인터페이스입니다. 이 기법을 사용 하면 문자열 또는 최근에 수정 된 글꼴을 사용 하는 문자열을 업데이트 하 여 그리기 코드를 최적화할 수 있습니다. 다음 섹션에서는 두 번째 Font 속성에 대 한 별도 알림 인터페이스를 구현 하는 데 필요한 단계를 보여 줍니다. 두 번째 font 속성으로 간주 됩니다는 `HeadingFont` 이전 섹션에 추가 된 속성입니다.  
  
###  <a name="_core_implementing_a_new_font_notification_interface"></a> 새 글꼴 알림 인터페이스 구현  
 여러 글꼴 알림의 구분 하기 위해 컨트롤에서 사용 되는 각 글꼴에 대 한 새 알림 인터페이스를 구현 합니다. 다음 섹션에서는 컨트롤 헤더와 구현 파일을 수정 하 여 새 글꼴 알림 인터페이스를 구현 하는 방법에 설명 합니다.  
  
### <a name="additions-to-the-header-file"></a>헤더 파일에 대 한 추가  
 컨트롤 헤더 파일에 (합니다. H), 클래스 선언에 다음 줄을 추가 합니다.  
  
 [!code-cpp[NVC_MFC_AxFont#19](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_19.h)]  
  
 이렇게 하면 구현을 만들어집니다는 `IPropertyNotifySink` 이라는 인터페이스 `HeadingFontNotify`합니다. 라는 메서드를 포함 하는이 새 인터페이스 `OnChanged`합니다.  
  
### <a name="additions-to-the-implementation-file"></a>구현 파일에 대 한 추가  
 (제어 생성자)에서 제목 글꼴을 초기화 하는 코드에서 변경 &*m_xFontNotification* 를 &*m_xHeadingFontNotify*합니다. 다음 코드를 추가 합니다.  
  
 [!code-cpp[NVC_MFC_AxFont#20](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_20.cpp)]  
  
 `AddRef` 및 `Release` 의 메서드는 `IPropertyNotifySink` 인터페이스에는 ActiveX 컨트롤 개체에 대 한 참조 횟수를 추적 계속 합니다. 인터페이스 포인터에 대 한 액세스 권한을 갖게 하는 컨트롤, 컨트롤 호출 `AddRef` 참조 수를 증가 합니다. 호출 컨트롤 포인터로 완료 되 면 `Release`, 훨씬 같은 방식으로 `GlobalFree` 전역 메모리 블록을 호출할 수 있습니다. 이 인터페이스에 대 한 참조 횟수를 0이 되 면 인터페이스 구현을 해제할 수 있습니다. 이 예제에서는 `QueryInterface` 함수 반환에 대 한 포인터는 `IPropertyNotifySink` 특정 개체에 대 한 인터페이스입니다. 이 함수에는 ActiveX 컨트롤을을 지 원하는 인터페이스를 결정 하는 개체를 쿼리할 수 있습니다.  
  
 이러한 변경이 프로젝트에 적용 된 후 프로젝트를 다시 작성 하 고 테스트 컨테이너를 사용 하 여 인터페이스를 테스트 합니다. 테스트 컨테이너에 액세스하는 방법은 [테스트 컨테이너로 속성 및 이벤트 테스트](../mfc/testing-properties-and-events-with-test-container.md) 를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX 컨트롤: ActiveX 컨트롤에서 그림 사용](../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)   
 [MFC ActiveX 컨트롤: 스톡 속성 페이지 사용](../mfc/mfc-activex-controls-using-stock-property-pages.md)

