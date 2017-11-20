---
title: "MFC ActiveX 컨트롤: 다른 사용자 지정 속성 페이지 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- property pages [MFC], MFC ActiveX controls
- custom property pages [MFC]
- ActiveX controls [MFC], property pages
- MFC ActiveX controls [MFC], property pages
ms.assetid: fcf7e119-9f29-41a9-908d-e9b1607e08af
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 225535055f05fa8d6eeb08476004fbc5074e86b2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-activex-controls-adding-another-custom-property-page"></a>MFC ActiveX 컨트롤: 다른 사용자 지정 속성 페이지 추가
경우에 따라서는 ActiveX 컨트롤 한 속성 페이지에 표시 될 수 있는 보다 더 많은 속성을 갖습니다. 이 경우 이러한 속성을 표시 하려면 ActiveX 컨트롤에 속성 페이지를 추가할 수 있습니다.  
  
 설명 속성 페이지를 하나 이상이 이미 있는 ActiveX 컨트롤에 새 속성 페이지를 추가 합니다. 스톡 속성 추가 대 한 자세한 내용은 페이지 (글꼴, 사진 또는 색) 문서를 참조 [MFC ActiveX 컨트롤: 스톡 속성 페이지를 사용 하 여](../mfc/mfc-activex-controls-using-stock-property-pages.md)합니다.  
  
 다음 절차는 ActiveX 컨트롤 마법사에서 만든 샘플 ActiveX 컨트롤 프레임 워크를 사용 합니다. 따라서 클래스 이름 및 식별자는이 예제에 고유 합니다.  
  
 ActiveX 컨트롤의 속성 페이지 사용에 대 한 자세한 내용은 다음 문서를 참조 합니다.  
  
-   [MFC ActiveX 컨트롤: 속성 페이지](../mfc/mfc-activex-controls-property-pages.md)  
  
-   [MFC ActiveX 컨트롤: 스톡 속성 페이지 사용](../mfc/mfc-activex-controls-using-stock-property-pages.md)  
  
    > [!NOTE]
    >  새 속성 페이지 크기 ActiveX 컨트롤 속성 페이지에 대 한 표준 준수 가장 좋습니다. 그림 및 색상 스톡 속성 페이지 250 x 62 측정값 대화 상자 단위 (DLU). 표준 글꼴 속성 페이지는 250 x 110 Dlu입니다. ActiveX 컨트롤 마법사에서 만든 기본 속성 페이지는 250 x 62 DLU 표준을 사용 합니다.  
  
### <a name="to-insert-a-new-property-page-template-into-your-project"></a>프로젝트에 새 속성 페이지 서식 파일을 삽입 하려면  
  
1.  컨트롤 프로젝트를 열고, 프로젝트 작업 영역에서 리소스 보기를 엽니다.  
  
2.  바로 가기 메뉴를 열고 클릭 리소스 뷰에서 마우스 오른쪽 단추로 클릭 **리소스 추가**합니다.  
  
3.  확장 된 **대화** 노드를 선택한 **IDD_OLE_PROPPAGE_SMALL**합니다.  
  
4.  클릭 `New` 프로젝트에 리소스를 추가 합니다.  
  
5.  속성 창을 새로 고쳐야 새 속성 페이지 템플릿을 선택 합니다.  
  
6.  에 대 한 새 값을 입력에서 **ID** 속성입니다. 이 예에서는 **IDD_PROPPAGE_NEWPAGE**합니다.  
  
7.  클릭 **저장** 도구 모음입니다.  
  
### <a name="to-associate-the-new-template-with-a-class"></a>클래스와 함께 새 서식 파일을 연결 하려면  
  
1.  클래스 뷰를 엽니다.  
  
2.  클래스 뷰 바로 가기 메뉴를 열고를 마우스 오른쪽 단추로 클릭 합니다.  
  
3.  바로 가기 메뉴에서 클릭 **추가** 클릭 하 고 **클래스 추가**합니다.  
  
     열립니다는 [클래스 추가](../ide/add-class-dialog-box.md) 대화 상자.  
  
4.  두 번 클릭 하 고 **MFC 클래스** 템플릿.  
  
5.  에 **클래스 이름** 상자에 [MFC 클래스 마법사](../mfc/reference/mfc-add-class-wizard.md), 새 대화 상자 클래스에 대 한 이름을 입력 합니다. (이 예제에서는 `CAddtlPropPage`.)  
  
6.  파일 이름을 변경 하려면 클릭 **변경**합니다. 구현 및 헤더 파일의 이름을 입력 하거나 기본 이름을 적용 합니다.  
  
7.  에 **기본 클래스** 상자 `COlePropertyPage`합니다.  
  
8.  에 **대화 ID** 상자 **IDD_PROPPAGE_NEWPAGE**합니다.  
  
9. 클릭 **마침** 여 클래스를 만듭니다.  
  
 컨트롤의 사용자가이 새 속성 페이지에 대 한 액세스를 하려면 다음과 같이 변경 컨트롤의 속성 페이지 Id 매크로 섹션 (컨트롤 구현 파일에 있음):  
  
 [!code-cpp[NVC_MFC_AxUI#32](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_1.cpp)]  
  
 참고의 두 번째 매개 변수를 증가 시켜야 하는 `BEGIN_PROPPAGEIDS` 2 1에서 매크로 (속성 페이지 수)입니다.  
  
 컨트롤 구현 파일을 수정 해야 (합니다. 헤더를 포함 하도록 CPP) 파일 (합니다. H) 새 속성 페이지 클래스의 파일입니다.  
  
 다음 단계에서는 새 속성 페이지에 대 한 형식 이름 및 캡션을 제공 하는 두 개의 새로운 문자열 리소스를 만들어야 합니다.  
  
#### <a name="to-add-new-string-resources-to-a-property-page"></a>새 문자열 리소스 속성 페이지를 추가 하려면  
  
1.  컨트롤 프로젝트를 열고, 리소스 보기를 엽니다.  
  
2.  두 번 클릭 하 여 **문자열 테이블** 기존 문자열 테이블 리소스 문자열을 추가 하려면 폴더와 두 번 클릭 합니다.  
  
     문자열 테이블을 창에서 열립니다.  
  
3.  문자열 테이블의 끝에 빈 줄을 선택 하 고 텍스트 또는 캡션 문자열을 입력 합니다: 예를 들어 "추가 속성 페이지입니다."  
  
     열립니다는 **문자열 속성** 페이지 표시 **캡션** 및 **ID** 상자입니다. **캡션** 상자에 입력 한 문자열이 포함 됩니다.  
  
4.  에 **ID** 상자를 선택 하거나 문자열에 대 한 ID를 입력 합니다. 완료 하면 enter 키를 누릅니다.  
  
     이 예에서는 **IDS_SAMPLE_ADDPAGE** 새 속성 페이지의 형식 이름에 대 한 합니다.  
  
5.  3-4를 사용 하 여 단계를 반복 **IDS_SAMPLE_ADDPPG_CAPTION** ID 및 캡션에 대 한 "추가 속성 페이지"에 대 한 합니다.  
  
6.  안에. 새 속성 페이지 클래스의 CPP 파일 (이 예제에서는 `CAddtlPropPage`) 수정 된 `CAddtlPropPage::CAddtlPropPageFactory::UpdateRegistry` IDS_SAMPLE_ADDPAGE로 전달 되도록 [AfxOleRegisterPropertyPageClass](../mfc/reference/registering-ole-controls.md#afxoleregisterpropertypageclass)다음 예제와 같이,:  
  
     [!code-cpp[NVC_MFC_AxUI#33](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_2.cpp)]  
  
7.  생성자를 수정 `CAddtlPropPage` 있도록 **IDS_SAMPLE_ADDPPG_CAPTION** 에 전달 되는 `COlePropertyPage` 생성자를 다음과 같이 합니다.  
  
     [!code-cpp[NVC_MFC_AxUI#34](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_3.cpp)]  
  
 프로젝트를 다시 작성 하 고 테스트 컨테이너를 사용 하 여 새 속성 페이지를 테스트 하려면 필요한 대로 수정 수행한 후 합니다. 테스트 컨테이너에 액세스하는 방법은 [테스트 컨테이너로 속성 및 이벤트 테스트](../mfc/testing-properties-and-events-with-test-container.md) 를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)

