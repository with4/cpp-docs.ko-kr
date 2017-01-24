---
title: "방법: 기존 MFC 리본을 리본 리소스로 변환 | Microsoft Docs"
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
  - "MFC 리본, 리본 리소스로 변환"
  - "리본 리소스, MFC 리본에서 변환"
ms.assetid: 324b7ff6-58f9-4691-96a9-9836a79d0fb6
caps.latest.revision: 8
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 기존 MFC 리본을 리본 리소스로 변환
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ribbon resources are easier to visualize, modify, and maintain than manually coded ribbons.  This topic describes how to convert a manually coded ribbon in an MFC Project into a ribbon resource.  
  
 You must have an existing MFC project that has code that uses the MFC ribbon classes, for example, [CMFCRibbonBar Class](../mfc/reference/cmfcribbonbar-class.md).  
  
### To convert an MFC ribbon to a ribbon resource  
  
1.  In Visual Studio, in an existing MFC project, open the source file where the CMFCRibbonBar object is initialized.  Typically, the file is mainfrm.cpp.  Add the following code after the initialization code for the ribbon.  
  
    ```  
    m_wndRibbonBar.SaveToXMLFile("RibbonOutput.xml");  
    ```  
  
     파일을 저장한 후 닫습니다.  
  
2.  Build and run the MFC application, and then in Notepad, open RibbonOutput.txt and copy its contents.  
  
3.  In Visual Studio, on the **Project** menu, click **Add Resource**.  **리소스 추가**대화 상자에서,  **리본** 을 선택한 다음 **New**을 클릭합니다.  
  
     Visual Studio creates a ribbon resource and opens it in design view.  리본 리소스 ID는 **리소스 뷰**에서 표시되는 IDR\_RIBBON1입니다.  The ribbon is defined in the ribbon1.mfcribbon\-ms XML file.  
  
4.  In Visual Studio, open ribbon1.mfcribbon\-ms, delete its contents, and then paste the contents of RibbonOutput.txt, which you copied earlier.  Save and close ribbon1.mfcribbon\-ms.  
  
5.  Again open the source file where the CMFCRibbonBar object is initialized \(typically, mainfrm.cpp\) and comment out the existing ribbon code.  Add the following code after the code that you commented out.  
  
    ```  
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);  
    ```  
  
6.  Build the project and run the program.  
  
## 참고 항목  
 [리본 디자이너\(MFC\)](../mfc/ribbon-designer-mfc.md)