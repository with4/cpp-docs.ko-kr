---
title: 'MFC ActiveX 컨트롤: 속성 페이지 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DDP_ functions [MFC]
- MFC ActiveX controls [MFC], properties
- property pages [MFC], MFC ActiveX controls
- DoDataExchange method [MFC]
- OLEIVERB_PROPERTIES
- CPropertyPageDialog class [MFC]
- MFC ActiveX controls [MFC], property pages
ms.assetid: 1506f87a-9fd6-4505-8380-0dbc9636230e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 23f8aaf1e485d7ba38a561639f81b36d494a98f2
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930435"
---
# <a name="mfc-activex-controls-property-pages"></a>MFC ActiveX 컨트롤: 속성 페이지
속성 페이지 보기 및 ActiveX 컨트롤 속성을 변경 하는 ActiveX 컨트롤 사용자를 사용 합니다. 이러한 속성 보기 및 편집 컨트롤 속성에 대 한 사용자 지정,이 그래픽 인터페이스를 제공 하는 하나 이상의 속성 페이지를 포함 하는 컨트롤 속성 대화 상자를 호출 하 여 액세스 됩니다.  
  
 ActiveX 컨트롤 속성 페이지는 두 가지 방법으로 표시 됩니다.  
  
-   때 컨트롤의 Properties 동사 (**OLEIVERB_PROPERTIES**)은 호출 컨트롤 컨트롤의 속성 페이지를 포함 하는 모달 속성 대화 상자를 엽니다.  
  
-   컨테이너 선택 된 컨트롤의 속성 페이지를 표시 하는 자체 모덜리스 대화 상자를 표시할 수 있습니다.  
  
 현재 속성 페이지에서 속성 페이지 및 속성 페이지 대화 상자를 닫기 등의 일반적인 작업을 수행 하는 단추의 컬렉션 간 전환에 대 한 탭을 표시 하기 위한 영역 이루어져 있습니다 (다음 그림에 표시 된) 속성 대화 상자 변경 된 내용을, 취소 또는 ActiveX 컨트롤에 변경 내용을 즉시 적용 합니다.  
  
 ![Circ3 속성 대화 상자](../mfc/media/vc373i1.gif "vc373i1")  
속성 대화 상자  
  
 이 문서에서는 ActiveX 컨트롤에서 속성 페이지를 사용 하 여 관련 된 항목에 설명 합니다. 여기에는 다음이 포함됩니다.  
  
-   [ActiveX 컨트롤에 대 한 기본 속성 페이지를 구현합니다.](#_core_implementing_the_default_property_page)  
  
-   [속성 페이지에 컨트롤 추가](#_core_adding_controls_to_a_property_page)  
  
-   [DoDataExchange 함수를 사용자 지정](#_core_customizing_the_dodataexchange_function)  
  
 ActiveX 컨트롤의 속성 페이지 사용에 대 한 자세한 내용은 다음 문서를 참조 합니다.  
  
-   [MFC ActiveX 컨트롤: 다른 사용자 지정 속성 페이지 추가](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)  
  
-   [MFC ActiveX 컨트롤: 스톡 속성 페이지 사용](../mfc/mfc-activex-controls-using-stock-property-pages.md)  
  
 ActiveX 컨트롤 이외의 MFC 응용 프로그램에서 속성 시트를 사용 하는 방법은 참조 하십시오. [속성 시트](../mfc/property-sheets-mfc.md)합니다.  
  
##  <a name="_core_implementing_the_default_property_page"></a> 기본 속성 페이지를 구현합니다.  
 ActiveX 컨트롤 마법사에서 파생 된 컨트롤에 대 한 기본 속성 페이지 클래스 제공 ActiveX 컨트롤 마법사를 사용 하 여 제어 프로젝트를 만드는 [COlePropertyPage 클래스](../mfc/reference/colepropertypage-class.md)합니다. 처음에이 속성 페이지는 비어 있지만 모든 대화 상자 컨트롤 또는 컨트롤 집합에 추가할 수 있습니다. ActiveX 컨트롤 마법사는 기본적으로 추가 속성 페이지 클래스 하나만 속성 페이지 클래스를 만들기 때문에 (또한에서 파생 `COlePropertyPage`) 클래스 뷰를 사용 하 여 만들어야 합니다. 이 절차에 대 한 자세한 내용은 참조 하십시오. [MFC ActiveX 컨트롤: 다른 사용자 지정 속성 페이지 추가](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)합니다.  
  
 속성 구현 (이 경우 기본값)에서 페이지 세 단계로 구성 됩니다.  
  
#### <a name="to-implement-a-property-page"></a>속성 페이지를 구현 하려면  
  
1.  추가 `COlePropertyPage`-컨트롤 프로젝트에 클래스를 파생 합니다. 프로젝트를 만들어진 경우 (예:이 경우) ActiveX 컨트롤 마법사를 사용 하 여 기본 속성 페이지 클래스 이미 있습니다.  
  
2.  대화 상자 편집기를 사용 하 여 속성 페이지 서식 파일에 컨트롤을 추가 합니다.  
  
3.  사용자 지정의 `DoDataExchange` 의 함수는 `COlePropertyPage`-속성 페이지 컨트롤 및 ActiveX 컨트롤 간의 값을 교환 하는 클래스를 파생 합니다.  
  
 예를 들어 다음 절차에서는 ("Sample" 이라는) 하는 간단한 컨트롤을 사용 합니다. ActiveX 컨트롤 마법사를 사용 하 여 만들어진 샘플과 스톡 Caption 속성을 포함 합니다.  
  
##  <a name="_core_adding_controls_to_a_property_page"></a> 속성 페이지에 컨트롤 추가  
  
#### <a name="to-add-controls-to-a-property-page"></a>속성 페이지에 컨트롤을 추가 하려면  
  
1.  컨트롤 프로젝트를 열고, 리소스 보기를 엽니다.  
  
2.  두 번 클릭 하 고 **대화** 디렉터리 아이콘입니다.  
  
3.  IDD_PROPPAGE_SAMPLE 대화 상자를 엽니다.  
  
     ActiveX 컨트롤 마법사는 대화 ID,이 경우 샘플의 끝에 프로젝트의 이름을 추가합니다.  
  
4.  도구 상자 대화 상자의 영역으로 선택한 컨트롤을 끌어서 설정.  
  
5.  이 예제에서는 텍스트 레이블 컨트롤 "캡션:" 및 편집 상자 컨트롤 IDC_CAPTION 식별자로는 충분 합니다.  
  
6.  클릭 **저장** 변경 내용을 저장 하려면 도구 모음에서 합니다.  
  
 사용자 인터페이스 수정 했으므로 해당 입력란 Caption 속성을 연결 해야 합니다. 편집 하 여 다음 섹션에서 이렇게는 `CSamplePropPage::DoDataExchange` 함수입니다.  
  
##  <a name="_core_customizing_the_dodataexchange_function"></a> DoDataExchange 함수를 사용자 지정  
 속성 페이지 [CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) 함수 컨트롤에서 속성의 실제 값을 사용 하 여 속성 페이지 값을 연결할 수 있습니다. 연결을 설정 하려면 해당 컨트롤 속성을 적절 한 속성 페이지 필드를 매핑해야 합니다.  
  
 이러한 매핑은 속성 페이지를 사용 하 여 구현 됩니다 **DDP_** 함수입니다. **DDP_** 함수 처럼 작동는 **DDX_** 예외적으로 표준 MFC 대화 상자에서 사용 되는 함수입니다. 멤버 변수에 대 한 참조 외에도 **DDP_** 함수는 사용 된 컨트롤 속성의 이름입니다. 다음은 일반적인 한 항목에는 `DoDataExchange` 속성 페이지에 대 한 함수입니다.  
  
 [!code-cpp[NVC_MFC_AxUI#31](../mfc/codesnippet/cpp/mfc-activex-controls-property-pages_1.cpp)]  
  
 이 함수는 속성 페이지의 연결 *m_caption* 라는 캡션이 있는 멤버 변수를 사용 하는 `DDP_TEXT` 함수입니다.  
  
 속성 페이지 컨트롤, IDC_CAPTION, 및 실제 컨트롤 속성 사이의 연결을 설정 해야 하는 삽입 속성 페이지 컨트롤을 사용 하는 다음 캡션를 사용 하는 `DDP_Text` 위에서 설명한 것 처럼 작동 합니다.  
  
 [속성 페이지](../mfc/reference/property-pages-mfc.md) 목록 상자 및 확인란, 라디오 단추 등의 다른 대화 상자 컨트롤 형식에 사용할 수 있습니다. 아래 표에 속성 페이지의 전체 집합 **DDP_** 함수 및 해당 용도:  
  
### <a name="property-page-functions"></a>속성 페이지 함수  
  
|함수 이름|이 함수를 사용 하 여 연결|  
|-------------------|-------------------------------|  
|`DDP_CBIndex`|컨트롤 속성 콤보 상자에서 선택한 문자열의 인덱스입니다.|  
|`DDP_CBString`|컨트롤 속성 콤보 상자에서 선택한 문자열입니다. 선택 된 문자열 속성의 값으로 동일한 문자로 시작할 수 있지만 완벽 하 게 일치 하지 않아도 합니다.|  
|`DDP_CBStringExact`|컨트롤 속성 콤보 상자에서 선택한 문자열입니다. 선택한 문자열 및 속성의 문자열 값이 정확히 일치 해야 합니다.|  
|`DDP_Check`|컨트롤 속성을 갖는 확인란입니다.|  
|`DDP_LBIndex`|컨트롤 속성으로 목록 상자에서 선택한 문자열의 인덱스입니다.|  
|`DDP_LBString`|컨트롤 속성으로 목록 상자에서 선택한 문자열입니다. 선택 된 문자열 속성의 값으로 동일한 문자로 시작할 수 있지만 완벽 하 게 일치 하지 않아도 합니다.|  
|`DDP_LBStringExact`|컨트롤 속성으로 목록 상자에서 선택한 문자열입니다. 선택한 문자열 및 속성의 문자열 값이 정확히 일치 해야 합니다.|  
|`DDP_Radio`|컨트롤 속성을 갖는 라디오 단추입니다.|  
|`DDP_Text`|컨트롤 속성을 갖는 텍스트입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [COlePropertyPage 클래스](../mfc/reference/colepropertypage-class.md)
