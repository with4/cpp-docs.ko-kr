---
title: (ATL 자습서, 3 부) 컨트롤에 속성 추가 | Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f775fe34-103b-4f07-9999-400e987ee030
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db800de12c0c0e4d7bef2a59a576f1d475e675da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="adding-a-property-to-the-control-atl-tutorial-part-3"></a>컨트롤에 속성 추가(ATL 자습서, 3부)
`IPolyCtl` 사용자 지정 컨트롤의 메서드 및 속성을 포함 하는 인터페이스 이며 속성을 추가 합니다.  
  
### <a name="to-add-a-property-using-the-add-property-wizard"></a>속성 추가 마법사를 사용 하 여 속성을 추가 하려면  
  
1.  클래스 뷰에서 다각형 분기를 확장 합니다.  
  
2.  IPolyCtl를 마우스 오른쪽 단추로 클릭 합니다.  
  
3.  바로 가기 메뉴를 클릭 **추가**, 클릭 하 고 **속성 추가**합니다.  
  
     속성 추가 마법사가 나타납니다.  
  
4.  속성 유형을 드롭 다운 목록에서 선택 `SHORT`합니다.  
  
5.  형식 `Sides` 로 **속성 이름입니다.**  
  
6.  클릭 **마침** 속성 추가 작업을 마칩니다.  
  
 MIDL (.idl 파일을 컴파일하는 프로그램)를 정의 하는 인터페이스에는 속성을 추가 하면 한 `Get` 해당 값을 검색 하기 위한 메서드 및 `Put` 새 값을 설정 하기 위한 메서드. 메서드는 앞에 추가 하 여 명명 된 `put_` 및 `get_` 속성 이름에 있습니다.  
  
 속성 추가 마법사는.idl 파일에 필요한 줄을 추가합니다. 또한 추가 `Get` 및 `Put` 프로토타입 PolyCtl.h 클래스 정의에 작동 하 고 빈 구현 PolyCtl.cpp에 추가 합니다. PolyCtl.cpp 열고 함수를 찾고이 확인 하려면 `get_Sides` 및 `put_Sides`합니다.  
  
 이제 기본 함수를 설정 및 속성을 검색 갖지만 저장할 곳이 필요 합니다. 변수 속성을 저장 하 고 함수에 따라 업데이트를 만들게 됩니다.  
  
#### <a name="to-create-a-variable-to-store-the-property-and-update-the-put-and-get-methods"></a>업데이트는 put 및 get 메서드와 달라 속성을 저장할 변수를 만들려면  
  
1.  정의 뒤에 다음 줄을 추가 하 고 PolyCtl.h를 열고 솔루션 탐색기에서 `m_clrFillColor`:  
  
     [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]  
  
2.  기본값을 설정 `m_nSides`합니다. 기본 삼각형 PolyCtl.h의 생성자에 대 한 행을 추가 하 여 모양을 확인 합니다.  
  
     [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]  
  
3.  구현 된 `Get` 및 `Put` 메서드. `get_Sides` 및 `put_Sides` 함수 선언 PolyCtl.h에 추가 되었습니다. 에 대 한 PolyCtl.cpp의 코드 `get_Sides` 및 `put_Sides` 다음 코드를 사용 합니다.  
  
     [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]  
  
 `get_Sides` 의 현재 값을 반환 하는 메서드는 `Sides` 속성을 통해는 `pVal` 포인터입니다. 에 `put_Sides` 메서드, 코드를 사용 하면 사용자 설정 하 고는 `Sides` 속성에 적합 한 값을 합니다. 최소한, 2이 고 100은 최대 값에 대 한 적절 한 제한을 점의 배열에는 각 측에 대 한 사용 되므로, 합니다.  
  
 이제 라는 속성이 있는 `Sides`합니다. 다음 단계에서 사용 하는 그리기 코드를 변경 합니다.  
  
 [2 단계를 다시](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; [4 단계로](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)  
  
## <a name="see-also"></a>참고 항목  
 [자습서](../atl/active-template-library-atl-tutorial.md)

