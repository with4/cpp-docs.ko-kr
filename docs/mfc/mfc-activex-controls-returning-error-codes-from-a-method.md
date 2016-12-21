---
title: "MFC ActiveX 컨트롤: 메서드에서 오류 코드 반환 | Microsoft Docs"
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
  - "오류[C++], ActiveX 컨트롤 오류 코드"
  - "FireError 메서드"
  - "GetNotSupported 메서드"
  - "MFC ActiveX 컨트롤, 오류 코드"
  - "SCODE, MFC ActiveX 컨트롤"
  - "SetNotSupported 메서드, using"
  - "ThrowError 메서드"
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC ActiveX 컨트롤: 메서드에서 오류 코드 반환
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article describes how to return error codes from an ActiveX control method.  
  
 To indicate that an error has occurred within a method, you should use the [COleControl::ThrowError](../Topic/COleControl::ThrowError.md) member function, which takes an `SCODE` \(status code\) as a parameter.  You can use a predefined `SCODE` or define one of your own.  
  
> [!NOTE]
>  `ThrowError` is meant to be used only as a means of returning an error from within a property's Get or Set function or an automation Method.  These are the only times that the appropriate exception handler will be present on the stack.  
  
 Helper functions exist for the most common predefined `SCODE`s, such as [COleControl::SetNotSupported](../Topic/COleControl::SetNotSupported.md), [COleControl::GetNotSupported](../Topic/COleControl::GetNotSupported.md), and [COleControl::SetNotPermitted](../Topic/COleControl::SetNotPermitted.md).  
  
 For a list of predefined `SCODE`s and instructions on defining custom `SCODE`s, see the section [Handling Errors in Your ActiveX Control](../mfc/mfc-activex-controls-advanced-topics.md) in ActiveX Controls: Advanced Topics.  
  
 For more information on reporting exceptions in other areas of your code, see [COleControl::FireError](../Topic/COleControl::FireError.md) and the section [Handling Errors in Your ActiveX Control](../mfc/mfc-activex-controls-advanced-topics.md) in ActiveX Controls: Advanced Topics.  
  
## 참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)