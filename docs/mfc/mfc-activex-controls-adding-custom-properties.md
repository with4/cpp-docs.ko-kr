---
title: 'MFC ActiveX 컨트롤: 사용자 지정 속성 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], properties
- properties [MFC], custom
ms.assetid: 85af5167-74c7-427b-b8f3-e0d7b73942e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fc3aa3f7aa8b6f4abf28c12a11f75540f59238e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-activex-controls-adding-custom-properties"></a>MFC ActiveX 컨트롤: 사용자 지정 속성 추가
스톡 속성에서 사용자 지정 속성 다를 사용자 지정 속성에서 아직 구현 되지 않는 한다는 점에서 `COleControl` 클래스입니다. 사용자 지정 속성은 특정 상태 또는 컨트롤을 사용 하 여 프로그래머에 ActiveX 컨트롤의 모양을을 노출할 사용 됩니다.  
  
 이 문서 속성 추가 마법사를 사용 하 여 ActiveX 컨트롤에 사용자 지정 속성을 추가 하는 방법을 설명 하 고 그 결과 코드 수정 사항에 설명 합니다. 다음과 같은 내용을 다룹니다.  
  
-   [속성 추가 마법사를 사용 하 여 사용자 지정 속성을 추가 하려면](#_core_using_classwizard_to_add_a_custom_property)  
  
-   [사용자 지정 속성에 대 한 변경 사항을 속성 마법사 추가](#_core_classwizard_changes_for_custom_properties)  
  
 사용자 지정 속성으로 구현 하는 네 가지가 수행할: 멤버 변수, 알림, Get/Set 메서드 및 매개 변수화 된 멤버 변수입니다.  
  
-   멤버 변수 구현  
  
     이 구현은 컨트롤 클래스의 멤버 변수 속성의 상태를 나타냅니다. 속성 값이 변경에 대해 알아야 중요 하지 않은 경우 멤버 변수 구현을 사용 합니다. 이 구현 세 가지 유형 중 최소한의 속성에 대 한 지원 코드를 만듭니다. 멤버 변수 구현에 대 한 디스패치 맵 항목 매크로 [DISP_PROPERTY](../mfc/reference/dispatch-maps.md#disp_property)합니다.  
  
-   알림 구현은 멤버 변수  
  
     이 구현은 멤버 변수 및 속성 추가 마법사에서 만든 알림 함수로 구성 됩니다. 속성 값이 변경 후 알림 함수는 자동으로 프레임 워크에서 호출 됩니다. 사용 하 여 멤버 변수 알림 구현은 속성 값이 변경 후 알림이 표시 하려는 경우. 이 구현은 함수 호출이 필요 하기 때문에 시간이 오래 걸립니다. 이 구현에 대 한 디스패치 맵 항목 매크로 [DISP_PROPERTY_NOTIFY](../mfc/reference/dispatch-maps.md#disp_property_notify)합니다.  
  
-   Get/Set 메서드 구현  
  
     이 구현은 컨트롤 클래스의 멤버 함수 쌍으로 이루어져 있습니다. Get/Set 메서드 구현 자동으로 Get 멤버가 컨트롤의 사용자 속성의 현재 값을 요청 하는 경우 함수 및 호출 Set 멤버 함수 컨트롤의 사용자 속성을 변경할 수를 요청 합니다. 예를 실행 하는 동안 속성의 값을 계산 하기 실제 속성을 변경 하기 전에 컨트롤의 사용자에 의해 전달 되는 값의 유효성을 검사 하거나 여러 읽기 또는 쓰기 전용 속성 유형을 구현 하는 경우에이 구현을 사용 합니다. 이 구현에 대 한 디스패치 맵 항목 매크로 [DISP_PROPERTY_EX](../mfc/reference/dispatch-maps.md#disp_property_ex)합니다. 다음 섹션을 [속성 추가 마법사를 사용 하 여 사용자 지정 속성을 추가 하려면](#_core_using_classwizard_to_add_a_custom_property), CircleOffset 사용자 지정 속성을 사용 하 여이 구현을 보여 줍니다.  
  
-   매개 변수가 있는 구현  
  
     매개 변수가 있는 구현은 속성 추가 마법사에서 지원 됩니다. 매개 변수가 있는 속성 (속성 배열 라고도 함) 값 집합을 단일 사용자 컨트롤의 속성을 통해 액세스 데 사용할 수 있습니다. 이 구현에 대 한 디스패치 맵 항목 매크로 `DISP_PROPERTY_PARAM`합니다. 이 형식을 구현에 대 한 자세한 내용은 참조 하십시오. [매개 변수가 있는 속성을 구현](../mfc/mfc-activex-controls-advanced-topics.md) 문서의 ActiveX 컨트롤: 고급 항목입니다.  
  
##  <a name="_core_using_classwizard_to_add_a_custom_property"></a> 사용 하는 속성 추가 마법사 사용자 지정 속성을 추가 하려면  
 다음 절차 CircleOffset Get/Set 메서드 구현을 사용 하 여 사용자 지정 속성을 추가 하는 방법을 보여 줍니다. CircleOffset 사용자 지정 속성에는 컨트롤의 사용자를를 컨트롤의 경계 사각형의 중앙에서 원을 오프셋할 수 있습니다. Get/Set 메서드 이외의 구현 사용 하 여 사용자 지정 속성을 추가 하기 위한 절차는 매우 비슷합니다.  
  
 이 절차는 다른 사용자 지정 속성을 추가 하려면 데도 사용할 수 있습니다. 사용자 지정 속성 이름을 CircleOffset 속성 이름 및 매개 변수를 대체 합니다.  
  
#### <a name="to-add-the-circleoffset-custom-property-using-the-add-property-wizard"></a>속성 추가 마법사를 사용 하 여 CircleOffset 사용자 지정 속성을 추가 하려면  
  
1.  컨트롤의 프로젝트를 로드합니다.  
  
2.  클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.  
  
3.  컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.  
  
4.  바로 가기 메뉴에서 클릭 **추가** 클릭 하 고 **속성 추가**합니다.  
  
     열립니다는 [속성 추가 마법사](../ide/names-add-property-wizard.md)합니다.  
  
5.  에 **속성 이름** 상자에서 입력 `CircleOffset`합니다.  
  
6.  **구현 형식**에서 **Get/Set 메서드**를 클릭합니다.  
  
7.  에 **속성 형식** 상자 **짧은**합니다.  
  
8.  Get 및 Set 함수의 고유 이름을 입력 하거나 기본 이름을 적용 합니다.  
  
9. **마침**을 클릭합니다.  
  
##  <a name="_core_classwizard_changes_for_custom_properties"></a> 속성 추가 마법사 변경에 대 한 사용자 지정 속성  
 CircleOffset 사용자 지정 속성을 추가 하는 때 속성 추가 마법사 헤더에는 변경 (합니다. H)와 구현 (합니다. 컨트롤 클래스의 CPP) 파일입니다.  
  
 다음 줄에 추가 되 고 있습니다. H 이라는 두 개의 함수를 선언 하는 파일 `GetCircleOffset` 및 `SetCircleOffset`:  
  
 [!code-cpp[NVC_MFC_AxUI#25](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_1.h)]  
  
 다음 줄은 컨트롤의에 추가 됩니다. IDL 파일:  
  
 [!code-cpp[NVC_MFC_AxUI#26](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_2.idl)]  
  
 이 줄 CircleOffset 속성을 속성 추가 마법사의 메서드 및 속성 목록에서 메서드의 위치에서 가져온 특정 ID 번호를 할당 합니다.  
  
 또한 다음 줄 디스패치 맵에 추가 됩니다 (에 합니다. 컨트롤 클래스의 CPP 파일) CircleOffset 속성 컨트롤의 두 가지 처리기 함수에 매핑됩니다.  
  
 [!code-cpp[NVC_MFC_AxUI#27](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_3.cpp)]  
  
 구현에 마지막으로 `GetCircleOffset` 및 `SetCircleOffset` 함수는 컨트롤의 끝에 추가 됩니다. CPP 파일입니다. 대부분의 경우에서 속성의 값을 반환 하는 Get 함수를 수정 합니다. Set 함수에는 대개 앞 이나 뒤 속성 변경 내용을 실행 하는 코드가 포함 됩니다.  
  
 [!code-cpp[NVC_MFC_AxUI#28](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_4.cpp)]  
  
 속성 추가 마법사 자동으로 추가 하는 호출에 [SetModifiedFlag](../mfc/reference/colecontrol-class.md#setmodifiedflag), Set 함수 본문에 있습니다. 수정 된 대로 컨트롤을 표시이 함수를 호출 합니다. 컨트롤이 수정 된 경우 컨테이너에 저장 될 때 새 상태로 저장 됩니다. 컨트롤의 영구 상태의 일부로 저장 하는 속성 값이 변경 될 때마다이 함수를 호출 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX 컨트롤: 속성](../mfc/mfc-activex-controls-properties.md)   
 [MFC ActiveX 컨트롤: 메서드](../mfc/mfc-activex-controls-methods.md)   
 [COleControl 클래스](../mfc/reference/colecontrol-class.md)
