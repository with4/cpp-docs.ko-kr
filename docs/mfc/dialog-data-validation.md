---
title: "대화 상자 데이터 유효성 검사 | Microsoft Docs"
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
  - "데이터 유효성 검사[C++], 대화 상자"
  - "데이터 유효성 검사[C++], 메시지 상자"
  - "DDV(대화 상자 데이터 유효성 검사)[C++]"
  - "대화 상자[C++], 데이터 유효성 검사"
  - "데이터 유효성 검사[C++], 대화 상자 데이터 입력"
  - "데이터 유효성 검사[C++], 메시지 상자"
ms.assetid: f070c309-2044-4ff2-8c92-1ec1ea84af58
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 대화 상자 데이터 유효성 검사
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

You can specify validation in addition to data exchange by calling DDV functions, as shown in the example in [Dialog Data Exchange](../mfc/dialog-data-exchange.md).  The `DDV_MaxChars` call in the example validates that the string entered in the text\-box control is not longer than 20 characters.  The DDV function typically alerts the user with a message box if the validation fails and puts the focus on the offending control so the user can reenter the data.  A DDV function for a given control must be called immediately after the DDX function for the same control.  
  
 You can also define your own custom DDX and DDV routines.  For details on this and other aspects of DDX and DDV, see [MFC Technical Note 26](../mfc/tn026-ddx-and-ddv-routines.md).  
  
 The [Add Member Variable Wizard](../ide/add-member-variable-wizard.md) will write all of the DDX and DDV calls in the data map for you.  
  
## 참고 항목  
 [대화 상자 데이터 교환 및 유효성 검사](../mfc/dialog-data-exchange-and-validation.md)   
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)   
 [대화 상자 데이터 교환](../mfc/dialog-data-exchange.md)