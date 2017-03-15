---
title: "ATL 컨트롤 마법사, 모양 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.misc
dev_langs:
- C++
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: dde27a7b62f3ee3b5fe8fcacd8141e9f89ed3c98
ms.lasthandoff: 02/24/2017

---
# <a name="appearance-atl-control-wizard"></a>모양, ATL 컨트롤 마법사
여기 "검색 결과" 요약을 삽입 합니다.  
  
 마법사의이 페이지를 사용 하 여 컨트롤에 대 한 추가 사용자 요소 옵션을 식별 합니다. 이 페이지는로 식별 되는 컨트롤에 대 한 **표준 컨트롤** 아래 **컨트롤 형식** 에 [옵션, ATL 컨트롤 마법사](../../atl/reference/options-atl-control-wizard.md) 페이지입니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **상태 보기**  
 컨테이너 내의 컨트롤의 모양을 설정합니다.  
  
-   **불투명**: 설정의 `VIEWSTATUS_OPAQUE` 비트를 [VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201) 열거형과에 전달 되는 전체 컨트롤 사각형을 그립니다는 [CComControlBase::OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw) 메서드. 컨트롤이 완전히 불투명 나타나고 컨트롤 경계선 뒤 표시 컨테이너의 없음.  
  
     이 컨테이너 컨트롤을 더 빠르게 그릴 수 있습니다. 이 옵션을 선택 하지 않으면 컨트롤 투명 한 부분을 포함할 수 있습니다.  
  
     불투명 컨트롤에만 단색 배경이 있을 수 있습니다.  
  
-   설정의 `VIEWSTATUS_SOLIDBKGND` 에 비트는 `VIEWSTATUS` 열거형입니다. 컨트롤의 배경 무늬 없이 단색으로 표시 됩니다.  
  
     이 옵션은 사용할 경우에만 **불투명** 옵션도 선택 되어 있습니다.  
  
 **기준 컨트롤 추가**  
 컨트롤 추가 하 여 Windows 컨트롤 형식을 기준으로 설정 하는 [CContainedWindow](ccontainedwindowt-class.md) 컨트롤을 구현 하는 클래스 데이터 멤버입니다. 또한 메시지 맵 및 컨트롤에 대 한 Windows 메시지를 처리 하는 메시지 처리기 함수를 추가 합니다. 목록에서 만들려는, 있는 경우 Windows 컨트롤의 종류를 선택 합니다.  

  
-   `Button`  
  
-   `ListBox`  
  
-   `SysAnimate32`  
  
-   `SysListView32`  
  
-   `ComboBox`  
  
-   `RichEdit`  
  
-   `SysDateTimePick32`  
  
-   `SysMonthCal32`  
  
-   `ComboBoxEx32`  
  
-   `ScrollBar`  
  
-   `SysHeader32`  
  
-   `SysTabControl32`  
  
-   `Edit`  
  
-   `Static`  
  
-   `SysIPAddress32`  
  
-   `SysTreeView32`  
  
 **기타 상태**  
 컨트롤에 대 한 추가 모양 및 동작 옵션을 설정합니다.  
  
-   **런타임에 보이지 않는**: 런타임 시 표시 되지 않도록 하려면 제어를 설정 합니다. 정해진 간격 이벤트를 발생 시키고 같이 백그라운드에서 작업을 수행할 보이지 않는 컨트롤을 사용할 수 있습니다.  
  
-   **단추 처럼 동작**: 설정의 `OLEMISC_ACTSLIKEBUTTON` 비트를 [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) 작동 하는 컨트롤을 사용 하도록 설정 하는 열거형 단추를 선택 합니다. 컨테이너는 기본 단추 컨트롤의 클라이언트 사이트를 표시 하는 경우이 옵션을 선택 하면 단추 컨트롤을 기본 단추로 두꺼운 프레임이 그려지고 표시 되도록에 수 있습니다. 참조 [CComControlBase::GetAmbientDisplayAsDefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault) 에 대 한 자세한 내용은 합니다.  
  
-   **레이블 비슷합니다**: 설정의 `OLEMISC_ACTSLIKELABEL` 비트를 `OLEMISC` 대체할 컨테이너의 기본 레이블 컨트롤을 사용 하도록 설정 하는 열거형입니다. 컨테이너 경우 아무 것도이 플래그를 사용 해야 할 일을 결정 합니다.  
  
 **기타**  
 컨트롤에 대 한 추가 동작이 옵션을 설정합니다.  
  
-   **정규화 된 DC**:을 그리게 호출 될 때 정규화 된 장치 컨텍스트를 만들 컨트롤을 설정 합니다. 이 작업에는 컨트롤의 모양을 표준화 되지만 그리기 효율성이 떨어집니다.  
  
-   **창 에서만**: 컨트롤에 반드시 창이 있도록 지정 합니다. 이 옵션을 선택 하지 않으면 컨트롤은 창 없는 개체를 지 원하는 컨테이너에 자동으로 창이 며 창 없는 개체를 지원 하지 않는 컨테이너. 이 옵션을 선택 하면 강제로 컨트롤이 창 없는 개체를 지 원하는 컨테이너의 경우라도 기간 이동 됩니다.  
  
-   **삽입 가능**: 컨트롤에 표시 하려면이 옵션을 선택 된 **개체 삽입** Word 및 Excel 같은 응용 프로그램의 대화 상자입니다. 그런 다음이 대화 상자를 통해 포함 된 개체를 지 원하는 응용 프로그램에서 컨트롤을 삽입할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL 컨트롤 마법사](../../atl/reference/atl-control-wizard.md)   
 [샘플: SUBEDIT 슈퍼 클래스는 표준 Windows 컨트롤](http://msdn.microsoft.com/en-us/30e46bdc-ed92-417c-b6b8-359017265a7b)


