---
title: 그리기 코드 (ATL 자습서, 4 부) 변경 | Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 08ff14e8-aa49-4139-a110-5d071939cf1e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c077aca8c3276fac963eda8cdd2c413a9d6d5f5b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358914"
---
# <a name="changing-the-drawing-code-atl-tutorial-part-4"></a>그리기 코드 변경(ATL 자습서, 4부)
기본적으로 컨트롤의 그리기 코드가 표시 사각형 및 텍스트 **PolyCtl**합니다. 이 단계에서는 좀 더 재미 있게 표시 하는 코드를 변경 합니다. 다음 작업은 다음과 같습니다.  
  
-   헤더 파일 수정  
  
-   수정 된 `OnDraw` 함수  
  
-   다각형 요소를 사용 하는 계산에 메서드 추가  
  
-   채우기 색 초기화  
  
## <a name="modifying-the-header-file"></a>헤더 파일 수정  
 수학 함수에 대 한 지원을 추가 하 여 시작 `sin` 및 `cos`, 사용 될 다각형 점 계산 하 고 저장 하는 배열 만들어 배치 합니다.  
  
#### <a name="to-modify-the-header-file"></a>헤더 파일을 수정 하려면  
  
1.  줄 추가 `#include <math.h>` PolyCtl.h의 맨 위로 이동 합니다. 파일의 맨 위에 다음과 같이 표시 됩니다.  
  
     [!code-cpp[NVC_ATL_Windowing#47](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_1.cpp)]  
  
2.  저장 형식의 배열에 됩니다 다각형 점 계산 되 면 `POINT`, 배열 정의 후 추가 `m_nSides` PolyCtl.h에:  
  
     [!code-cpp[NVC_ATL_Windowing#48](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_2.h)]  
  
## <a name="modifying-the-ondraw-method"></a>OnDraw 메서드를 수정합니다.  
 이제 사용자가 수정할 수는 `OnDraw` PolyCtl.h의 메서드. 코드를 추가할 새 펜 및 브러시를 그릴 다각형,으로 만들고 호출 합니다는 `Ellipse` 및 `Polygon` 실제 그리기를 수행 하는 Win32 API 함수입니다.  
  
#### <a name="to-modify-the-ondraw-function"></a>OnDraw 함수를 수정 하려면  
  
1.  기존 항목 바꾸기 `OnDraw` PolyCtl.h의 메서드를 다음 코드로:  
  
     [!code-cpp[NVC_ATL_Windowing#49](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_3.cpp)]  
  
## <a name="adding-a-method-to-calculate-the-polygon-points"></a>다각형 요소를 사용 하는 계산에 메서드 추가  
 라는 메서드를 추가 `CalcPoints`, 다각형의 경계를 구성 하는 점의 좌표는 계산입니다. 이러한 계산 함수에 전달 되는 RECT 변수에 따라 달라 집니다.  
  
#### <a name="to-add-the-calcpoints-method"></a>CalcPoints 메서드를 추가 하려면  
  
1.  선언을 추가 `CalcPoints` 에 `IPolyCtl` 의 공용 섹션은 `CPolyCtl` PolyCtl.h의 클래스:  
  
     [!code-cpp[NVC_ATL_Windowing#50](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_4.h)]  
  
     공용 섹션의 마지막 부분에서 `CPolyCtl` 클래스는 다음과 같습니다.  
  
     [!code-cpp[NVC_ATL_Windowing#51](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_5.h)]  
  
2.  이 구현을 추가 `CalcPoints` PolyCtl.cpp의 끝에 함수:  
  
     [!code-cpp[NVC_ATL_Windowing#52](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_6.cpp)]  
  
## <a name="initializing-the-fill-color"></a>채우기 색 초기화  
 초기화 `m_clrFillColor` 기본 색을 사용 합니다.  
  
#### <a name="to-initialize-the-fill-color"></a>채우기 색을 초기화 하려면  
  
1.  기본 색으로 녹색을 사용 하 여이 줄을 추가 하 여는 `CPolyCtl` PolyCtl.h에 생성자가 있습니다.  
  
     [!code-cpp[NVC_ATL_Windowing#53](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_7.h)]  
  
 생성자는 이제 다음과 같이 보입니다.  
  
 [!code-cpp[NVC_ATL_Windowing#54](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_8.h)]  
  
## <a name="building-and-testing-the-control"></a>빌드 및 컨트롤 테스트  
 컨트롤을 다시 빌드하십시오. 가 아직 열려 경우 PolyCtl.htm 파일이 닫혀 있는지 확인 한 다음 클릭 **빌드 다각형** 에 **빌드** 메뉴. 다시 한 번 PolyCtl.htm 페이지에서에서 컨트롤을 볼 수 있습니다 하지만이 이번 ActiveX Control Test Container를 사용 합니다.  
  
#### <a name="to-use-the-activex-control-test-container"></a>ActiveX Control Test Container를 사용 하려면  
  
1.  빌드하고 ActiveX Control Test Container를 시작 합니다. 자세한 내용은 참조 [TSTCON 샘플: ActiveX Control Test Container](../visual-cpp-samples.md)합니다.  
  
2.  테스트 컨테이너에에 **편집** 메뉴를 클릭 하 여 **새 컨트롤 삽입**합니다.  
  
3.  호출할 사용자 컨트롤을 찾아 `PolyCtl Class`를 클릭 하 고 **확인**합니다. 원 안에 녹색 삼각형이 표시 됩니다.  
  
 다음 절차에 따라 면 수를 변경해 보십시오. 테스트 컨테이너에서 이중 인터페이스에서 속성을 수정 하려면 사용 하 여 **메서드 호출**합니다.  
  
#### <a name="to-modify-a-controls-property-from-within-the-test-container"></a>테스트 컨테이너 내에서 컨트롤의 속성을 수정 하려면  
  
1.  테스트 컨테이너에서 클릭 **메서드 호출** 에 **제어** 메뉴.  
  
     **메서드 호출** 대화 상자가 표시 됩니다.  
  
2.  선택의 **PropPut** 버전의는 **면** 속성에서는 **메서드 이름** 드롭다운 목록 상자입니다.  
  
3.  형식 `5` 에 **매개 변수 값** 상자를 클릭 **값 설정**를 클릭 하 고 **Invoke**합니다.  
  
 컨트롤 변경 되지 않는 참고 합니다. 설정 하 여 내부적으로 면 수를 변경 하는 `m_nSides` 변수,이 시 키 지 않는 다시 그리기를 제어 합니다. 다른 응용 프로그램으로 전환 하 고 다음 테스트 컨테이너도 다시 전환 하는 경우에 컨트롤 그려져 있고에 올바른 개수의 측면을 찾을 수 있습니다.  
  
 이 문제를 해결 하려면에 대 한 호출 추가 `FireViewChange` 에 정의 된 함수 `IViewObjectExImpl`면 수를 설정한 후, 합니다. 컨트롤은 별도 창에서 실행 중인 경우 `FireViewChange` 호출 됩니다는 `InvalidateRect` 메서드를 직접 합니다. 컨트롤 창 없는 실행 하는 경우는 `InvalidateRect` 컨테이너의 사이트 인터페이스 메서드를 호출 합니다. 이렇게 하면 컨트롤이 다시 그려집니다.  
  
#### <a name="to-add-a-call-to-fireviewchange"></a>FireViewChange에 대 한 호출을 추가 하려면  
  
1.  에 대 한 호출을 추가 하 여 PolyCtl.cpp 업데이트 `FireViewChange` 에 `put_Sides` 메서드. 완료 되 면는 `put_Sides` 메서드는 다음과 같이 표시 됩니다.  
  
     [!code-cpp[NVC_ATL_Windowing#55](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_9.cpp)]  
  
 추가한 후 `FireViewChange`, 다시 작성 및 ActiveX Control Test Container 컨트롤을 다시 시도 하십시오. 양쪽의 수를 변경 하 고 클릭이 시간 `Invoke`를 즉시 변경 제어를 참조 해야 합니다.  
  
 다음 단계에서 이벤트를 추가 합니다.  
  
 [3 단계로 뒤로](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md) &#124; [5 단계로](../atl/adding-an-event-atl-tutorial-part-5.md)  
  
## <a name="see-also"></a>참고 항목  
 [자습서](../atl/active-template-library-atl-tutorial.md)   
 [테스트 컨테이너로 속성 및 이벤트 테스트](../mfc/testing-properties-and-events-with-test-container.md)

