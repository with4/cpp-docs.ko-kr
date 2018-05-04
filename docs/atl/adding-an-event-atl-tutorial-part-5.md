---
title: 이벤트 (ATL 자습서, 5 부) 추가 | Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 2de12022-3148-4ce3-8606-8a9d4274f0e9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a118cf29546ac8dae2e882d5658b07e3b5e085f6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="adding-an-event-atl-tutorial-part-5"></a>이벤트 추가(ATL 자습서, 5부)
이 단계에서 추가한는 `ClickIn` 및 `ClickOut` ATL 컨트롤에는 이벤트입니다. 발생는 `ClickIn` 다각형 및 화재 내부를 클릭할 경우 이벤트 `ClickOut` 바깥쪽을 클릭할 경우. 이벤트 추가 하려면 작업은 다음과 같습니다.  
  
-   추가 `ClickIn` 및 `ClickOut` 메서드  
  
-   형식 라이브러리를 생성합니다.  
  
-   연결 지점 인터페이스 구현  
  
## <a name="adding-the-clickin-and-clickout-methods"></a>ClickIn 및 ClickOut 메서드 추가  
 2 단계에서 ATL 컨트롤을 만들 때 선택 된 **연결점** 확인란 합니다. 만든이 `_IPolyCtlEvents` 마우스 오른쪽 단추로 Polygon.idl 파일에 대 한 인터페이스입니다. 인터페이스 이름이 밑줄로 시작 하는 참고 합니다. 이 내부 인터페이스는 인터페이스 임을 나타내기 위해 규칙. COM 개체를 검색 하는 수 있는 프로그램를 사용자에 게 인터페이스를 표시 하지 않는 선택할 수 있습니다. 또한 선택 하면 참고 **연결점** 나타내기 위해 마우스 오른쪽 단추로 Polygon.idl 파일에 다음 줄을 추가 `_IPolyCtlEvents` 기본 소스 인터페이스는:  
  
 `[default, source] dispinterface _IPolyCtlEvents;`  
  
 원본 특성은 컨트롤 임을 나타냅니다는 알림의 소스 있도록 컨테이너에서이 인터페이스를 호출 합니다.  
  
 이제 추가 `ClickIn` 및 `ClickOut` 하는 메서드는 `_IPolyCtlEvents` 인터페이스입니다.  
  
#### <a name="to-add-the-clickin-and-clickout-methods"></a>ClickIn 및 ClickOut 메서드를 추가 하려면  
  
1.  클래스 뷰에서 다각형 및 PolygonLib _IPolyCtlEvents 표시 하려면 확장 합니다.  
  
2.  _IPolyCtlEvents를 마우스 오른쪽 단추로 클릭 합니다. 바로 가기 메뉴를 클릭 **추가**, 클릭 하 고 **메서드 추가**합니다.  
  
3.  선택 된 **반환 형식** 의 `void`합니다.  
  
4.  입력 `ClickIn` 에 **메서드 이름** 상자입니다.  
  
5.  **매개 변수 특성**, 선택는 **에** 상자입니다.  
  
6.  선택 된 **매개 변수 형식** 의 `LONG`합니다.  
  
7.  형식 `x` 로 **매개 변수 이름**를 클릭 하 고 **추가**합니다.  
  
8.  5-7,이 시간에 대 한 단계를 반복 하는 **매개 변수 이름** 의 `y`합니다.  
  
9. **다음**을 클릭합니다.  
  
10. 형식 `method ClickIn` 로 **helpstring**합니다.  
  
11. **마침**을 클릭합니다.  
  
12. 정의 하려면 위의 단계를 반복는 `ClickOut` 메서드 같은 `LONG` 매개 변수 `x` 및 `y`, 동일한 **매개 변수 특성** 과 동일한 `void` 형식을 반환 합니다.  
  
 마우스 오른쪽 단추로 Polygon.idl 파일 코드에 추가 된 확인을 확인 하 고 `_IPolyCtlEvents` dispinterface 합니다.  
  
 `_IPolyCtlEvents` dispinterface 마우스 오른쪽 단추로 Polygon.idl 파일에는 이제 다음과 같이 표시 됩니다.  
  
 [!code-cpp[NVC_ATL_Windowing#56](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_1.idl)]  
  
 `ClickIn` 및 `ClickOut` 메서드는 x 매개 변수로 클릭 지점의 y 좌표입니다.  
  
## <a name="generating-the-type-library"></a>형식 라이브러리를 생성합니다.  
 연결 지점 마법사를 사용 하면 연결 지점 인터페이스 및 컨트롤에 대 한 연결 지점 컨테이너 인터페이스를 구성 하는 데 필요한 정보를 얻을 사용 되기 때문에 시점에서 형식 라이브러리를 생성 합니다.  
  
#### <a name="to-generate-the-type-library"></a>형식 라이브러리를 생성 하려면  
  
1.  프로젝트를 다시 빌드하십시오.  
  
     -또는-  
  
2.  솔루션 탐색기에서 마우스 오른쪽 단추로 Polygon.idl 파일을 마우스 오른쪽 단추로 클릭 하 고 클릭 **컴파일** 바로 가기 메뉴.  
  
 이렇게 하면 형식 라이브러리 Polygon.tlb 파일을 만들어집니다. Polygon.tlb 파일은 이진 파일 및 수 보거나 없습니다은 직접 편집할 때문에 솔루션 탐색기에서 표시 되지 않습니다.  
  
## <a name="implementing-the-connection-point-interfaces"></a>연결 지점 인터페이스 구현  
 연결 지점 인터페이스 및 컨트롤에 대 한 연결 지점 컨테이너 인터페이스를 구현 합니다. COM 이벤트 연결 지점의 메커니즘을 통해 구현 됩니다. COM 개체에서 이벤트를 수신 하는 컨테이너는 COM 개체가 구현 연결점에 권장 된 연결을 설정 합니다. COM 개체에는 연결 지점이 여러 개 있을 수 있지만, 때문에 COM 개체는 또한 연결 지점 컨테이너 인터페이스를 구현 합니다. 이 인터페이스를 통해 컨테이너는 연결 지점이 지원 되는지 확인할 수 있습니다.  
  
 연결 지점을 구현 하는 인터페이스를 라고 `IConnectionPoint`, 연결 지점 컨테이너를 구현 하는 인터페이스 라고 하 고 `IConnectionPointContainer`합니다.  
  
 구현할 수 있도록 `IConnectionPoint`, 연결 지점 구현 마법사를 사용 합니다. 이 마법사는 생성 된 `IConnectionPoint` 형식 라이브러리를 읽고 실행 될 수 있는 각 이벤트에 대 한 함수를 구현 하 여 인터페이스입니다.  
  
#### <a name="to-use-the-implement-connection-point-wizard"></a>연결 지점 구현 마법사를 사용 하려면  
  
1.  클래스 뷰에서 컨트롤의 구현 클래스를 마우스 오른쪽 단추로 `CPolyCtl`합니다.  
  
2.  바로 가기 메뉴를 클릭 **추가**, 클릭 하 고 **연결 지점 추가**합니다.  
  
3.  선택 `_IPolyCtlEvents` 에서 **소스 인터페이스** 나열 하 고 두 번 클릭 하 여 추가 된 **연결 지점을 구현** 열입니다. **마침**을 클릭합니다. 연결 지점에 대 한 프록시 클래스 생성 될 경우에 `CProxy_IPolyCtlEvents`합니다.  
  
 솔루션 탐색기에서 생성 된 _IPolyCtlEvents_CP.h 파일을 보면 나타납니다 라는 클래스는 `CProxy_IPolyCtlEvents` 에서 파생 된 `IConnectionPointImpl`합니다. _IPolyCtlEvents_CP.h 정의 두 가지 방법 `Fire_ClickIn` 및 `Fire_ClickOut`, 두 개의 좌표 매개 변수를 사용 하 합니다. 컨트롤에서 이벤트를 발생 시킬 때 이러한 메서드를 호출 합니다.  
  
 또한 추가 마법사 `CProxy_PolyEvents` 및 `IConnectionPointContainerImpl` 컨트롤의 다중 상속 목록에 있습니다. 노출 마법사 `IConnectionPointContainer` COM 맵에서에 적절 한 항목을 추가 하 여 있습니다.  
  
 이벤트를 지 원하는 코드 구현 완료 됩니다. 이제 적절 한 시점에서의 이벤트를 발생 시키는 일부 코드를 추가 합니다. 발생 하는 것을 기억 하십시오는 `ClickIn` 또는 `ClickOut` 이벤트 사용자가 컨트롤에서 마우스 왼쪽된 단추를 클릭 합니다. 추가 대 한 처리기를 확인 하려면 단추를 클릭할 때는 `WM_LBUTTONDOWN` 메시지입니다.  
  
#### <a name="to-add-a-handler-for-the-wmlbuttondown-message"></a>WM_LBUTTONDOWN 메시지에 대 한 처리기를 추가 하려면  
  
1.  클래스 뷰에서 CPolyCtl 클래스를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성** 바로 가기 메뉴.  
  
2.  에 **속성** 창 클릭는 **메시지** 아이콘을 클릭 한 다음 `WM_LBUTTONDOWN` 왼쪽에 있는 목록에서.  
  
3.  표시 되는 드롭다운 목록에서 클릭  **\<추가 > OnLButtonDown**합니다. `OnLButtonDown` 처리기 선언 PolyCtl.h에 추가 되 고 처리기 구현 PolyCtl.cpp에 추가 됩니다.  
  
 처리기를 다음으로 수정 합니다.  
  
#### <a name="to-modify-the-onlbuttondown-method"></a>OnLButtonDown 메서드를 수정 하려면  
  
1.  구성 하는 코드 변경는 `OnLButtonDown` PolyCtl.cpp (마법사로 넣은 코드 삭제)에 대 한 메서드를 다음과 같이:  
  
     [!code-cpp[NVC_ATL_Windowing#57](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_2.cpp)]  
  
 계산 된 점 사용 하 여가 코드는 `OnDraw` 함수를 호출 하는 사용자의 마우스 클릭을 검색 하는 영역을 만들 `PtInRegion`합니다.  
  
 `uMsg` 매개 변수는 처리 되 고 Windows 메시지의 ID입니다. 이 옵션을 사용 하면 메시지의 범위를 처리 하는 하나의 기능이 있을 수 있습니다. `wParam` 및 `lParam` 매개 변수는 처리 중인 메시지에 대 한 표준 값입니다. 매개 변수 bhandled 여부 함수에서 메시지를 처리 하는지 여부를 지정할 수 있습니다. 기본적으로 값 설정 `TRUE` 함수에서 메시지를 처리 하지만를 설정할 수 있습니다를 나타내기 위해 `FALSE`합니다. 이렇게 하면 메시지를 보낼 다른 메시지 처리기 함수를 찾고 있습니다. 계속 하려면는 ATL 합니다.  
  
## <a name="building-and-testing-the-control"></a>빌드 및 컨트롤 테스트  
 이제 이벤트를 시험해 봅니다. 컨트롤을 빌드하고 ActiveX Control Test Container를 다시 시작 합니다. 이 이번에는 이벤트 로그 창을 봅니다. 클릭 이벤트를 출력 창에 라우트하도록 **로깅** 에서 **옵션** 메뉴와 선택 **출력 창에는 로그**합니다. 컨트롤을 삽입 하 고 창에서를 클릭 해 보십시오. 사항에 유의 `ClickIn` 채워진된 다각형 내부를 클릭할 경우 발생 하 고 `ClickOut` 외부 클릭할 때 발생 합니다.  
  
 다음으로, 속성 페이지를 추가 합니다.  
  
 [4 단계를 다시](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) &#124; [6 단계로](../atl/adding-a-property-page-atl-tutorial-part-6.md)  
  
## <a name="see-also"></a>참고 항목  
 [자습서](../atl/active-template-library-atl-tutorial.md)

