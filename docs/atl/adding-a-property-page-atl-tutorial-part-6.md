---
title: 속성 페이지 (ATL 자습서, 6 부) 추가 | Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: df80d255-e7ea-49d9-b940-3f012e90cf9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 32b89b36318800ff35bc78fee35f094f75bdf36e
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848693"
---
# <a name="adding-a-property-page-atl-tutorial-part-6"></a>속성 페이지 추가(ATL 자습서, 6부)
속성 페이지는 필요한 경우 공유할 수 있도록 별도 COM 개체로 구현 됩니다. 이 단계에서는 컨트롤에 속성 페이지를 추가 하려면 다음 작업을 수행 합니다.  
  
-   속성 페이지 리소스 만들기  
  
-   속성 페이지를 만들고 코드를 추가 합니다.  
  
-   컨트롤에 속성 페이지 추가  
  
## <a name="creating-the-property-page-resource"></a>속성 페이지 리소스 만들기  
 속성 페이지에 컨트롤을 추가할 ATL 클래스 추가 마법사를 사용 합니다.  
  
#### <a name="to-add-a-property-page"></a>속성 페이지를 추가 하려면  
  
1.  솔루션 탐색기에서 다각형을 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  바로 가기 메뉴에서 클릭 **추가**를 클릭 하 고 **클래스 추가**합니다.  
  
3.  템플릿 목록에서 선택 **ATL 속성 페이지** 누릅니다 **추가**합니다.  
  
4.  ATL 속성 페이지 마법사가 나타나면 입력 *PolyProp* 으로 **짧은** 이름입니다.  
  
5.  클릭 **문자열** 열려는 합니다 **문자열** 페이지 및 입력 **& 다각형** 으로 **제목**합니다.  
  
     합니다 **Title** 속성의 페이지는 해당 페이지의 탭에 표시 되는 문자열입니다. 합니다 **Doc 문자열** 상태 줄 또는 도구 설명에 적용할 속성 프레임을 사용 하는 설명입니다. 참고는 표준 속성 프레임에서 현재 사용 하지 않으므로이 문자열 기본 내용이 포함 된 상태로 남겨둘 수 있습니다. 생성 하지 것입니다는 **도움말 파일** 지금은 되므로 해당 텍스트 상자에 항목을 삭제 합니다.  
  
6.  클릭 **완료**, 속성 페이지 개체 생성 됩니다.  
  
 다음 세 개의 파일이 만들어집니다.  
  
|파일|설명|  
|----------|-----------------|  
|PolyProp.h|C + + 클래스를 포함 `CPolyProp`, 속성 페이지를 구현 하는 합니다.|  
|PolyProp.cpp|PolyProp.h 파일이 포함 됩니다.|  
|PolyProp.rgs|속성 페이지 개체를 등록 하는 레지스트리 스크립트입니다.|  
  
 코드 변경도 수행 됩니다.  
  
-   새 속성 페이지 Polygon.cpp의 개체 항목 맵에 추가 됩니다.  
  
-   `PolyProp` 클래스를 마우스 오른쪽 단추로 Polygon.idl 파일에 추가 됩니다.  
  
-   새 레지스트리 스크립트 파일 PolyProp.rgs 프로젝트 리소스에 추가 됩니다.  
  
-   프로젝트 리소스 속성 페이지 대화 상자 템플릿에 추가 됩니다.  
  
-   지정 된 속성 문자열 리소스 문자열 테이블에 추가 됩니다.  
  
 이제 속성 페이지에 표시 하려는 필드를 추가 합니다.  
  
#### <a name="to-add-fields-to-the-property-page"></a>속성 페이지에 필드를 추가 하려면  
  
1.  솔루션 탐색기에서 Polygon.rc 리소스 파일을 두 번 클릭 합니다. 리소스 뷰 열립니다.  
  
2.  리소스 뷰에서 대화 상자 노드를 확장 하 고 IDD_POLYPROP를 두 번 클릭 합니다. 여기에 컨트롤을 삽입 하 라고 지시 하는 레이블을 제외 하 고 비어 대화 상자가 표시 되는 참고 합니다.  
  
3.  해당 레이블을 선택 하 고 변경 `Sides:` 변경 하 여 합니다 **캡션** 에서 텍스트를 **속성** 창입니다.  
  
4.  텍스트의 크기에 맞도록 레이블 상자 크기를 조정 합니다.  
  
5.  레이블의 오른쪽에 도구 상자에서 편집 컨트롤을 끕니다.  
  
6.  마지막으로 변경 합니다 **ID** 편집 컨트롤의 `IDC_SIDES` 속성 창을 사용 합니다.  
  
 이 속성 페이지 리소스를 만드는 과정을 완료 합니다.  
  
## <a name="adding-code-to-create-and-manage-the-property-page"></a>속성 페이지를 만들고 코드를 추가 합니다.  
 속성 페이지 리소스를 만들었으므로 이제 구현 코드를 작성 해야 합니다.  
  
 먼저 사용 하도록 설정 합니다 `CPolyProp` 개체에서 면의 수를 설정 하는 클래스 때 합니다 **적용** 단추가 눌러져 합니다.  
  
#### <a name="to-modify-the-apply-function-to-set-the-number-of-sides"></a>양쪽의 수를 설정 하려면 적용 함수를 수정 하려면  
  
1.  대체는 `Apply` PolyProp.h에서 함수를 다음 코드로 바꿉니다.  
  
     [!code-cpp[NVC_ATL_Windowing#58](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_1.h)]  
  
 속성 페이지를 한 번에 연결 된 둘 이상의 클라이언트가 있을 수 있습니다 때문 `Apply` 함수는 루프를 실행 하 고 호출 `put_Sides` 값을 사용 하 여 각 클라이언트에서 편집 상자에서 검색 합니다. 사용 하는 합니다 [CComQIPtr](../atl/reference/ccomqiptr-class.md) 수행 하는 클래스를 `QueryInterface` 가져올 각 개체에는 `IPolyCtl` 에서 인터페이스를 `IUnknown` 인터페이스 (에 저장 된는 `m_ppUnk` 배열).  
  
 코드는 이제 해당 설정을 확인 합니다 `Sides` 실제로 작동 하는 속성입니다. 실패 한 경우 코드에서 오류 세부 정보 표시 메시지 상자를 표시 합니다 `IErrorInfo` 인터페이스입니다. 컨테이너에 대 한 개체를 요청 하는 일반적으로 `ISupportErrorInfo` 인터페이스 및 호출 `InterfaceSupportsErrorInfo` 먼저 개체 설정 오류 정보를 지원 하는지 여부를 확인 합니다. 이 작업을 건너뛸 수 있습니다.  
  
 [CComPtr](../atl/reference/ccomptr-class.md) 를 사용 하면 자동으로 계산을 처리 하 여 호출 해야 하므로 `Release` 인터페이스에 있습니다. `CComBSTR` 지 원하는 BSTR 처리의 마지막으로 수행 해야 하므로 `SysFreeString` 호출 합니다. 또한 중 하나를 사용의 다양 한 문자열 변환 클래스 (따라가 함수 시작 하는 이유는) 필요한 경우에 BSTR를 변환할 수 있도록 합니다.  
  
 나타내는 속성 페이지의 변경 플래그를 설정 해야 합니다 **적용** 단추를 사용 해야 합니다. 이 사용자의 값을 변경할 때 발생 합니다 **양쪽** 편집 상자입니다.  
  
#### <a name="to-handle-the-apply-button"></a>적용 단추 처리 하려면  
  
1.  클래스 뷰에서 CPolyProp를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성** 바로 가기 메뉴.  
  
2.  속성 창에서 클릭 합니다 **이벤트** 아이콘입니다.  
  
3.  확장 된 `IDC_SIDES` 노드 이벤트 목록입니다.  
  
4.  선택 `EN_CHANGE`를 오른쪽에 드롭다운 메뉴에서 클릭  **\<추가 > OnEnChangeSides**합니다. `OnEnChangeSides` 처리기 선언 Polyprop.h, 및 Polyprop.cpp 처리기 구현에 추가 됩니다.  
  
 그런 다음 처리기를 수정 합니다.  
  
#### <a name="to-modify-the-onenchangesides-method"></a>OnEnChangeSides 메서드를 수정 하려면  
  
1.  Polyprop.cpp 하에서 다음 코드를 추가 합니다 `OnEnChangeSides` 메서드 (삭제 마법사를 저장 하는 코드):  
  
     [!code-cpp[NVC_ATL_Windowing#59](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_2.cpp)]  
  
 `OnEnChangeSides` EN_CHANGE 알림을 사용 하 여 WM_COMMAND 메시지를 보낼 때 호출 되는 `IDC_SIDES` 제어 합니다. `OnEnChangeSides` 다음 호출 `SetDirty` 속성 페이지를 더티 되었습니다 나타내려면 TRUE를 전달 하며 **적용** 단추가 활성화 되어야 합니다.  
  
## <a name="adding-the-property-page-to-the-control"></a>컨트롤에 속성 페이지 추가  
 ATL 클래스 추가 마법사 및 ATL 속성 페이지 마법사 추가 하지 마십시오 속성 페이지 컨트롤에를 자동으로 프로젝트에서 여러 컨트롤 수 있습니다. 컨트롤의 속성 맵에 항목을 추가 해야 합니다.  
  
#### <a name="to-add-the-property-page"></a>속성 페이지를 추가 하려면  
  
1.  PolyCtl.h 열고 속성 맵에이 줄을 추가 합니다.  
  
     [!code-cpp[NVC_ATL_Windowing#60](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_3.h)]  
  
 이제 컨트롤의 속성 맵에 모양은 다음과 같습니다.  
  
 [!code-cpp[NVC_ATL_Windowing#61](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_4.h)]  
  
 속성 페이지에 표시 된 대로 PROP_ENTRY 매크로 사용 하는 경우 있지만 CLSID 사용 하 여 PROP_PAGE 매크로 추가할 수는 `Sides` 컨트롤을 저장할 때 속성 값도 저장 됩니다.  
  
 매크로에 세 개의 매개 변수는 속성의 DISPID 및 속성에는 속성 페이지의 CLSID 속성 설명 합니다. Visual Basic 컨트롤을 로드 하 고 디자인 타임에 면의 수를 설정 하는 예를 들어 하는 경우에 유용 합니다. Visual Basic 프로젝트를 다시 로드 하면 변 수가 저장 되므로, 변 수가 복원 됩니다.  
  
## <a name="building-and-testing-the-control"></a>빌드 및 컨트롤 테스트  
 이제 빌드를 제어 하는 ActiveX Control Test Container를 삽입 합니다. 테스트 컨테이너에서에 **편집** 메뉴에서 클릭 **PolyCtl 클래스 개체**합니다. 속성 페이지에 표시 됩니다. 클릭 합니다 **다각형** 탭 합니다.  
  
 합니다 **적용** 단추가 처음에 비활성화 됩니다. 값을 입력 하기 시작 합니다 **양쪽** 상자와 **적용** 단추가 사용 가능해 집니다. 값 입력을 완료 한 후 클릭 합니다 **적용** 단추입니다. 컨트롤 표시 변경 하며 **적용** 단추 다시 사용할 수 없습니다. 잘못 된 값을 입력 하십시오. 설정 하는 오류 설명을 포함 하는 메시지 상자가 표시 됩니다는 `put_Sides` 함수입니다.  
  
 다음으로, 웹 페이지에 컨트롤을 추가 합니다.  
  
 [5 단계를 다시](../atl/adding-an-event-atl-tutorial-part-5.md) &#124; [7 단계로 이동 합니다.](../atl/putting-the-control-on-a-web-page-atl-tutorial-part-7.md)  
  
## <a name="see-also"></a>참고 항목  
 [자습서](../atl/active-template-library-atl-tutorial.md)

