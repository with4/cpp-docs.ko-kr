---
title: "MFC ActiveX 컨트롤: 스톡 속성 추가 | Microsoft Docs"
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
  - "BackColor 속성"
  - "ForeColor 속성"
  - "전경색"
  - "전경색, ActiveX 컨트롤"
  - "MFC ActiveX 컨트롤, 속성"
  - "속성[MFC], 스톡 추가"
ms.assetid: 8b98c8c5-5b69-4366-87bf-0e61e6668ecb
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC ActiveX 컨트롤: 스톡 속성 추가
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stock properties differ from custom properties in that they are already implemented by the class `COleControl`.  `COleControl` contains predefined member functions that support common properties for the control.  Some common properties include the control's caption and the foreground and background colors.  For information on other stock properties, see [Stock Properties Supported by the Add Property Wizard](#_core_stock_properties_supported_by_classwizard) later in this article.  The dispatch map entries for stock properties are always prefixed by **DISP\_STOCKPROP**.  
  
 This article describes how to add a stock property \(in this case, Caption\) to an ActiveX control using the Add Property Wizard and explains the resulting code modifications.  다음 내용을 다룹니다.  
  
-   [Using the Add Property Wizard to add a stock property](#_core_using_classwizard_to_add_a_stock_property)  
  
-   [Add Property Wizard changes for stock properties](#_core_classwizard_changes_for_stock_properties)  
  
-   [Stock properties supported by the Add Property Wizard](#_core_stock_properties_supported_by_classwizard)  
  
-   [Stock properties and notification](#_core_stock_properties_and_notification)  
  
-   [Color properties](#_core_color_properties)  
  
    > [!NOTE]
    >  Visual Basic custom controls typically have properties such as Top, Left, Width, Height, Align, Tag, Name, TabIndex, TabStop, and Parent.  ActiveX control containers, however, are responsible for implementing these control properties and therefore ActiveX controls should not support these properties.  
  
##  <a name="_core_using_classwizard_to_add_a_stock_property"></a> Using the Add Property Wizard to Add a Stock Property  
 Adding stock properties requires less code than adding custom properties because support for the property is handled automatically by `COleControl`.  The following procedure demonstrates adding the stock Caption property to an ActiveX control framework and can also be used to add other stock properties.  Substitute the selected stock property name for Caption.  
  
#### To add the stock Caption property using the Add Property Wizard  
  
1.  Load your control's project.  
  
2.  In Class View, expand the library node of your control.  
  
3.  Right\-click the interface node for your control \(the second node of the library node\) to open the shortcut menu.  
  
4.  From the shortcut menu, click **Add** and then click **Add Property**.  
  
     This opens the [Add Property Wizard](../ide/names-add-property-wizard.md).  
  
5.  In the **Property Name** box, click **Caption**.  
  
6.  **마침**을 클릭합니다.  
  
##  <a name="_core_classwizard_changes_for_stock_properties"></a> Add Property Wizard Changes for Stock Properties  
 Because `COleControl` supports stock properties, the Add Property Wizard does not change the class declaration in any way; it adds the property to the dispatch map.  The Add Property Wizard adds the following line to the dispatch map of the control, which is located in the implementation \(.CPP\) file:  
  
 [!code-cpp[NVC_MFC_AxUI#22](../mfc/codesnippet/CPP/mfc-activex-controls-adding-stock-properties_1.cpp)]  
  
 The following line is added to your control's interface description \(.IDL\) file:  
  
 [!code-cpp[NVC_MFC_AxUI#23](../mfc/codesnippet/CPP/mfc-activex-controls-adding-stock-properties_2.idl)]  
  
 This line assigns the Caption property a specific ID.  Notice that the property is bindable and will request permission from the database before modifying the value.  
  
 This makes the Caption property available to users of your control.  To use the value of a stock property, access a member variable or member function of the `COleControl` base class.  For more information on these member variables and member functions, see the next section, Stock Properties Supported by the Add Property Wizard.  
  
##  <a name="_core_stock_properties_supported_by_classwizard"></a> Stock Properties Supported by the Add Property Wizard  
 The `COleControl` class provides nine stock properties.  You can add the properties you want by using the Add Property Wizard.  
  
|Property|Dispatch map entry|How to access value|  
|--------------|------------------------|-------------------------|  
|**모양**|**DISP\_STOCKPROP\_APPEARANCE\( \)**|Value accessible as **m\_sAppearance**.|  
|`BackColor`|**DISP\_STOCKPROP\_BACKCOLOR\( \)**|Value accessible by calling `GetBackColor`.|  
|`BorderStyle`|**DISP\_STOCKPROP\_BORDERSTYLE\( \)**|Value accessible as **m\_sBorderStyle**.|  
|**Caption**|**DISP\_STOCKPROP\_CAPTION\( \)**|Value accessible by calling `InternalGetText`.|  
|**Enabled**|**DISP\_STOCKPROP\_ENABLED\( \)**|Value accessible as **m\_bEnabled**.|  
|**글꼴**|**DISP\_STOCKPROP\_FONT\( \)**|See the article [MFC ActiveX Controls: Using Fonts](../mfc/mfc-activex-controls-using-fonts.md) for usage.|  
|`ForeColor`|**DISP\_STOCKPROP\_FORECOLOR\( \)**|Value accessible by calling `GetForeColor`.|  
|**hWnd**|**DISP\_STOCKPROP\_HWND\( \)**|Value accessible as `m_hWnd`.|  
|**Text**|**DISP\_STOCKPROP\_TEXT\( \)**|Value accessible by calling `InternalGetText`.  This property is the same as **Caption**, except for the property name.|  
|**ReadyState**|**DISP\_STOCKPROP\_READYSTATE\(\)**|Value accessible as m\_lReadyState or `GetReadyState`|  
  
##  <a name="_core_stock_properties_and_notification"></a> Stock Properties and Notification  
 Most stock properties have notification functions that can be overridden.  For example, whenever the `BackColor` property is changed, the `OnBackColorChanged` function \(a member function of the control class\) is called.  The default implementation \(in `COleControl`\) calls `InvalidateControl`.  Override this function if you want to take additional actions in response to this situation.  
  
##  <a name="_core_color_properties"></a> Color Properties  
 You can use the stock `ForeColor` and `BackColor` properties, or your own custom color properties, when painting the control.  To use a color property, call the [COleControl::TranslateColor](../Topic/COleControl::TranslateColor.md) member function.  The parameters of this function are the value of the color property and an optional palette handle.  The return value is a **COLORREF** value that can be passed to GDI functions, such as `SetTextColor` and `CreateSolidBrush`.  
  
 The color values for the stock `ForeColor` and `BackColor` properties are accessed by calling either the `GetForeColor` or the `GetBackColor` function, respectively.  
  
 The following example demonstrates using these two color properties when painting a control.  It initializes a temporary **COLORREF** variable and a `CBrush` object with calls to `TranslateColor`: one using the `ForeColor` property and the other using the `BackColor` property.  A temporary `CBrush` object is then used to paint the control's rectangle, and the text color is set using the `ForeColor` property.  
  
 [!code-cpp[NVC_MFC_AxUI#24](../mfc/codesnippet/CPP/mfc-activex-controls-adding-stock-properties_3.cpp)]  
  
## 참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX 컨트롤: 속성](../mfc/mfc-activex-controls-properties.md)   
 [MFC ActiveX 컨트롤: 메서드](../mfc/mfc-activex-controls-methods.md)   
 [COleControl Class](../mfc/reference/colecontrol-class.md)