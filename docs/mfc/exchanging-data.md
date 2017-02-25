---
title: "데이터 교환 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DDX(대화 상자 데이터 교환), 속성 시트"
  - "속성 시트와 데이터 교환"
  - "속성 시트, 데이터 교환"
ms.assetid: 689f02d0-51a9-455b-8ffb-5b44f0aefa28
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 데이터 교환
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

As with most dialog boxes, the exchange of data between the property sheet and the application is one of the most important functions of the property sheet.  This article describes how to accomplish this task.  
  
 Exchanging data with a property sheet is actually a matter of exchanging data with the individual property pages of the property sheet.  The procedure for exchanging data with a property page is the same as for exchanging data with a dialog box, since a [CPropertyPage](../mfc/reference/cpropertypage-class.md) object is just a specialized [CDialog](../mfc/reference/cdialog-class.md) object.  The procedure takes advantage of the framework's dialog data exchange \(DDX\) facility, which exchanges data between controls in a dialog box and member variables of the dialog box object.  
  
 The important difference between exchanging data with a property sheet and with a normal dialog box is that the property sheet has multiple pages, so you must exchange data with all the pages in the property sheet.  For more information on DDX, see [Dialog Data Exchange and Validation](../mfc/dialog-data-exchange-and-validation.md).  
  
 The following example illustrates exchanging data between a view and two pages of a property sheet:  
  
 [!code-cpp[NVC_MFCDocView#4](../mfc/codesnippet/CPP/exchanging-data_1.cpp)]  
  
## 참고 항목  
 [속성 시트](../mfc/property-sheets-mfc.md)