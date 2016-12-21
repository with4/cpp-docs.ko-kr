---
title: "속성 페이지 추가(ATL 자습서, 6부) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
ms.assetid: df80d255-e7ea-49d9-b940-3f012e90cf9b
caps.latest.revision: 15
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 속성 페이지 추가(ATL 자습서, 6부)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

속성 페이지는 필요에 따라 공유 될 수 있도록 별도 COM 개체로 구현 됩니다.  이 단계에서는 컨트롤에 속성 페이지를 추가 하려면 다음 작업을 수행 합니다.  
  
-   속성 페이지 리소스 만들기  
  
-   작성 하 고 속성 페이지를 관리 하는 코드 추가  
  
-   속성 페이지에 컨트롤 추가  
  
## 속성 페이지 리소스 만들기  
 속성 페이지에 컨트롤을 추가 하려면 ATL 클래스 추가 마법사를 사용 합니다.  
  
#### 속성 페이지를 추가 하려면  
  
1.  솔루션 탐색기에서 다각형을 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  바로 가기 메뉴에서 **추가**를 클릭한 다음 **클래스 추가**를 클릭합니다.  
  
3.  템플릿 목록에서 선택  **ATL 속성 페이지** 를 클릭 하 고  **추가**.  
  
4.  ATL 속성 페이지 마법사 표시 되 면 입력  `PolyProp` 으로  **짧은** 이름입니다.  
  
5.  클릭  **문자열** 열은  **문자열** 페이지를 입력 하 고  **및 다각형** 으로  **제목**.  
  
     **제목** 의 속성 페이지를 해당 페이지의 탭에 표시 되는 문자열입니다.  **문서 문자열** 속성 프레임을 사용 하 여 상태 표시줄이 나 도구 팁에 배치 하는 설명입니다.  참고 기본 내용으로 그대로 둘 수 있습니다 표준 속성 프레임 현재이 문자열을 사용 하지 않는 것입니다.  생성 되지 않습니다는  **도움말 파일** 는 순간에 따라서 텍스트 상자에서 항목을 삭제 합니다.  
  
6.  클릭  **완료**, 및 속성 페이지 개체를 만듭니다.  
  
 다음 세 개의 파일이 만들어집니다.  
  
|파일|설명|  
|--------|--------|  
|PolyProp.h|C \+ \+ 클래스를 포함 합니다. `CPolyProp`, 속성 페이지를 구현 합니다.|  
|PolyProp.cpp|PolyProp.h 파일에 포함 됩니다.|  
|PolyProp.rgs|속성 페이지 개체를 등록 하는 레지스트리 스크립트입니다.|  
  
 다음과 같이 코드 변경도 수행 됩니다.  
  
-   새 속성 페이지가 polygon.cpp의 개체 엔트리 맵에 추가 됩니다.  
  
-   `PolyProp` Polygon.idl 파일에 클래스를 추가 합니다.  
  
-   PolyProp.rgs 새 레지스트리 스크립트 파일을 프로젝트 리소스에 추가 됩니다.  
  
-   프로젝트 리소스에 대 한 속성 페이지 대화 상자 템플릿에 추가 됩니다.  
  
-   지정한 속성 문자열 리소스 문자열 테이블에 추가 됩니다.  
  
 이제 속성 페이지에 표시 하려는 필드를 추가 합니다.  
  
#### 속성 페이지에 필드를 추가 하려면  
  
1.  솔루션 탐색기에서 Polygon.rc 리소스 파일을 두 번 클릭 합니다.  그러면 리소스 뷰가 열립니다.  
  
2.  리소스 뷰에서 대화 상자 노드를 확장 하 고 IDD\_POLYPROP를 두 번 클릭.  참고 표시 되는 대화 상자 컨트롤을 삽입 하 라는 레이블을 제외한 비어 있습니다.  
  
3.  해당 레이블을 선택 하 고 읽을 수 변경  `면:` 변경의  **캡션** 텍스트는  **속성** 창.  
  
4.  텍스트의 크기에 맞도록 레이블 상자 크기를 조정 합니다.  
  
5.  편집 컨트롤을 도구 상자에서 레이블 오른쪽으로 끕니다.  
  
6.  마지막으로 변경 된  **ID** 편집 컨트롤의  `IDC_SIDES` 속성 창을 사용 하 여.  
  
 속성 페이지 리소스를 만드는 프로세스를 완료 합니다.  
  
## 작성 하 고 속성 페이지를 관리 하는 코드 추가  
 속성 페이지 리소스를 만든 이제 구현 코드를 작성 해야 합니다.  
  
 먼저 사용은 `CPolyProp` 개체에서 변의 수를 설정 하는 클래스 때의  **적용** 단추를 누를.  
  
#### 변의 수를 설정할 수 있도록 Apply 함수를 수정 하려면  
  
1.  대체는 `Apply` Polyprop.h에서 함수에 다음 코드를:  
  
     [!code-cpp[NVC_ATL_Windowing#58](../atl/codesnippet/CPP/adding-a-property-page-atl-tutorial-part-6_1.h)]  
  
 속성 페이지 연결 한 번에 둘 이상의 클라이언트가 있을 수 있습니다 때문에 `Apply` 반복 실행 하 고 호출 하는 함수 `put_Sides` 검색 편집 상자에서 값을 각 클라이언트에.  사용 하는  [CComQIPtr](../atl/reference/ccomqiptr-class.md) 수행 하는 클래스는 `QueryInterface` 얻으려면 각 개체에는 `IPolyCtl` 인터페이스에서 **IUnknown** 인터페이스 \(저장은 `m_ppUnk` 배열\).  
  
 코드는 이제 해당 설정을 확인은 `Sides` 속성을 실제로 작동 합니다.  실패할 경우 코드에서 오류 정보를 표시 하는 메시지 상자 표시는 **IErrorInfo** 인터페이스.  컨테이너 개체에 대 한 요청 하는 일반적으로 **ISupportErrorInfo** 인터페이스와 호출 `InterfaceSupportsErrorInfo` 개체 설정 오류 정보를 지원 하는지 확인 하려면 먼저 합니다.  이 작업을 건너뛸 수 있습니다.  
  
 [CComPtr](../atl/reference/ccomptr-class.md) 를 호출 하지 않아도 되므로 참조 횟수를 자동으로 처리 함으로써 수 `Release` 인터페이스.  `CComBSTR`사용 하면 `BSTR` 최종 수행 하지 않고도 처리 `SysFreeString` 를 호출 합니다.  변환할 수 있도록 또한 중 다양 한 문자열 변환 클래스를 사용 하면의 `BSTR` 필요한 경우 \(이유가는 `USES_CONVERSION` 매크로 함수를 시작할 때입니다\).  
  
 나타내기 위해 속성 페이지의 더티 플래그를 설정 해야 할 수도 있는  **적용** 단추를 활성화 합니다.  이런 사용자의 값이 변경 되는  **면** 편집 상자.  
  
#### 적용 단추를 처리 하려면  
  
1.  클래스 뷰에서 CPolyProp 마우스 오른쪽 단추로 클릭 하 고  **속성** 바로 가기 메뉴에서.  
  
2.  속성 창에서 클릭 하 여  **이벤트** 아이콘.  
  
3.  확장 된 `IDC_SIDES` 노드는 이벤트 목록입니다.  
  
4.  선택 `EN_CHANGE`, 오른쪽의 드롭다운 메뉴를 클릭 하 고  **\<Add\> OnEnChangeSides**.  `OnEnChangeSides` , Polyprop.h 및 polyprop.cpp는 처리기 구현 처리기 선언을 추가 합니다.  
  
 그런 다음 처리기를 수정 합니다.  
  
#### OnEnChangeSides 메서드를 수정.  
  
1.  Polyprop.cpp에 다음 코드를 추가 된 `OnEnChangeSides` 메서드 \(마법사 포함 시킨 모든 코드를 삭제\).  
  
     [!code-cpp[NVC_ATL_Windowing#59](../atl/codesnippet/CPP/adding-a-property-page-atl-tutorial-part-6_2.cpp)]  
  
 `OnEnChangeSides`호출 될 때는 **WM\_COMMAND** 메시지에 **EN\_CHANGE** 알림을 `IDC_SIDES` 컨트롤.  `OnEnChangeSides`다음 호출 `SetDirty` 전달 `TRUE` 속성이 나타내는 페이지가 이제 커밋되지 않은 및  **적용** 단추가 활성화 합니다.  
  
## 속성 페이지에 컨트롤 추가  
 프로젝트에 컨트롤을 여러 개 있을 수 있기 때문 ATL 클래스 추가 마법사 및 ATL 속성 페이지 마법사 속성 페이지에 컨트롤을 자동으로 추가 하지 마십시오.  컨트롤의 속성 맵에 엔트리를 추가 해야 합니다.  
  
#### 속성 페이지를 추가 하려면  
  
1.  Polyctl.h를 열고 속성 맵에 다음이 줄을 추가 합니다.  
  
     [!code-cpp[NVC_ATL_Windowing#60](../atl/codesnippet/CPP/adding-a-property-page-atl-tutorial-part-6_3.h)]  
  
 이제 컨트롤의 속성 맵이 다음과 같이 나타납니다.  
  
 [!code-cpp[NVC_ATL_Windowing#61](../atl/codesnippet/CPP/adding-a-property-page-atl-tutorial-part-6_4.h)]  
  
 추가한 수는 `PROP_PAGE` 매크로를 제외 하면 속성 페이지의 CLSID는 `PROP_ENTRY` 같이 매크로 `Sides` 컨트롤을 저장할 때 속성 값이 저장도.  
  
 매크로 세 개의 매개 변수는 속성의 DISPID 및 CLSID 속성이 있는 속성 페이지의 속성 설명입니다.  예를 들어, Visual Basic 해당 컨트롤을 로드 하 고 변의 수를 디자인 타임에 설정 하는 경우에 유용 합니다.  변의 수 Visual Basic 프로젝트를 다시 로드 하면 변의 수를 저장 하기 때문에 복원 됩니다.  
  
## 빌드 및 컨트롤 테스트  
 이제 해당 컨트롤을 빌드 및 ActiveX 컨트롤 테스트 컨테이너에 삽입 합니다.  테스트 컨테이너에서에 있는  **편집** 메뉴를 클릭  **PolyCtl 클래스 개체**.  속성 페이지에 표시 됩니다. 클릭 하 여  **다각형** 탭.  
  
 **적용** 처음에 단추가 비활성화 됩니다.  입력 값에는  **면** 상자 및  **적용** 단추를 사용할 수 없게 됩니다.  값을 입력 한 후 클릭 된  **적용** 단추.  컨트롤 표시 변경 및  **적용** 단추는 다시 비활성화 됩니다.  잘못 된 값을 입력 하십시오.  설정에서 오류 설명을 포함 하는 메시지 상자를 볼 수 있는 `put_Sides` 함수.  
  
 그런 다음 웹 페이지에 컨트롤을 배치 합니다.  
  
 [5 단계로 다시](../atl/adding-an-event-atl-tutorial-part-5.md) &#124; [7 단계](../atl/putting-the-control-on-a-web-page-atl-tutorial-part-7.md)  
  
## 참고 항목  
 [자습서](../atl/active-template-library-atl-tutorial.md)