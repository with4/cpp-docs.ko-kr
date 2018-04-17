---
title: 속성 페이지 (ATL 자습서, 6 부) 추가 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: get-started-article
dev_langs:
- C++
ms.assetid: df80d255-e7ea-49d9-b940-3f012e90cf9b
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 067c5d662fee3838a33a3b53fd5dab2946ab50cf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-a-property-page-atl-tutorial-part-6"></a>속성 페이지 추가(ATL 자습서, 6부)
속성 페이지는 필요한 경우를 공유할 수 있도록 별도 COM 개체로 구현 됩니다. 이 단계에서는 컨트롤에 속성 페이지를 추가 하려면 다음 작업을 수행 합니다.  
  
-   속성 페이지 리소스 만들기  
  
-   만들기 및 속성 페이지를 관리 하는 코드 추가  
  
-   컨트롤에 속성 페이지 추가  
  
## <a name="creating-the-property-page-resource"></a>속성 페이지 리소스 만들기  
 속성 페이지에 있는 컨트롤을 추가 하려면 ATL 클래스 추가 마법사를 사용 합니다.  
  
#### <a name="to-add-a-property-page"></a>속성 페이지를 추가 하려면  
  
1.  솔루션 탐색기에서 다각형을 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  바로 가기 메뉴를 클릭 **추가**, 클릭 하 고 **클래스 추가**합니다.  
  
3.  템플릿 목록에서 선택 **ATL 속성 페이지** 클릭 **추가**합니다.  
  
4.  ATL 속성 페이지 마법사가 나타나면 입력 `PolyProp` 로 **짧은** 이름입니다.  
  
5.  클릭 **문자열** 열려는 **문자열** 페이지 및 입력 **& 다각형** 로 **제목**합니다.  
  
     **제목** 속성의 페이지는 해당 페이지의 탭에 표시 되는 문자열입니다. **문서 문자열** 속성 프레임을 사용 하 여 상태 표시줄이 나 도구 설명에 대 한 설명입니다. 참고는 표준 속성 프레임에서 현재 사용 하지 않습니다이 문자열 기본 내용으로 둘 수 있도록 합니다. 생성 하지 것입니다는 **도움말 파일** 현재 해당 텍스트 상자에 항목을 삭제 되므로 합니다.  
  
6.  클릭 **마침**, 속성 페이지 개체 생성 됩니다.  
  
 다음 세 파일이 생성 됩니다.  
  
|파일|설명|  
|----------|-----------------|  
|PolyProp.h|C + + 클래스가 포함 되어 `CPolyProp`, 속성 페이지를 구현 하는 합니다.|  
|PolyProp.cpp|PolyProp.h 파일이 포함 됩니다.|  
|PolyProp.rgs|속성 페이지 개체를 등록 하는 레지스트리 스크립트입니다.|  
  
 다음 코드도 변경 됩니다.  
  
-   새 속성 페이지에서 Polygon.cpp 개체 항목 맵은에 추가 됩니다.  
  
-   `PolyProp` 클래스를 마우스 오른쪽 단추로 Polygon.idl 파일에 추가 합니다.  
  
-   새 레지스트리 스크립트 파일 PolyProp.rgs 프로젝트 리소스에 추가 됩니다.  
  
-   대화 상자 템플릿에 속성 페이지에 대 한 프로젝트 리소스에 추가 됩니다.  
  
-   지정한 속성 문자열 리소스 문자열 테이블에 추가 됩니다.  
  
 이제 속성 페이지에 표시 하려는 필드를 추가 합니다.  
  
#### <a name="to-add-fields-to-the-property-page"></a>속성 페이지에 필드를 추가 하려면  
  
1.  솔루션 탐색기에서 Polygon.rc 리소스 파일을 두 번 클릭 합니다. 리소스 뷰 열립니다.  
  
2.  리소스 뷰에서 대화 노드를 확장 하 고 IDD_POLYPROP를 두 번 클릭 합니다. 표시 되는 대화 상자를 제외 하 고 여기에 컨트롤을 삽입할 수를 알려 주는 레이블 비어 있는지 확인 합니다.  
  
3.  해당 레이블을 선택 하 고 읽을 변경 `Sides:` 변경 하 여는 **캡션** 의 텍스트는 **속성** 창.  
  
4.  텍스트의 크기에 맞도록 레이블 상자 크기를 조정 합니다.  
  
5.  도구 상자에서 편집 컨트롤을 레이블 오른쪽으로 끕니다.  
  
6.  마지막으로 변경 된 **ID** 편집 컨트롤의 `IDC_SIDES` 속성 창을 사용 하 여 합니다.  
  
 속성 페이지 리소스를 만드는 과정을 완료 합니다.  
  
## <a name="adding-code-to-create-and-manage-the-property-page"></a>만들기 및 속성 페이지를 관리 하는 코드 추가  
 속성 페이지 리소스를 만든 구현 코드를 작성 해야 합니다.  
  
 먼저, 사용 하도록 설정는 `CPolyProp` 클래스 개체에 양쪽의 수를 설정 하려면 때는 **적용** 단추가 눌려질 합니다.  
  
#### <a name="to-modify-the-apply-function-to-set-the-number-of-sides"></a>양쪽의 수를 설정 하려면 적용 함수를 수정 하려면  
  
1.  대체는 `Apply` PolyProp.h에서 함수를 다음 코드로:  
  
     [!code-cpp[NVC_ATL_Windowing#58](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_1.h)]  
  
 속성 페이지에는 한 번에 연결 된 클라이언트가 여러 개 있을 수 있습니다 하므로 `Apply` 함수는 루프를 실행 하 고 호출 `put_Sides` 값을 사용 하 여 각 클라이언트에는 편집 상자에서 검색 합니다. 사용 하는 [CComQIPtr](../atl/reference/ccomqiptr-class.md) 수행 하는 클래스는 `QueryInterface` 가져올 각 개체에는 `IPolyCtl` 에서 인터페이스는 **IUnknown** 인터페이스 (에 저장 된는 `m_ppUnk` 배열)입니다.  
  
 이 코드는 이제 해당 설정을 검사는 `Sides` 실제로 작동 하는 속성입니다. 실패 한 경우 코드에서 오류 세부 정보 표시 메시지 상자를 표시 하는 **IErrorInfo** 인터페이스입니다. 컨테이너에 대 한 개체를 요청 하는 일반적으로 **ISupportErrorInfo** 인터페이스 및 호출 `InterfaceSupportsErrorInfo` 먼저 개체가 설정 오류 정보를 지원 하는지 여부를 확인 합니다. 이 태스크를 건너뛸 수 있습니다.  
  
 [CComPtr](../atl/reference/ccomptr-class.md) 를 사용 하면 참조 횟수를 자동으로 처리 하 여 되므로 호출 하지 않고도 `Release` 인터페이스에 있습니다. `CComBSTR`사용 하면 `BSTR` 처리의 마지막으로 수행 해야 하므로 `SysFreeString` 호출 합니다. 또한 중 하나를 사용할 다양 한 문자열 변환 클래스를 변환할 수 있도록는 `BSTR` 필요한 경우 (이 인해는 `USES_CONVERSION` 매크로 함수의 시작 부분에).  
  
 속성 페이지의 해당 변경 플래그를 설정 해야는 **적용** 단추가 활성화 되어야 합니다. 사용자의 값을 변경할 때 발생 하는이 **면** 상자 편집 합니다.  
  
#### <a name="to-handle-the-apply-button"></a>적용 단추 처리  
  
1.  클래스 뷰에서 CPolyProp를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성** 바로 가기 메뉴.  
  
2.  속성 창에서 클릭 된 **이벤트** 아이콘입니다.  
  
3.  확장 된 `IDC_SIDES` 노드 이벤트 목록입니다.  
  
4.  선택 `EN_CHANGE`, 오른쪽 드롭 다운 메뉴에서 클릭 하 고  **\<추가 > OnEnChangeSides**합니다. `OnEnChangeSides` 처리기 선언 Polyprop.h, 및 Polyprop.cpp 처리기 구현에 추가 됩니다.  
  
 다음으로 처리기를 수정 합니다.  
  
#### <a name="to-modify-the-onenchangesides-method"></a>OnEnChangeSides 방법을 수정 하려면  
  
1.  에 Polyprop.cpp에 다음 코드를 추가 `OnEnChangeSides` 메서드 (없음에도 마법사는 모든 코드 삭제):  
  
     [!code-cpp[NVC_ATL_Windowing#59](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_2.cpp)]  
  
 `OnEnChangeSides`호출 됩니다는 **WM_COMMAND** 메시지와 함께 보내집니다는 **EN_CHANGE** 에 대 한 알림을 `IDC_SIDES` 제어 합니다. `OnEnChangeSides`그런 다음 호출 `SetDirty` 전달 `TRUE` 속성을 나타내기 위해 페이지가 이제 커밋되지 않았는지 및 **적용** 단추가 활성화 되어야 합니다.  
  
## <a name="adding-the-property-page-to-the-control"></a>컨트롤에 속성 페이지 추가  
 ATL 클래스 추가 마법사 및 ATL 속성 페이지 마법사 추가 하지 마십시오 속성 페이지에 있는 컨트롤을 자동으로 프로젝트에서 하는 컨트롤을 여러 개 있을 수 있기 때문. 컨트롤의 속성 매핑이 두에 항목을 추가 해야 합니다.  
  
#### <a name="to-add-the-property-page"></a>속성 페이지를 추가 하려면  
  
1.  PolyCtl.h 열고 속성 맵에이 줄을 추가 합니다.  
  
     [!code-cpp[NVC_ATL_Windowing#60](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_3.h)]  
  
 컨트롤의 속성 매핑이 두는 이제 다음과 같이 보입니다.  
  
 [!code-cpp[NVC_ATL_Windowing#61](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_4.h)]  
  
 추가할 수는 `PROP_PAGE` 있지만 사용 하는 경우 속성 페이지의 clsid 매크로 `PROP_ENTRY` 표시 된 대로 매크로 `Sides` 속성 값이 컨트롤을 저장할 때에 저장 됩니다.  
  
 매크로에 세 개의 매개 변수는 속성의 경우 DISPID 및 속성에는 속성 페이지의 CLSID 속성 설명 합니다. 예를 들어 Visual Basic로 컨트롤을 로드 하 고 디자인 타임에 면 수를 설정한 경우에 유용 합니다. Visual Basic 프로젝트를 다시 로드 하면 면 수 저장 되므로, 면 수 복원 됩니다.  
  
## <a name="building-and-testing-the-control"></a>빌드 및 컨트롤 테스트  
 이제 해당 컨트롤을 빌드하고 ActiveX Control Test Container에 삽입 합니다. 테스트 컨테이너에에 **편집** 메뉴를 클릭 하 여 **PolyCtl 클래스 개체**합니다. 속성 페이지가 나타납니다. 클릭는 **다각형** 탭 합니다.  
  
 **적용** 단추를 처음으로 사용할 수 있습니다. 값을 입력 하기 시작는 **면** 상자 및 **적용** 단추가 사용 가능해 집니다. 값 입력을 완료 한 후 클릭는 **적용** 단추입니다. 컨트롤 표시 변경 내용이 고 **적용** 단추 다시 사용할 수 없습니다. 잘못 된 값을 입력 하십시오. 설정 하는 오류 설명을 포함 하는 메시지 상자가 표시 됩니다는 `put_Sides` 함수입니다.  
  
 다음으로, 웹 페이지에 컨트롤을 추가 합니다.  
  
 [5 단계를 다시](../atl/adding-an-event-atl-tutorial-part-5.md) &#124; [7 단계로](../atl/putting-the-control-on-a-web-page-atl-tutorial-part-7.md)  
  
## <a name="see-also"></a>참고 항목  
 [자습서](../atl/active-template-library-atl-tutorial.md)

