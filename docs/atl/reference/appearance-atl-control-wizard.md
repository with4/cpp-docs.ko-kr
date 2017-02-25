---
title: "모양, ATL 컨트롤 마법사 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.control.misc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL 컨트롤 마법사, 모양"
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# 모양, ATL 컨트롤 마법사
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

여기에 "검색 결과" 요약을 삽입합니다.  
  
 마법사의 이 페이지에서는 컨트롤에 대한 추가 사용자 요소 옵션을 식별합니다.  이 페이지는 [옵션, ATL 컨트롤 마법사](../../atl/reference/options-atl-control-wizard.md) 페이지의 **컨트롤 형식**에서 **표준 컨트롤**로 지정된 컨트롤인 경우 나타납니다.  
  
## UI 요소 목록  
 **뷰 상태**  
 컨테이너 내에서의 컨트롤 모양을 설정합니다.  
  
-   **불투명**: [VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201) 열거형에서 `VIEWSTATUS_OPAQUE` 비트를 설정하고 [CComControlBase::OnDraw](../Topic/CComControlBase::OnDraw.md) 메서드에 전달되는 전체 컨트롤 사각형을 그립니다.  컨트롤이 완전히 불투명하게 나타나고 컨트롤 경계선 뒤에서 컨테이너가 전혀 보이지 않습니다.  
  
     이렇게 설정하면 컨테이너에서 컨트롤을 더 신속하게 그리는데 도움이 됩니다.  이 옵션을 선택하지 않으면 컨트롤에 투명한 부분이 포함될 수 있습니다.  
  
     불투명 컨트롤에만 단색 배경이 포함될 수 있습니다.  
  
-   `VIEWSTATUS` 열거형에서 `VIEWSTATUS_SOLIDBKGND` 비트를 설정합니다.  컨트롤의 배경은 무늬 없이 단색으로 나타납니다.  
  
     **불투명** 옵션을 선택한 경우에만 이 옵션을 사용할 수 있습니다.  
  
 **컨트롤 추가 기준**  
 컨트롤을 구현하는 클래스에 [CContainedWindow](../Topic/CContainedWindow.md) 데이터 멤버를 추가하여 컨트롤을 Windows 컨트롤 형식 기반으로 설정합니다.  또한 메시지 맵과 메시지 처리기 함수를 추가하여 컨트롤에 대한 Windows 메시지를 처리합니다.  다음 목록에서 만들려는 Windows 컨트롤 형식을 선택합니다.  
  
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
 컨트롤의 기타 모양 및 동작 옵션을 설정합니다.  
  
-   **런타임에 숨김**: 런타임에 컨트롤이 보이지 않도록 설정합니다.  보이지 않는 컨트롤을 사용하여 일정 시간 간격으로 이벤트를 발생시키는 등과 같은 작업을 백그라운드에서 수행할 수 있습니다.  
  
-   **단추로 사용**: [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) 열거형에서 `OLEMISC_ACTSLIKEBUTTON` 비트를 설정하여 컨트롤이 단추처럼 동작하도록 합니다.  컨테이너가 컨트롤의 클라이언트 사이트를 기본 단추로 표시한 경우 이 옵션을 선택하면 단추 컨트롤에 두꺼운 프레임이 그려지고 해당 컨트롤이 기본 단추로 표시됩니다.  자세한 내용은 [CComControlBase::GetAmbientDisplayAsDefault](../Topic/CComControlBase::GetAmbientDisplayAsDefault.md)를 참조하십시오.  
  
-   **레이블로 사용**: `OLEMISC` 열거형에서 `OLEMISC_ACTSLIKELABEL` 비트를 설정하여 컨트롤이 컨테이너의 네이티브 레이블을 대체할 수 있도록 합니다.  컨테이너에서는 이 플래그를 사용하여 할 일을 결정합니다.  
  
 **기타**  
 컨트롤에 대한 추가 동작 옵션을 설정합니다.  
  
-   **정규화된 DC**: 컨트롤이 자신을 그리도록 호출될 때 정규화된 장치 컨텍스트를 만들도록 설정합니다.  이렇게 하면 컨트롤의 모양은 표준화되지만 그리기 작업의 효율성은 떨어집니다.  
  
-   **창만**: 컨트롤에 반드시 창이 있도록 지정합니다.  이 옵션을 선택하지 않으면 창 없는 개체를 지원하는 컨테이너에서 컨트롤은 자동으로 창이 없는 상태가 되고, 창 없는 개체를 지원하지 않는 컨테이너에서는 자동으로 창이 있는 상태가 됩니다.  이 옵션을 선택하면 창 없는 개체를 지원하는 컨테이너의 경우라도 창 있는 컨트롤이 됩니다.  
  
-   **삽입 가능**: Word 및 Excel과 같은 응용 프로그램의 **개체 삽입** 대화 상자에 컨트롤이 나타나게 하려면 이 옵션을 선택합니다.  그런 다음 포함 개체를 지원하는 모든 응용 프로그램에서 이 대화 상자를 통해 컨트롤을 삽입할 수 있습니다.  
  
## 참고 항목  
 [ATL 컨트롤 마법사](../../atl/reference/atl-control-wizard.md)   
 [SUBEDIT Sample: Superclasses a Standard Windows Control](http://msdn.microsoft.com/ko-kr/30e46bdc-ed92-417c-b6b8-359017265a7b)