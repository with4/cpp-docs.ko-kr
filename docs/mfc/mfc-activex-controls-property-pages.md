---
title: "MFC ActiveX 컨트롤: 속성 페이지 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPropertyPageDialog 클래스"
  - "DDP_ 함수"
  - "DoDataExchange 메서드"
  - "MFC ActiveX 컨트롤, 속성"
  - "MFC ActiveX 컨트롤, 속성 페이지"
  - "OLEIVERB_PROPERTIES"
  - "속성 페이지, MFC ActiveX 컨트롤"
ms.assetid: 1506f87a-9fd6-4505-8380-0dbc9636230e
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC ActiveX 컨트롤: 속성 페이지
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ActiveX 컨트롤 사용자는 속성 페이지를 통해 ActiveX 컨트롤 속성을 보거나 변경할 수 있습니다.  이러한 속성은 컨트롤 속성 대화 상자를 통해 액세스할 수 있습니다. 이 대화 상자에는 하나 이상의 속성 페이지가 있으며 각 페이지는 컨트롤 속성을 표시하거나 편집할 수 있는 사용자 지정 그래픽 인터페이스로 구성되어 있습니다.  
  
 ActiveX 컨트롤 속성 페이지는 두 가지 방법으로 표시 됩니다.  
  
-   컨트롤의 속성 동사 \(**OLEIVERB\_PROPERTIES**\)가 호출될 때 그 컨트롤은 컨트롤의 속성 페이지를 포함하는 모달 속성 대화상자를 엽니다.  
  
-   컨테이너는 선택된 컨트롤의 속성 페이지를 보여주는 모덜리스 대화상자를 표시합니다.  
  
 현재 속성 페이지를 보여주기 위한 영역을 포함하는 속성 대화 상자 \(다음 그림과 같이\), 속성 페이지 사이의 변경을 위한 탭들, 그리고 속성페이지 대화상자를 닫는 것, 변경 취소 또는 ActiveX 컨트롤에 변경내용을 즉시 적용하는 것과 같은 일반적인 작업을 수행하는 버튼들의 모음.  
  
 ![Circ3 속성 대화 상자](../mfc/media/vc373i1.png "vc373I1")  
속성 대화 상자  
  
 이 문서는 ActiveX 컨트롤의 속성 페이지 사용과 관련된 항목들입니다.  제공합니다.  
  
-   [ActiveX 컨트롤의 기본 속성 페이지 구현](#_core_implementing_the_default_property_page)  
  
-   [속성 페이지에 컨트롤 추가](#_core_adding_controls_to_a_property_page)  
  
-   [DoDataExchange 함수의 사용자 지정](#_core_customizing_the_dodataexchange_function)  
  
 ActiveX 컨트롤에서 속성 페이지 사용에 대한 더 많은 정보를 원하신다면 다음 문서를 참조하십시오.  
  
-   [MFC ActiveX 컨트롤: 다른 사용자 지정 속성 페이지 추가](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)  
  
-   [MFC ActiveX 컨트롤: 스톡 속성 페이지 사용](../mfc/mfc-activex-controls-using-stock-property-pages.md)  
  
 ActiveX 컨트롤보다 MFC 응용 프로그램에서 속성 시트를 사용하는 것에 대한 정보를 보려면 [속성 시트](../mfc/property-sheets-mfc.md)를 참조하세요.  
  
##  <a name="_core_implementing_the_default_property_page"></a> 기본 속성 페이지의 구현  
 ActiveX 컨트롤 마법사를 사용하여 컨트롤 프로젝트를 만드려고 한다면 ActiveX 컨트롤 마법사는 [COlePropertyPage Class](../mfc/reference/colepropertypage-class.md)에서 파생된 컨트롤에 대한 기본 속성 페이지 클래스를 제공합니다 .  처음에 이 속성 페이지는 비어 있지만 대화 상자 컨트롤이나 컨트롤 집합을 추가할 수 있습니다.  ActiveX 컨트롤 마법사는 기본적으로 단 하나만의 속성 페이지 클래스를 생성하기 때문에 \( `COlePropertyPage` 에서 파생된 것 또한\) 클래스 뷰를 사용 하 여 만들어야 합니다.  이 절차에 대한 자세한 내용은 [MFC ActiveX 컨트롤: 다른 사용자 지정 속성 페이지 추가](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)을 참조하십시오.  
  
 속성 페이지를 구현하는 것 \( 이경우 기본값\) 은 3단계 프로세스 입니다 :  
  
#### 속성 페이지를 구현 하려면  
  
1.  `COlePropertyPage` 파생 클래스를 컨트롤 프로젝트에 추가합니다.  만약 프로젝트가 ActiveX 컨트롤 마법사를 사용하여\(이 경우에\) 생성된 경우 기본 속성 페이지 클래스는 이미 존재합니다.  
  
2.  속성 페이지 템플릿에 컨트롤들을 추가하려면 대화상자 편집기를 사용합니다.  
  
3.  속성 페이지 컨트롤과 ActiveX 컨트롤 사이에서 값을 변경하기위해서 `COlePropertyPage` 파생클래스의 `DoDataExchange` 함수를 사용자 지정합니다.  
  
 예를 들어 다음 절자에서는 \("Sample"이라는\) 간단한 컨트롤을 사용합니다.  샘플은 ActiveX컨트롤 마법사를 사용하여 생성되고 스톡 caption 속성을 포함합니다.  
  
##  <a name="_core_adding_controls_to_a_property_page"></a> 속성 페이지에 컨트롤 추가  
  
#### 속성 페이지에 컨트롤을 추가 하려면  
  
1.  컨트롤 프로젝트를 열고, 리소스 뷰를 엽니다.  
  
2.  **Dialog** 디렉터리 아이콘을 더블클릭합니다.  
  
3.  **IDD\_PROPPAGE\_SAMPLE**  대화 상자를 엽니다.  
  
     ActiveX 컨트롤 마법사는 대화상자 ID의 끝에 프로젝트의 이름을 추가합니다. 이경우에는 Sample입니다.  
  
4.  도구 상자에서 대화상자 영역으로 선택된 컨트롤을 드래그해서 드롭합니다.  
  
5.  이 예제에서 텍스트 레이블 컨트롤 "Caption:" 그리고 **IDC\_CAPTION** 식별자를 가진 편집 상자 컨트롤은 적당합니다.  
  
6.  응용 프로그램 도구 모음에서 **저장**을 클릭하여 변경 내용을 저장합니다.  
  
 유저 인터페이스가 수정되었으므로 사용자는 Caption속성과 편집 상자를 연결해야합니다.  `CSamplePropPage::DoDataExchange` 함수를 편집함으로써 다음 섹션은 완료됩니다.  
  
##  <a name="_core_customizing_the_dodataexchange_function"></a> DoDataExchange 함수의 사용자 지정  
 속성 페이지 [CWnd::DoDataExchange](../Topic/CWnd::DoDataExchange.md) 함수는 사용자가 컨트롤의 속성들의 실제값과 속성 페이지의 값을 연결시키도록 허용합니다.  연결을 설정하려면 사용자는 각 컨트롤 속성들에 적당한 속성 페이지 필드를 맵핑시켜야 합니다.  
  
 이 매핑들은 속성 페이지 **DDP\_** 함수를 사용하여 구현됩니다.   **DDP\_** 들은 표준 MFC 대화상자에서 사용되는 **DDX\_** 함수처럼 하나의 예외를 가지고 작동합니다.  멤버 변수를 참조하는 것이외에도 **DDP\_** 함수는 컨트롤 속성의 이름을 갖습니다.  다음은 속성 페이지에 대한 `DoDataExchange` 함수의 일반적인 항목입니다.  
  
 [!code-cpp[NVC_MFC_AxUI#31](../mfc/codesnippet/CPP/mfc-activex-controls-property-pages_1.cpp)]  
  
 이 함수는 `DDP_TEXT` 함수를 사용하여 속성 페이지의 `m_caption` 멤버 변수와 캡션을 연결시켜줍니다.  
  
 사용자가 속성 페이지 컨트롤을 삽입하고 난 후 사용자는 위에서 설명한대로 **DDP\_Text** 함수를 사용하여 속성 페이지 컨트롤, `IDC_CAPTION`, 캡션, 실제 컨트롤 속성 사이의 연결을 설정할 필요가 있습니다.  
  
 [속성 페이지](../mfc/reference/property-pages-mfc.md)들은 체크박스, 라디오 버튼, 목록 상자 등과 같은 다른 대화상자 컨트롤 형식에 대해 사용가능합니다.  아래의 표는 속성 페이지의 전체적인 집합, **DDP\_** 함수와 기능들의 목록입니다 :  
  
### 속성 페이지 함수  
  
|함수 이름|연결하려면 이 함수를 사용하세요|  
|-----------|-----------------------|  
|`DDP_CBIndex`|컨트롤 속성과 콤보상자의 선택된 문자열의 인덱스입니다.|  
|`DDP_CBString`|컨트롤 속성과 콤보상자의 선택된 문자열의 인덱스입니다.  선택된 문자열은 속성의 값과 동일한 문자들로 시작할 수 있지만 완전히 일치하지는 않아도 됩니다.|  
|`DDP_CBStringExact`|컨트롤 속성과 콤보상자의 선택된 문자열의 인덱스입니다.  선택한 문자열과 속성의 문자열 값은 정확히 일치 해야 합니다.|  
|`DDP_Check`|컨트롤 속성의 체크 박스|  
|`DDP_LBIndex`|컨트롤 속성과 콤보상자의 선택된 문자열의 인덱스입니다.|  
|`DDP_LBString`|컨트롤 속성을 사용 하 여 목록 상자에서 선택한 문자열입니다.  선택된 문자열은 속성의 값과 동일한 문자들로 시작할 수 있지만 완전히 일치하지는 않아도 됩니다.|  
|`DDP_LBStringExact`|컨트롤 속성을 사용 하 여 목록 상자에서 선택한 문자열입니다.  선택한 문자열과 속성의 문자열 값은 정확히 일치 해야 합니다.|  
|`DDP_Radio`|컨트롤 속성의 라디오 버튼|  
|**DDP\_Text**|컨트롤 속성의 텍스트|  
  
## 참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [COlePropertyPage Class](../mfc/reference/colepropertypage-class.md)