---
title: "컨트롤에 속성 추가(ATL 자습서, 3부) | Microsoft Docs"
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
ms.assetid: f775fe34-103b-4f07-9999-400e987ee030
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 컨트롤에 속성 추가(ATL 자습서, 3부)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`IPolyCtl`컨트롤의 사용자 지정 메서드 및 속성을 포함 하는 인터페이스 이며 속성에 추가 됩니다.  
  
### 속성 추가 마법사를 사용 하 여 속성을 추가 하려면  
  
1.  클래스 뷰에서 다각형 분기를 확장 합니다.  
  
2.  Ipolyctl를 마우스 오른쪽 단추로 클릭 합니다.  
  
3.  바로 가기 메뉴에서  **추가**를 누른 다음  **속성 추가**.  
  
     속성 추가 마법사가 나타납니다.  
  
4.  속성 유형 드롭다운 목록에서 선택 `SHORT`.  
  
5.  형식  `면` 으로  **속성 이름입니다.**  
  
6.  클릭  **완료** 속성 추가 완료 합니다.  
  
 인터페이스에 속성을 추가 하면 MIDL \(.idl 파일을 컴파일하는 프로그램\)을 정의 `Get` 값을 검색 하는 메서드 및는 `Put` 새 값을 설정 하는 방법.  앞으로 메서드는 명명 된 `put_` 및 `get_` 속성 이름입니다.  
  
 속성 추가 마법사는 필요한 선.idl 파일에 추가합니다.  또한 추가 `Get` 및 `Put` Polyctl.h의 클래스 정의에 프로토타입을 작동 및 Polyctl.cpp를 빈 구현을 추가 합니다.  Polyctl.cpp를 열고 함수를 찾고이 확인할 수 있습니다 `get_Sides` 및 `put_Sides`.  
  
 이제 기초 기능을 설정 하 고 속성을 검색할 수 없지만 장소에 저장 해야 합니다.  속성을 저장 하 고 함수를 적절 하 게 업데이트 하는 변수를 만듭니다.  
  
#### 변수 속성을 저장 하 고 업데이트 put 및 get 메서드를 만들려면  
  
1.  솔루션 탐색기에서 Polyctl.h를 열고 정의 뒤에 다음 줄을 추가 합니다. `m_clrFillColor`.  
  
     [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/CPP/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]  
  
2.  설정의 기본값은 `m_nSides`.  기본 줄을 Polyctl.h의 생성자에에서 추가 하 여 삼각형 모양을 확인 합니다.  
  
     [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/CPP/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]  
  
3.  `Get` 및 `Put` 메서드를 구현합니다.  `get_Sides` 및 `put_Sides` 함수 선언을 Polyctl.h에 추가 되었습니다.  코드에서 Polyctl.cpp에 대 한 대체 `get_Sides` 및 `put_Sides` 다음 코드를:  
  
     [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/CPP/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]  
  
 `get_Sides` 의 현재 값을 반환 된 `Sides` 속성을 통해의 `pVal` 포인터.  에 `put_Sides` 메서드, 코드 확인 되는 사용자 설정의 `Sides` 속성에 허용 되는 값.  최소 2 되며 배열 요소의 각 측면에 대 한 사용 되므로 100 최대 값에 대 한 적절 한 제한입니다.  
  
 지금 이라는 속성을 설정할 `Sides`.  다음 단계에서 사용 하는 그리기 코드를 변경 됩니다.  
  
 [2 단계로 다시](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; [4 단계](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)  
  
## 참고 항목  
 [자습서](../atl/active-template-library-atl-tutorial.md)