---
title: 컨트롤 (ATL 자습서, 3 부)에 속성 추가 | Microsoft Docs
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
ms.openlocfilehash: 7cbfb0b22579aceb5cbee196e3c5eda3079c9304
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848719"
---
# <a name="adding-a-property-to-the-control-atl-tutorial-part-3"></a>컨트롤에 속성 추가(ATL 자습서, 3부)
`IPolyCtl` 컨트롤의 사용자 지정 메서드 및 속성을 포함 하는 인터페이스 이며 속성을 추가 합니다.  
  
### <a name="to-add-a-property-using-the-add-property-wizard"></a>속성 추가 마법사를 사용 하 여 속성을 추가 하려면  
  
1.  클래스 뷰에서 Polygon 분기를 확장 합니다.  
  
2.  IPolyCtl를 마우스 오른쪽 단추로 클릭 합니다.  
  
3.  바로 가기 메뉴에서 클릭 **추가**를 클릭 하 고 **; 속성 추가**합니다.  
  
     속성 추가 마법사가 나타납니다.  
  
4.  형식의 속성 드롭다운 목록에서 선택 `SHORT`합니다.  
  
5.  형식 *양쪽* 으로 **속성 이름입니다.**  
  
6.  클릭 **완료** 속성 추가 완료 합니다.  
  
 MIDL (.idl 파일을 컴파일되지 않는 프로그램)를 정의 하는 인터페이스에 속성을 추가 하는 경우는 `Get` 해당 값을 검색 하는 메서드 및 `Put` 새 값을 설정 하는 것에 대 한 메서드. 메서드를 추가 하 여 라고 `put_` 및 `get_` 속성 이름입니다.  
  
 속성 추가 마법사는.idl 파일에 필요한 줄을 추가합니다. 또한 추가 된 `Get` 및 `Put` 함수 PolyCtl.h의 클래스 정의에 프로토타입 및 PolyCtl.cpp에 비어 있는 구현을 추가 합니다. 이 함수를 찾아 열고 PolyCtl.cpp 확인할 수 있습니다 `get_Sides` 고 `put_Sides`입니다.  
  
 이제 기본 함수를 설정 하 고 속성을 검색 하지만 저장할 수 있는 위치를 해야 합니다. 변수 속성을 저장 하 고 함수에 따라 업데이트를 만들게 됩니다.  
  
#### <a name="to-create-a-variable-to-store-the-property-and-update-the-put-and-get-methods"></a>속성을 저장 및 업데이트는 put 및 get 메서드와 달라 야 하는 변수를 만들려면  
  
1.  솔루션 탐색기에서 PolyCtl.h를 열고 정의 뒤에 다음 줄을 추가 `m_clrFillColor`:  
  
     [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]  
  
2.  기본값을 설정 `m_nSides`합니다. 기본 삼각형 PolyCtl.h의 생성자에 대 한 줄을 추가 하 여 모양을 확인 합니다.  
  
     [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]  
  
3.  구현 된 `Get` 고 `Put` 메서드. 합니다 `get_Sides` 및 `put_Sides` 함수 선언 PolyCtl.h에 추가 되었습니다. 에 대 한 PolyCtl.cpp의 코드를 바꿔 `get_Sides` 고 `put_Sides` 다음 코드를 사용 하 여:  
  
     [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]  
  
 합니다 `get_Sides` 의 현재 값을 반환 하는 메서드를 `Sides` 속성을 통해는 `pVal` 포인터입니다. 에 `put_Sides` 메서드는 코드를 사용 하면 사용자 설정는 `Sides` 속성 허용 되는 값을 합니다. 최소 3, 및 지점의 배열로, 각 면에 대해 사용 되므로 100 제한은 적절 한 최 댓 값.  
  
 이제 라는 속성이 `Sides`합니다. 다음 단계에서 사용 하는 그리기 코드를 변경 됩니다.  
  
 [2 단계를 다시](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; [4 단계로 이동 합니다.](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)  
  
## <a name="see-also"></a>참고 항목  
 [자습서](../atl/active-template-library-atl-tutorial.md)

