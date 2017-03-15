---
title: "그리기 코드 변경(ATL 자습서, 4부) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_MIN_CRT 매크로"
ms.assetid: 08ff14e8-aa49-4139-a110-5d071939cf1e
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# 그리기 코드 변경(ATL 자습서, 4부)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기본적으로 사각형 및 텍스트 컨트롤의 그리기 코드를 표시 **PolyCtl**.  이 단계에서는 좀 더 재미 있게 표시 하는 코드가 변경 됩니다.  다음과 같은 작업이 포함 됩니다.  
  
-   헤더 파일 수정  
  
-   수정 된 `OnDraw` 함수  
  
-   다각형 점을 계산할 메서드 추가  
  
-   채우기 색 초기화  
  
## 헤더 파일 수정  
 시작 하는 수학 함수에 대 한 지원을 추가 하 여 `sin` 및 `cos`, 다각형 점을 계산할 및 위치를 저장 하는 배열을 만들어 사용할 수 있습니다.  
  
#### 헤더 파일을 수정 하려면  
  
1.  줄 추가 `#include <math.h>` PolyCtl.h 맨.  파일의 맨 위에 다음과 같습니다.  
  
     [!code-cpp[NVC_ATL_Windowing#47](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_1.cpp)]  
  
2.  다각형 점을 계산 하 고 나면 형식 배열에 저장 됩니다 `POINT`, 배열 정의를 한 후 추가 추가 `m_nSides` Polyctl.h의.  
  
     [!code-cpp[NVC_ATL_Windowing#48](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_2.h)]  
  
## OnDraw 메서드 수정  
 수정 하면 이제는 `OnDraw` Polyctl.h의 방법.  추가 코드를 새 펜 및 브러시를 사용 하 여 다각형 그리기를 만들고 호출 하 고 있는 `Ellipse` 및 `Polygon` 실제 그리기를 수행 하는 Win32 API 함수입니다.  
  
#### OnDraw 함수를 수정 하려면  
  
1.  기존 대체 `OnDraw` PolyCtl.h 메서드에서 다음 코드를 사용 합니다.  
  
     [!code-cpp[NVC_ATL_Windowing#49](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_3.cpp)]  
  
## 다각형 점을 계산할 메서드 추가  
 라는 메서드를 추가 합니다. `CalcPoints`, 다각형의 경계를 확인 하는 점의 좌표를 계산 합니다.  함수에 전달 되는 RECT 변수에서 이러한 계산을 기반으로 합니다.  
  
#### CalcPoints 메서드를 추가 하려면  
  
1.  변수의 선언 추가 `CalcPoints` 에 `IPolyCtl` 공용 부분을 `CPolyCtl` Polyctl.h의 클래스:  
  
     [!code-cpp[NVC_ATL_Windowing#50](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_4.h)]  
  
     공용 섹션의 마지막 부분에 `CPolyCtl` 클래스가 다음과 같이 표시 됩니다.  
  
     [!code-cpp[NVC_ATL_Windowing#51](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_5.h)]  
  
2.  이 구현을 추가 `CalcPoints` PolyCtl.cpp 끝 함수:  
  
     [!code-cpp[NVC_ATL_Windowing#52](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_6.cpp)]  
  
## 채우기 색 초기화  
 초기화 `m_clrFillColor` 기본 색으로 합니다.  
  
#### 채우기 색을 초기화 하려면  
  
1.  이 줄을 추가 하 여 녹색의 기본 색으로 사용 된 `CPolyCtl` Polyctl.h의 생성자:  
  
     [!code-cpp[NVC_ATL_Windowing#53](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_7.h)]  
  
 이제 생성자는 다음과 같이 나타납니다.  
  
 [!code-cpp[NVC_ATL_Windowing#54](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_8.h)]  
  
## 빌드 및 컨트롤 테스트  
 컨트롤을 다시 빌드하십시오.  PolyCtl.htm 파일 여전히 열 이면 닫혀 있는지 확인 하 고 다음을 클릭  **빌드 다각형** 에 있는  **빌드** 메뉴.  다시 PolyCtl.htm 페이지에서에서 컨트롤을 볼 수 있지만이 이번 ActiveX 컨트롤 테스트 컨테이너를 사용 합니다.  
  
#### ActiveX 컨트롤 테스트 컨테이너를 사용.  
  
1.  빌드 및 ActiveX 컨트롤 Test Container를 시작 합니다.  자세한 내용은  [TSTCON 샘플: 컨트롤 테스트 컨테이너 ActiveX](../top/visual-cpp-samples.md).  
  
2.  테스트 컨테이너에서에  **편집** 메뉴를 클릭  **새 컨트롤 삽입**.  
  
3.  호출 되는 컨트롤을 찾아 `PolyCtl Class`를 클릭 하 고  **확인**.  원 안에 녹색 삼각형이 표시 됩니다.  
  
 다음 절차에 따라 변의 수를 변경해 보십시오.  테스트 컨테이너에서 이중 인터페이스의 속성을 수정 하려면 사용 **Invoke Methods**.  
  
#### 테스트 컨테이너 내에서 컨트롤의 속성을 수정.  
  
1.  테스트 컨테이너에서 클릭  **메서드 호출** 에 있는  **컨트롤** 메뉴.  
  
     **메서드 호출** 대화 상자가 표시 됩니다.  
  
2.  선택의 **PropPut** 버전의 **Sides** 속성에서의  **메서드 이름** 드롭다운 목록 상자.  
  
3.  형식  `5` 에  **매개 변수 값** 상자에서 클릭  **설정 값**를 클릭 하 고  **Invoke**.  
  
 참고 컨트롤은 변경 되지 않습니다.  설정 하 여 변의 수를 내부적으로 변경 했지만 `m_nSides` 변수에서이 컨트롤을 다시 발생 하지 않습니다.  다른 응용 프로그램으로 전환한 다음 다시 테스트 컨테이너로 전환 하면 컨트롤 그려져 있고 올바른 변의 수가 있습니다.  
  
 이 문제를 해결 하려면 호출을 추가 `FireViewChange` 에 정의 된 함수를 `IViewObjectExImpl`, 변의 수를 설정한 후.  컨트롤이 자체 창에서 실행 되는 경우 `FireViewChange` 를 호출 하 여 `InvalidateRect` 메서드를 직접.  컨트롤, 창 없는 실행 하는 경우는 `InvalidateRect` 컨테이너의 사이트 인터페이스에서 메서드를 호출 합니다.  이렇게 자동으로 다시 칠해집니다 컨트롤이 됩니다.  
  
#### Fireviewchange에 호출을 추가 하려면  
  
1.  PolyCtl.cpp 호출을 추가 하 여 업데이트 `FireViewChange` 에 있는 `put_Sides` 메서드.  완료 되 면은 `put_Sides` 메서드가 다음과 같이 표시 되어야 합니다.  
  
     [!code-cpp[NVC_ATL_Windowing#55](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_9.cpp)]  
  
 추가한 후 `FireViewChange`, 다시 작성 및 제어 ActiveX 컨트롤 테스트 컨테이너에 다시 시도 하십시오.  변의 수를 변경 하 고 클릭이 시간 `Invoke`, 즉시 변경할 컨트롤이 표시 되어야 합니다.  
  
 다음 단계에서는 이벤트를 추가 합니다.  
  
 [3 단계로 다시](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md) &#124; [5 단계](../atl/adding-an-event-atl-tutorial-part-5.md)  
  
## 참고 항목  
 [자습서](../atl/active-template-library-atl-tutorial.md)   
 [테스트 컨테이너로 속성 및 이벤트 테스트](../mfc/testing-properties-and-events-with-test-container.md)