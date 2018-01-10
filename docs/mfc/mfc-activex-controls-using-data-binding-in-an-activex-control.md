---
title: "MFC ActiveX 컨트롤: ActiveX 컨트롤에서 데이터 바인딩 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- bindable
- requestedit
- defaultbind
- displaybind
- dispid
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], data binding
- data binding [MFC], MFC ActiveX controls
- data-bound controls [MFC], MFC ActiveX controls
- controls [MFC], data binding
- bound controls [MFC], MFC ActiveX
ms.assetid: 476b590a-bf2a-498a-81b7-dd476bd346f1
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 691f832717f5a71c461316b725ee9a69d1350124
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-using-data-binding-in-an-activex-control"></a>MFC ActiveX 컨트롤: ActiveX 컨트롤에서 데이터 바인딩 사용
ActiveX 컨트롤의 보다 강력한 용도 중 하나는 데이터베이스의 특정 필드와 바인딩하려면 컨트롤의 속성 수 있는 데이터 바인딩입니다. 바인딩된 속성의 데이터를 수정할 때 컨트롤에는 데이터베이스 및 레코드 필드를 업데이트 해야 하는 요청에 알립니다. 데이터베이스에는 다음 요청이 실패 또는 성공 컨트롤에 알립니다.  
  
 이 문서에서는 제어 측면에서의 작업에 설명 합니다. 데이터베이스와 데이터 바인딩 상호 작용을 구현 하는 것은 컨트롤 컨테이너의 책임입니다. 이 설명서의 범위를 벗어납니다 컨테이너의 데이터베이스 상호 작용을 관리 하는 방법. 이 문서의 나머지 부분에서 데이터 바인딩에 대 한 제어를 준비 하는 방법을 설명 합니다.  
  
 ![바인딩된 컨트롤; 데이터 & # 45의 개념적 다이어그램](../mfc/media/vc374v1.gif "vc374v1")  
데이터 바인딩된 컨트롤의 개념적 다이어그램  
  
 `COleControl` 클래스 바인딩 쉬운 작업을 구현 하는 데이터를 구성 하는 두 개의 멤버 함수를 제공 합니다. 첫 번째 함수 [BoundPropertyRequestEdit](../mfc/reference/colecontrol-class.md#boundpropertyrequestedit), 속성 값을 변경할 수 있는 권한을 요청 하는 데 사용 됩니다. [BoundPropertyChanged](../mfc/reference/colecontrol-class.md#boundpropertychanged), 두 번째 함수는 속성 값이 성공적으로 변경 후에 호출 됩니다.  
  
 이 문서에서는 다음 항목을 다룹니다.  
  
-   [바인딩할 수 있는 스톡 속성 만들기](#vchowcreatingbindablestockproperty)  
  
-   [바인딩 가능한 Get/Set 메서드 만들기](#vchowcreatingbindablegetsetmethod)  
  
##  <a name="vchowcreatingbindablestockproperty"></a>바인딩할 수 있는 스톡 속성 만들기  
 더 많이 사용할 수 있습니다 하지만 데이터 바인딩 스톡 속성을 만들 수는 [바인딩 가능한 get/set 메서드에](#vchowcreatingbindablegetsetmethod)합니다.  
  
> [!NOTE]
>  스톡 속성에는 **바인딩 가능한** 및 **requestedit** 기본적으로 특성입니다.  
  
#### <a name="to-add-a-bindable-stock-property-using-the-add-property-wizard"></a>속성 추가 마법사를 사용 하 여 바인딩할 수 있는 스톡 속성을 추가 하려면  
  
1.  사용 하 여 프로젝트 시작의 [MFC ActiveX 컨트롤 마법사](../mfc/reference/mfc-activex-control-wizard.md)합니다.  
  
2.  컨트롤에 대 한 인터페이스 노드를 마우스 오른쪽 단추로 클릭 합니다.  
  
     바로 가기 메뉴를 엽니다.  
  
3.  바로 가기 메뉴에서 클릭 **추가** 클릭 하 고 **속성 추가**합니다.  
  
4.  항목 중 하나를 선택는 **속성 이름** 드롭 다운 목록입니다. 선택할 수는 예를 들어 **텍스트**합니다.  
  
     때문에 **텍스트** 스톡 속성의 **바인딩 가능한** 및 **requestedit** 특성은 이미 확인 합니다.  
  
5.  다음 확인란이 선택 된 **IDL 특성** 탭: **displaybind** 및 **defaultbind** 프로젝트의 속성 정의에 특성을 추가 합니다. IDL 파일입니다. 이러한 특성 컨트롤을 사용자에 게 표시 되도록 설정 및 기본 바인딩 가능 속성 스톡 속성을 확인 합니다.  
  
 이 시점에서 컨트롤에서 데이터 원본에서 데이터를 표시할 수 있지만 사용자 데이터 필드를 업데이트할 수 없습니다. 데이터 업데이트, 변경 수를 제어 하려는 경우는 `OnOcmCommand` [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) 함수를 다음과 같습니다.  
  
 [!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]  
  
 이제 컨트롤을 등록 하는 프로젝트를 빌드할 수 있습니다. 대화 상자에 컨트롤을 삽입 하는 경우는 **데이터 필드** 및 **데이터 원본** 속성은 추가 되 고 이제 데이터 원본 및 컨트롤에 표시할 필드를 선택할 수 있습니다.  
  
##  <a name="vchowcreatingbindablegetsetmethod"></a>바인딩 가능한 Get/Set 메서드 만들기  
 데이터 바인딩 get/set 메서드 외에도 만들 수도 있습니다는 [바인딩할 수 있는 스톡 속성](#vchowcreatingbindablestockproperty)합니다.  
  
> [!NOTE]
>  이 절차는 ActiveX 컨트롤을 서브클래싱하는 Windows 컨트롤 프로젝트 있다고 가정 합니다.  
  
#### <a name="to-add-a-bindable-getset-method-using-the-add-property-wizard"></a>속성 추가 마법사를 사용 하 여 바인딩 가능한 get/set 메서드를 추가 하려면  
  
1.  컨트롤의 프로젝트를 로드합니다.  
  
2.  에 **제어 설정** 페이지에서 컨트롤을 서브 클래스에 대 한 창 클래스를 선택 합니다. 예를 들어 편집 컨트롤 하위 클래스를 지정할 수 있습니다.  
  
3.  컨트롤의 프로젝트를 로드합니다.  
  
4.  컨트롤에 대 한 인터페이스 노드를 마우스 오른쪽 단추로 클릭 합니다.  
  
     바로 가기 메뉴를 엽니다.  
  
5.  바로 가기 메뉴에서 클릭 **추가** 클릭 하 고 **속성 추가**합니다.  
  
6.  에 속성 이름을 입력 된 **속성 이름** 상자입니다. 사용 하 여 `MyProp` 이 예제에 대 한 합니다.  
  
7.  데이터 형식을 선택 된 **속성 형식** 드롭다운 목록 상자입니다. 사용 하 여 **짧은** 이 예제에 대 한 합니다.  
  
8.  **구현 형식**에서 **Get/Set 메서드**를 클릭합니다.  
  
9. IDL 특성 탭에서 다음 확인란을 선택: **바인딩 가능한**, **requestedit**, **displaybind**, 및 **defaultbind** 추가 하려면 프로젝트의 속성 정의에 대 한 특성입니다. IDL 파일입니다. 이러한 특성 컨트롤을 사용자에 게 표시 되도록 설정 및 기본 바인딩 가능 속성 스톡 속성을 확인 합니다.  
  
10. **마침**을 클릭합니다.  
  
11. 본문을 수정 된 `SetMyProp` 함수를 다음 코드를 포함 합니다.  
  
     [!code-cpp[NVC_MFC_AxData#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_2.cpp)]  
  
12. 에 전달 된 매개 변수는 `BoundPropertyChanged` 및 `BoundPropertyRequestEdit` 함수는 매개 변수에서 속성에 대 한 id () 특성에 전달 되는 속성의 경우 dispid가는 합니다. IDL 파일입니다.  
  
13. 수정 된 [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) 함수 이므로 다음 코드를 포함 합니다.  
  
     [!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]  
  
14. 수정 된 `OnDraw` 함수를 다음 코드를 포함 합니다.  
  
     [!code-cpp[NVC_MFC_AxData#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_3.cpp)]  
  
15. 헤더 파일 컨트롤 클래스에 대 한 헤더 파일의 공용 섹션을 멤버 변수에 대 한 다음 정의 (생성자)를 추가 합니다.  
  
     [!code-cpp[NVC_MFC_AxData#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_4.h)]  
  
16. 다음 줄의 마지막 줄에서는 확인 된 `DoPropExchange` 함수:  
  
     [!code-cpp[NVC_MFC_AxData#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_5.cpp)]  
  
17. 수정 된 `OnResetState` 함수를 다음 코드를 포함 합니다.  
  
     [!code-cpp[NVC_MFC_AxData#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_6.cpp)]  
  
18. 수정 된 `GetMyProp` 함수를 다음 코드를 포함 합니다.  
  
     [!code-cpp[NVC_MFC_AxData#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_7.cpp)]  
  
 이제 컨트롤을 등록 하는 프로젝트를 빌드할 수 있습니다. 대화 상자에 컨트롤을 삽입 하는 경우는 **데이터 필드** 및 **데이터 원본** 속성은 추가 되 고 이제 데이터 원본 및 컨트롤에 표시할 필드를 선택할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   

