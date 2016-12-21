---
title: "대화 상자 개체에서 데이터 검색 | Microsoft Docs"
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
  - "사용자 입력 캡처"
  - "데이터[MFC], 대화 상자"
  - "데이터[MFC], 검색"
  - "데이터 검색[C++], 대화 상자"
  - "DDX(대화 상자 데이터 교환)[C++]"
  - "DDX(대화 상자 데이터 교환)[C++], DDX 정보"
  - "DDX(대화 상자 데이터 교환)[C++], 대화 상자 개체에서 데이터 검색"
  - "대화 상자 컨트롤[C++], 값 초기화"
  - "대화 상자 데이터[C++]"
  - "대화 상자 데이터[C++], 검색"
  - "대화 상자[C++], 사용자 데이터 검색"
  - "GetDlgItemText 메서드"
  - "GetWindowText 메서드"
  - "MFC 대화 상자, 사용자 입력 검색"
  - "데이터 검색"
  - "SetDlgItemText 메서드"
  - "SetWindowText 메서드"
  - "사용자 입력[C++], MFC 대화 상자에서 검색"
ms.assetid: bdca2b61-6b53-4c2e-b426-8712c7a38ec0
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 대화 상자 개체에서 데이터 검색
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The framework provides an easy way to initialize the values of controls in a dialog box and to retrieve values from the controls.  The more laborious manual approach is to call functions such as the `SetDlgItemText` and `GetDlgItemText` member functions of class `CWnd`, which apply to control windows.  With these functions, you access each control individually to set or get its value, calling functions such as `SetWindowText` and `GetWindowText`.  The framework's approach automates both initialization and retrieval.  
  
 Dialog data exchange \(DDX\) lets you exchange data between the controls in the dialog box and member variables in the dialog object more easily.  This exchange works both ways.  To initialize the controls in the dialog box, you can set the values of data members in the dialog object, and the framework will transfer the values to the controls before the dialog box is displayed.  Then you can at any time update the dialog data members with data entered by the user.  At that point, you can use the data by referring to the data member variables.  
  
 You can also arrange for the values of dialog controls to be validated automatically with dialog data validation \(DDV\).  
  
 DDX and DDV are explained in more detail in [Dialog Data Exchange and Validation](../mfc/dialog-data-exchange-and-validation.md).  
  
 For a modal dialog box, you can retrieve any data the user entered when `DoModal` returns **IDOK** but before the dialog object is destroyed.  For a modeless dialog box, you can retrieve data from the dialog object at any time by calling `UpdateData` with the argument **TRUE** and then accessing dialog class member variables.  This subject is discussed in more detail in [Dialog Data Exchange and Validation](../mfc/dialog-data-exchange-and-validation.md).  
  
## 참고 항목  
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)