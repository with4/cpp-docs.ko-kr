---
title: "MFC ActiveX 컨트롤: 다른 사용자 지정 속성 페이지 추가 | Microsoft Docs"
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
  - "ActiveX 컨트롤[C++], 속성 페이지"
  - "사용자 지정 속성 페이지"
  - "MFC ActiveX 컨트롤[C++], 속성 페이지"
  - "속성 페이지[C++], MFC ActiveX 컨트롤"
ms.assetid: fcf7e119-9f29-41a9-908d-e9b1607e08af
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC ActiveX 컨트롤: 다른 사용자 지정 속성 페이지 추가
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Occasionally, an ActiveX control will have more properties than can reasonably fit on one property page.  In this case, you can add property pages to the ActiveX control to display these properties.  
  
 This article discusses adding new property pages to an ActiveX control that already has at least one property page.  For more information on adding stock property pages \(font, picture, or color\), see the article [MFC ActiveX Controls: Using Stock Property Pages](../mfc/mfc-activex-controls-using-stock-property-pages.md).  
  
 The following procedures use a sample ActiveX control framework created by the ActiveX Control Wizard.  Therefore, the class names and identifiers are unique to this example.  
  
 For more information on using property pages in an ActiveX control, see the following articles:  
  
-   [MFC ActiveX Controls: Property Pages](../mfc/mfc-activex-controls-property-pages.md)  
  
-   [MFC ActiveX Controls: Using Stock Property Pages](../mfc/mfc-activex-controls-using-stock-property-pages.md)  
  
    > [!NOTE]
    >  It is strongly recommended that new property pages adhere to the size standard for ActiveX control property pages.  The stock picture and color property pages measure 250x62 dialog units \(DLU\).  The standard font property page is 250x110 DLUs.  The default property page created by the ActiveX Control Wizard uses the 250x62 DLU standard.  
  
### To insert a new property page template into your project  
  
1.  With your control project open, open Resource View in the project workspace.  
  
2.  Right\-click in Resource View to open the shortcut menu and click **Add Resource**.  
  
3.  Expand the **Dialog** node, and select **IDD\_OLE\_PROPPAGE\_SMALL**.  
  
4.  Click `New` to add the resource to your project.  
  
5.  Select the new property page template to refresh the Properties window.  
  
6.  Enter a new value for the **ID** property.  This example uses **IDD\_PROPPAGE\_NEWPAGE**.  
  
7.  도구 모음에서 **저장**을 클릭합니다.  
  
### To associate the new template with a class  
  
1.  Open Class View.  
  
2.  Right\-click in Class View to open the shortcut menu.  
  
3.  바로 가기 메뉴에서 **추가**를 클릭한 다음 **클래스 추가**를 클릭합니다.  
  
     This opens the [Add Class](../ide/add-class-dialog-box.md) dialog box.  
  
4.  Double\-click the **MFC Class** template.  
  
5.  In the **Class Name** box in the [MFC Class Wizard](../mfc/reference/mfc-add-class-wizard.md), type a name for the new dialog class. \(In this example, `CAddtlPropPage`.\)  
  
6.  If you want to change file names, click **Change**.  Type in the names for your implementation and header files, or accept the default names.  
  
7.  In the **Base Class** box, select `COlePropertyPage`.  
  
8.  In the **Dialog ID** box, select **IDD\_PROPPAGE\_NEWPAGE**.  
  
9. Click **Finish** to create the class.  
  
 To allow the control's users access to this new property page, make the following changes to the control's property page IDs macro section \(located in the control implementation file\):  
  
 [!code-cpp[NVC_MFC_AxUI#32](../mfc/codesnippet/CPP/mfc-activex-controls-adding-another-custom-property-page_1.cpp)]  
  
 Note that you must increase the second parameter of the `BEGIN_PROPPAGEIDS` macro \(the property page count\) from 1 to 2.  
  
 You must also modify the control implementation file \(.CPP\) file to include the header \(.H\) file of the new property page class.  
  
 The next step involves creating two new string resources that will provide a type name and a caption for the new property page.  
  
#### To add new string resources to a property page  
  
1.  With your control project open, open Resource View.  
  
2.  Double\-click the **String Table** folder and then double\-click the existing string table resource to which you want to add a string.  
  
     This opens the string table in a window.  
  
3.  Select the blank line at the end of the string table and type the text, or caption, of the string: for example, "Additional Property Page."  
  
     This opens a **String Properties** page showing **Caption** and **ID** boxes.  The **Caption** box contains the string you typed.  
  
4.  In the **ID** box, select or type an ID for the string.  Press Enter when you finish.  
  
     This example uses **IDS\_SAMPLE\_ADDPAGE** for the type name of the new property page.  
  
5.  Repeat steps 3 and 4 using **IDS\_SAMPLE\_ADDPPG\_CAPTION** for the ID and "Additional Property Page" for the caption.  
  
6.  In the .CPP file of your new property page class \(in this example, `CAddtlPropPage`\) modify the `CAddtlPropPage::CAddtlPropPageFactory::UpdateRegistry` so that IDS\_SAMPLE\_ADDPAGE is passed by [AfxOleRegisterPropertyPageClass](../Topic/AfxOleRegisterPropertyPageClass.md), as in the following example:  
  
     [!code-cpp[NVC_MFC_AxUI#33](../mfc/codesnippet/CPP/mfc-activex-controls-adding-another-custom-property-page_2.cpp)]  
  
7.  Modify the constructor of `CAddtlPropPage` so that **IDS\_SAMPLE\_ADDPPG\_CAPTION** is passed to the `COlePropertyPage` constructor, as follows:  
  
     [!code-cpp[NVC_MFC_AxUI#34](../mfc/codesnippet/CPP/mfc-activex-controls-adding-another-custom-property-page_3.cpp)]  
  
 After you have made the necessary modifications rebuild your project and use Test Container to test the new property page.  테스트 컨테이너에 액세스하는 방법에 대한 자세한 내용은 [Test Container를 사용하여 속성 및 이벤트 테스트](../mfc/testing-properties-and-events-with-test-container.md)를 참조하십시오.  
  
## 참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)