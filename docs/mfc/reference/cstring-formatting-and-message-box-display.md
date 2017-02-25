---
title: "CString 서식 지정 및 메시지 상자 표시 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.strings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CString 개체, 서식 지정 및 메시지 상자"
ms.assetid: d1068cf4-9cc5-4952-b9e7-d612c53cbc28
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# CString 서식 지정 및 메시지 상자 표시
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

A number of functions are provided to format and parse `CString` objects.  You can use these functions whenever you have to manipulate `CString` objects, but they are particularly useful for formatting strings that will appear in message\-box text.  
  
 This group of functions also includes a global routine for displaying a message box.  
  
### CString Functions  
  
|||  
|-|-|  
|[AfxExtractSubString](../Topic/AfxExtractSubString.md)|Extracts substrings separated by a single character from a given source string.|  
|[AfxFormatString1](../Topic/AfxFormatString1.md)|Substitutes a given string for the format characters "%1" in a string contained in the string table.|  
|[AfxFormatString2](../Topic/AfxFormatString2.md)|Substitutes two strings for the format characters "%1" and "%2" in a string contained in the string table.|  
|[AfxMessageBox](../Topic/AfxMessageBox.md)|메시지 상자를 표시합니다.|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)   
 [CStringT Class](../../atl-mfc-shared/reference/cstringt-class.md)