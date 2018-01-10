---
title: "ATL 컨트롤 마법사, 모양 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.codewiz.class.atl.control.misc
dev_langs: C++
helpviewer_keywords: ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8869df577dfbc541b989beb4b4f3117d7d12feea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="appearance-atl-control-wizard"></a>모양, ATL 컨트롤 마법사
여기에 요약 "검색 결과"를 삽입 합니다.  
  
 컨트롤에 대 한 추가 요소 옵션을 식별 하는 마법사의이 페이지를 사용 합니다. 이 페이지는로 식별 되는 컨트롤에 사용할 수 있는 **표준 컨트롤** 아래 **컨트롤 형식** 에 [옵션, ATL 컨트롤 마법사](../../atl/reference/options-atl-control-wizard.md) 페이지.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **상태 보기**  
 컨테이너 내에서 컨트롤의 모양을 설정합니다.  
  
-   **불투명**: 설정의 `VIEWSTATUS_OPAQUE` 비트는 [VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201) 열거형과에 전달 되는 전체 컨트롤 사각형을 그립니다는 [CComControlBase::OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw) 메서드. 컨트롤에는 완전히 불투명 나타나고 컨트롤 경계 뒤 표시 컨테이너 중입니다.  
  
     이 설정은 컨테이너 보다 신속 하 게 컨트롤을 그릴 수 있습니다. 이 옵션을 선택 하지 않으면 컨트롤이 투명 한 파트를 포함할 수 있습니다.  
  
     불투명 컨트롤에만 단색 배경이 있을 수 있습니다.  
  
-   설정의 `VIEWSTATUS_SOLIDBKGND` 비트는 `VIEWSTATUS` 열거형입니다. 컨트롤의 배경 무늬 없이 단색으로 표시 됩니다.  
  
     이 옵션은 사용할 수 있는 경우에만 **불투명** 옵션을 선택한 합니다.  
  
 **에 따라 컨트롤 추가**  
 설정 하는 컨트롤을 추가 하 여 Windows 컨트롤 형식에 따라 설정 된 [CContainedWindow](ccontainedwindowt-class.md) 컨트롤을 구현 하는 클래스 데이터 멤버입니다. 또한 메시지 맵 및 컨트롤에 대 한 Windows 메시지를 처리 하는 메시지 처리기 함수를 추가 합니다. 목록에서 만들려는, 있는 경우 Windows 컨트롤의 형식을 선택 합니다.  

  
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
  
-   **실행 시 보이지 않는**: 런타임 시 표시 되지 않도록 하려면 제어를 설정 합니다. 정해진 간격 이벤트를 발생 시키고 같이 백그라운드 작업을 수행할 보이지 않는 컨트롤을 사용할 수 있습니다.  
  
-   **단추와 같은 역할**: 설정의 `OLEMISC_ACTSLIKEBUTTON` 비트는 [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) 열거형 컨트롤이 동작할 수 있도록 단추와 같은 합니다. 컨테이너에 컨트롤의 클라이언트 사이트 기본 단추로으로 표시 하는 경우이 옵션을 선택 그려지고 두꺼운 프레임을 기본 단추로 표시 되도록 단추 컨트롤을 수 있습니다. 참조 [CComControlBase::GetAmbientDisplayAsDefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault) 자세한 정보에 대 한 합니다.  
  
-   **레이블 처럼 작동**: 집합은 `OLEMISC_ACTSLIKELABEL` 비트는 `OLEMISC` 대체할 컨테이너의 기본 레이블 컨트롤을 사용할 수 있도록 하는 열거형입니다. 컨테이너 내용이 있는 경우이 플래그를 수행할 작업을 결정 합니다.  
  
 **기타**  
 컨트롤에 대 한 추가 동작이 옵션을 설정합니다.  
  
-   **DC 정규화**: 정규화 된 장치 컨텍스트 자체를 그리는 데 호출 될 때 만들 컨트롤을 설정 합니다. 이 작업은 컨트롤의 모양 표준화 되지만 그리기 효율성이 떨어집니다.  
  
-   **창 에서만**: 컨트롤 창 없는 수 없음을 지정 합니다. 이 옵션을 선택 하지 않으면 자동으로 창 없는 개체를 지 원하는 컨테이너의 창 없는 컨트롤은 며 창 없는 개체를 지원 하지 않는 컨테이너. 창 없는 개체를 지 원하는 컨테이너에도 기간 이동 되도록 사용자 컨트롤을 강제로이 옵션을 선택 합니다.  
  
-   **삽입 가능**: 컨트롤에 표시 하려면이 옵션을 선택는 **개체 삽입** Word 및 Excel 같은 응용 프로그램의 대화 상자. 그런 다음이 대화 상자를 통해 포함 된 개체를 지 원하는 모든 응용 프로그램에서 컨트롤을 삽입할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL 컨트롤 마법사](../../atl/reference/atl-control-wizard.md)   
 [표준 Windows 컨트롤 샘플 SUBEDIT: 슈퍼 클래스](http://msdn.microsoft.com/en-us/30e46bdc-ed92-417c-b6b8-359017265a7b)

