---
title: 'MFC ActiveX 컨트롤: 사용자 지정 메서드 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], methods
- PtInCircle custom method [MFC]
ms.assetid: 8f8dc344-44a0-4021-8db5-4cdd3d700e18
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1cdf264bd0c2aa44bdeecc58b4bc8eb89c70fb91
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350035"
---
# <a name="mfc-activex-controls-adding-custom-methods"></a>MFC ActiveX 컨트롤: 사용자 지정 메서드 추가
사용자 지정 메서드 스톡 메서드 한다는 점에서 다릅니다 의해 이미 구현 되지 않은 `COleControl`합니다. 사용자 컨트롤에 추가한 각 사용자 지정 방법에 대 한 구현을 제공 해야 합니다.  
  
 ActiveX 컨트롤 사용자는 언제 든 지 컨트롤 관련 동작을 수행 하려면 사용자 지정 메서드를 호출할 수 있습니다. 사용자 지정 방법에 대 한 디스패치 맵 항목은 양식의 `DISP_FUNCTION`합니다.  
  
##  <a name="_core_adding_a_custom_method_with_classwizard"></a> 사용 하 여 사용자 지정 메서드 추가 메서드 추가 마법사  
 다음 절차에서는 사용자 지정 메서드 PtInCircle ActiveX 컨트롤의 기본 코드를 추가 합니다. PtInCircle 좌표는 컨트롤에 전달 된 내부 또는 외부의 원을 있는지 확인 합니다. 이 절차는 다른 사용자 지정 메서드를 추가 하려면 데도 사용할 수 있습니다. 사용자 지정 메서드 이름 및 해당 매개 변수 PtInCircle 메서드 이름과 매개 변수를 대체 합니다.  
  
> [!NOTE]
>  사용 하 여이 예제는 `InCircle` 이벤트 문서에서 함수입니다. 이 함수에 대 한 자세한 내용은 문서 참조 [MFC ActiveX 컨트롤: ActiveX 컨트롤에 사용자 지정 이벤트 추가](../mfc/mfc-activex-controls-adding-custom-events.md)합니다.  
  
#### <a name="to-add-the-ptincircle-custom-method-using-the-add-method-wizard"></a>메서드 추가 마법사를 사용 하 여 PtInCircle 사용자 지정 메서드를 추가 하려면  
  
1.  컨트롤의 프로젝트를 로드 합니다.  
  
2.  클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.  
  
3.  컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.  
  
4.  바로 가기 메뉴에서 클릭 **추가** 클릭 하 고 **메서드 추가**합니다.  
  
     메서드 추가 마법사가 열립니다.  
  
5.  에 **메서드 이름** 상자에서 입력 `PtInCircle`합니다.  
  
6.  에 **내부 이름** 상자 메서드 내부 함수의 이름을 입력 하거나 기본값을 사용 하 여 (이 경우 `PtInCircle`).  
  
7.  에 **반환 형식** 상자 **VARIANT_BOOL** 메서드의 반환 형식에 대 한 합니다.  
  
8.  사용 하는 **매개 변수 형식** 및 **매개 변수 이름** 호출 매개 변수를 추가 하는 컨트롤을 `xCoord` (형식 **OLE_XPOS_PIXELS**).  
  
9. 사용 하는 **매개 변수 형식** 및 **매개 변수 이름** 호출 매개 변수를 추가 하는 컨트롤을 `yCoord` (형식 **OLE_YPOS_PIXELS**).  
  
10. **마침**을 클릭합니다.  
  
##  <a name="_core_classwizard_changes_for_custom_methods"></a> 사용자 지정 메서드 추가 마법사 변경 메서드  
 사용자 지정 메서드를 추가할 때 메서드 추가 마법사 컨트롤 클래스 헤더에는 일부 변경 (합니다. H) 및 구현 (합니다. CPP) 파일입니다. 컨트롤 클래스 헤더에 디스패치 맵 선언은 다음 줄이 추가 (합니다. H) 파일:  
  
 [!code-cpp[NVC_MFC_AxUI#18](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_1.h)]  
  
 이 코드에서는 호출 디스패치 메서드 처리기 선언 `PtInCircle`합니다. PtInCircle 외부 이름을 사용 하 여 컨트롤 사용자가이 함수를 호출할 수 있습니다.  
  
 다음 줄은 컨트롤의에 추가 됩니다. IDL 파일:  
  
 [!code-cpp[NVC_MFC_AxUI#19](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_2.idl)]  
  
 이 줄에 표시 된 위치 메서드 추가 마법사 메서드 및 속성 목록에 특정 ID 번호를 PtInCircle 메서드를 할당합니다. 메서드 추가 마법사, 사용자 지정 메서드를 사용 하기 때문에 대 한 항목이 프로젝트의 자동으로 추가 되었습니다. IDL 파일입니다.  
  
 다음 명령줄을 구현에는 또한 (합니다. 컨트롤의 디스패치 맵에 cpp) 컨트롤 클래스에 추가 됩니다.  
  
 [!code-cpp[NVC_MFC_AxUI#20](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_3.cpp)]  
  
 `DISP_FUNCTION` 매크로 컨트롤의 처리기 함수에 PtInCircle 메서드 매핑됩니다 `PtInCircle`, 반환 형식이 되도록 선언 **VARIANT_BOOL**, 형식의 두 매개 변수를 선언 하 고 **VTS_XPOS_PIXELS** 및 **VTS_YPOSPIXELS** 에 전달할 `PtInCircle`합니다.  
  
 메서드 추가 마법사에서 스텁 함수를 추가 하는 마지막으로, `CSampleCtrl::PtInCircle` 맨 아래에서 컨트롤의 구현 (합니다. Cpp) 합니다. 에 대 한 `PtInCircle` 앞서 설명한 것 처럼 작동 것 해야 다음과 같이 수정할 수 있습니다.  
  
 [!code-cpp[NVC_MFC_AxUI#21](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_4.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [클래스 뷰 및 개체 브라우저 아이콘](/visualstudio/ide/class-view-and-object-browser-icons)

