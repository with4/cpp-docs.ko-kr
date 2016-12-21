---
title: "이벤트 추가(ATL 자습서, 5부) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
ms.assetid: 2de12022-3148-4ce3-8606-8a9d4274f0e9
caps.latest.revision: 13
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 이벤트 추가(ATL 자습서, 5부)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

추가이 단계에는 `ClickIn` 와 `ClickOut` ATL 컨트롤에 이벤트.  발생 하는 `ClickIn` 다각형 및 화재를 클릭할 경우 이벤트 `ClickOut` 외부를 클릭할 경우.  이벤트를 추가 하는 작업은 다음과 같습니다.  
  
-   추가 된 `ClickIn` 및 `ClickOut` 메서드  
  
-   형식 라이브러리를 생성합니다.  
  
-   연결 지점 인터페이스 구현  
  
## ClickIn 및 ClickOut 메서드 추가  
 2 단계에서 ATL 컨트롤을 만들 때 선택한의  **연결점** 확인란을 선택 합니다.  만든이 `_IPolyCtlEvents` Polygon.idl 파일에 대 한 인터페이스.  인터페이스 이름이 밑줄로 시작 하는 참고.  이 인터페이스는 내부 인터페이스 임을 표시 하는 규칙입니다.  따라서 COM 개체를 찾는 데 사용할 수 있는 프로그램 인터페이스를 사용자에 게 표시 하지 않도록 선택할 수 있습니다.  또한 해당 선택 참고  **연결점** 나타내기 위해 Polygon.idl 파일에 다음 줄을 추가 `_IPolyCtlEvents` 기본 소스 인터페이스입니다.  
  
 `[default, source] dispinterface _IPolyCtlEvents;`  
  
 컨트롤 알림, 소스 이므로 컨테이너에서이 인터페이스를 호출 합니다 원본 특성을 나타냅니다.  
  
 이제 추가 `ClickIn` 및 `ClickOut` 메서드에 `_IPolyCtlEvents` 인터페이스.  
  
#### ClickIn 및 ClickOut 메서드를 추가 하려면  
  
1.  다각형 및 PolygonLib \_ipolyctlevents를 표시 하려면 클래스 뷰를 확장 합니다.  
  
2.  \_Ipolyctlevents를 마우스 오른쪽 단추로 클릭 합니다.  바로 가기 메뉴에서 **추가**를 클릭한 다음 **메서드 추가**를 클릭합니다.  
  
3.  선택 된  **반환 형식이** 의 `void`.  
  
4.  입력  `ClickIn` 에 있는  **메서드 이름** 상자 합니다.  
  
5.  아래  **매개 변수**선택의  **에서** 상자 합니다.  
  
6.  선택은  **매개 변수 형식** 은 의 `LONG`.  
  
7.  형식  `x` 으로  **매개 변수 이름**를 클릭 하 고  **추가**.  
  
8.  반복 단계 5\-7,이 시간에는  **매개 변수 이름** 은  의  `y`.  
  
9. **다음**을 클릭합니다.  
  
10. 형식  `ClickIn 메서드` 으로  **helpstring**.  
  
11. **마침**을 클릭합니다.  
  
12. 정의 하려면 위의 단계를 반복 하는 `ClickOut` 메서드와 동일한 `LONG` 매개 변수 `x` 및 `y`, 동일한  **매개 변수 특성** 와 같은 `void` 반환 형식이.  
  
 확인 코드에 추가 되었는지 확인 하려면 Polygon.idl 파일의 `_IPolyCtlEvents` dispinterface를.  
  
 `_IPolyCtlEvents` Polygon.idl 파일에서 dispinterface 해야 이제 모양은:  
  
 [!code-cpp[NVC_ATL_Windowing#56](../atl/codesnippet/CPP/adding-an-event-atl-tutorial-part-5_1.idl)]  
  
 `ClickIn` 및 `ClickOut` 메서드는 x와 클릭 한 지점의 y 좌표를 매개 변수로 합니다.  
  
## 형식 라이브러리를 생성합니다.  
 연결 지점 마법사가 컨트롤의 연결 지점 컨테이너 인터페이스와 연결 지점 인터페이스를 생성 하는 데 필요한 정보를 가져오는 데 사용할 수 있기 때문에 시점에서 형식 라이브러리를 생성 합니다.  
  
#### 형식 라이브러리를 생성.  
  
1.  프로젝트를 다시 빌드해야 합니다.  
  
     또는  
  
2.  솔루션 탐색기에서 Polygon.idl 파일을 마우스 오른쪽 단추로 클릭  **컴파일** 바로 가기 메뉴에서.  
  
 형식 라이브러리의 Polygon.tlb 파일을 만듭니다.  이진 파일인 및 없습니다 수 보거나 직접 편집할 수 있기 때문에는 Polygon.tlb 파일을 솔루션 탐색기에서 표시 되지 않습니다.  
  
## 연결 지점 인터페이스 구현  
 컨트롤에 대 한 연결 지점 컨테이너 인터페이스와 연결 지점 인터페이스를 구현 합니다.  COM에서 이벤트의 연결 지점 메커니즘을 통해 구현 됩니다.  COM 개체에서 이벤트를 수신 하려면 컨테이너 COM 개체가 구현 하는 연결 지점에서 advise 연결을 설정 합니다.  COM 개체는 여러 연결 지점을 가질 수 있기 때문에 COM 개체는 또한 연결 지점 컨테이너 인터페이스를 구현 합니다.  이 인터페이스를 통해 컨테이너 어느 연결 지점이 지원 되는지 확인할 수 있습니다.  
  
 연결 지점을 구현 하는 인터페이스 라고 `IConnectionPoint`, 연결 지점 컨테이너를 구현 하는 인터페이스를 호출 하 고 `IConnectionPointContainer`.  
  
 구현할 수 있도록 `IConnectionPoint`, 연결 지점 구현 마법사를 사용 합니다.  이 마법사에서 생성 하는 `IConnectionPoint` 형식 라이브러리를 읽고 발생할 수 있는 각 이벤트에 대 한 함수를 구현 하는 인터페이스입니다.  
  
#### 연결 지점 구현 마법사를 사용.  
  
1.  클래스 뷰에서 컨트롤의 구현 클래스를 마우스 오른쪽 단추로 클릭 `CPolyCtl`.  
  
2.  바로 가기 메뉴에서  **추가**를 누른 다음  **연결 지점 추가**.  
  
3.  선택 `_IPolyCtlEvents` 에서  **원본 인터페이스** 나열 하 고 추가 두 번 클릭의  **연결 지점 구현** 열.  **마침**을 클릭합니다.  연결 지점에 대 한 프록시 클래스를이 경우에 생성 됩니다 `CProxy_IPolyCtlEvents`.  
  
 솔루션 탐색기에서 생성 된 \_IPolyCtlEvents\_CP.h 파일을 살펴보면 라는 클래스 있는지 볼 수 `CProxy_IPolyCtlEvents` 에서 파생 된 `IConnectionPointImpl`.  \_Ipolyctlevents\_cp.h에도 두 메서드 정의 `Fire_ClickIn` 및 `Fire_ClickOut`, 두 좌표 매개 변수를 사용 합니다.  컨트롤에서 이벤트를 발생 시키는 경우이 메서드를 호출 합니다.  
  
 또한 추가 마법사 `CProxy_PolyEvents` 및 `IConnectionPointContainerImpl` 컨트롤의 다중 상속 목록에.  또한 노출 마법사 `IConnectionPointContainer` COM 맵에 해당 엔트리를 추가 하 여.  
  
 이벤트를 지 원하는 코드 구현을 완료 됩니다.  이제 적절 한 시점에 이벤트를 발생 시키려면 일부 코드를 추가 합니다.  기억, 이동 하는 `ClickIn` 또는 `ClickOut` 이벤트는 컨트롤에서 마우스 왼쪽된 단추를 클릭할 때.  확인 단추를 클릭할 때 추가 대 한 처리기를 `WM_LBUTTONDOWN` 메시지.  
  
#### WM\_LBUTTONDOWN 메시지에 대 한 처리기를 추가 하려면  
  
1.  클래스 뷰에서 CPolyCtl 클래스를 마우스 오른쪽 단추로 클릭 하 고  **속성** 바로 가기 메뉴에서.  
  
2.  에  **속성** 창에서 클릭은  **메시지** 아이콘 클릭 하 고 `WM_LBUTTONDOWN` 왼쪽 목록에서.  
  
3.  드롭다운 목록에서 클릭  **\<Add\> OnLButtonDown**.  `OnLButtonDown` 처리기 선언 Polyctl.h를 추가 하 고 처리기 구현 Polyctl.cpp에 추가 됩니다.  
  
 그런 다음 처리기를 수정 합니다.  
  
#### OnLButtonDown 메서드를 수정.  
  
1.  구성 하는 코드를 변경의 `OnLButtonDown` PolyCtl.cpp \(코드 마법사에 의해 삭제\) 메서드에서 다음과 같이 되도록:  
  
     [!code-cpp[NVC_ATL_Windowing#57](../atl/codesnippet/CPP/adding-an-event-atl-tutorial-part-5_2.cpp)]  
  
 점 사용 계산에서이 코드를 통해의 `OnDraw` 사용자의 마우스 클릭 호출로 감지 영역을 만드는 기능 `PtInRegion`.  
  
 `uMsg` 매개 변수는 처리할 Windows 메시지의 ID입니다.  이 메시지를 처리 하는 함수가 있을 수 있습니다.  `wParam` , `lParam` 매개 변수는 처리 중인 메시지에 대 한 표준 값입니다.  매개 변수 bHandled 함수는 메시지 처리 여부를 지정할 수 있습니다.  기본적으로 값 설정 `TRUE` 함수는 메시지 처리 후 설정할 수 있습니다 나타낼 수 `FALSE`.  그러면 ATL 계속 메시지를 보낼 다른 메시지 처리기 함수를 찾습니다.  
  
## 빌드 및 컨트롤 테스트  
 이제 이벤트를 시험해 봅니다.  컨트롤을 빌드하고 ActiveX 컨트롤 테스트 컨테이너를 다시 시작 합니다.  이 이번에는 이벤트 로그 창을 봅니다.  출력 창에 이벤트를 보내려면 클릭  **로깅** 에서  **옵션** 메뉴 및 선택  **로그 출력 창에**.  컨트롤을 삽입 하 고 창에서 클릭 하십시오.  이때 `ClickIn` 안에 채워진된 다각형을 클릭 하면 발생 하는 및 `ClickOut` 외부에서 클릭할 때 발생 합니다.  
  
 그런 다음 속성 페이지를 추가 합니다.  
  
 [다시 단계 4](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) &#124; [6 단계](../atl/adding-a-property-page-atl-tutorial-part-6.md)  
  
## 참고 항목  
 [자습서](../atl/active-template-library-atl-tutorial.md)