---
title: "대화 상자 데이터 교환 | Microsoft Docs"
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
  - "데이터 교환 취소"
  - "사용자 입력 캡처"
  - "CDataExchange 클래스, DDX 사용"
  - "DDX(대화 상자 데이터 교환), 취소"
  - "DDX(대화 상자 데이터 교환), 데이터 교환 메커니즘"
  - "대화 상자 데이터"
  - "대화 상자 데이터, 검색"
  - "대화 상자, 데이터 교환"
  - "대화 상자, 초기화"
  - "대화 상자, DDX를 사용하여 사용자 입력 검색"
  - "DoDataExchange 메서드"
  - "대화 상자 초기화"
  - "대화 상자 데이터 검색"
  - "대화 상자 데이터 전송"
  - "UpdateData 메서드"
  - "사용자 입력, MFC 대화 상자에서 검색"
ms.assetid: 4675f63b-41d2-45ed-b6c3-235ad8ab924b
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 대화 상자 데이터 교환
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

If you use the DDX mechanism, you set the initial values of the dialog object's member variables, typically in your `OnInitDialog` handler or the dialog constructor.  Immediately before the dialog is displayed, the framework's DDX mechanism transfers the values of the member variables to the controls in the dialog box, where they appear when the dialog box itself appears in response to `DoModal` or **Create**.  The default implementation of `OnInitDialog` in `CDialog` calls the `UpdateData` member function of class `CWnd` to initialize the controls in the dialog box.  
  
 The same mechanism transfers values from the controls to the member variables when the user clicks the OK button \(or whenever you call the `UpdateData` member function with the argument **TRUE**\).  The dialog data validation mechanism validates any data items for which you specified validation rules.  
  
 The following figure illustrates dialog data exchange.  
  
 ![대화 상자 데이터 교환](../mfc/media/vc379d1.png "vc379D1")  
대화 상자 데이터 교환  
  
 `UpdateData` works in both directions, as specified by the **BOOL** parameter passed to it.  To carry out the exchange, `UpdateData` sets up a `CDataExchange` object and calls your dialog class's override of `CDialog`'s `DoDataExchange` member function.  `DoDataExchange` takes an argument of type `CDataExchange`.  The `CDataExchange` object passed to `UpdateData` represents the context of the exchange, defining such information as the direction of the exchange.  
  
 When you \(or a Code wizard\) override `DoDataExchange`, you specify a call to one DDX function per data member \(control\).  Each DDX function knows how to exchange data in both directions based on the context supplied by the `CDataExchange` argument passed to your `DoDataExchange` by `UpdateData`.  
  
 MFC provides many DDX functions for different kinds of exchange.  The following example shows a `DoDataExchange` override in which two DDX functions and one DDV function are called:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#49](../mfc/codesnippet/CPP/dialog-data-exchange_1.cpp)]  
  
 The `DDX_` and `DDV_` lines are a data map.  The sample DDX and DDV functions shown are for a check\-box control and an edit\-box control, respectively.  
  
 If the user cancels a modal dialog box, the `OnCancel` member function terminates the dialog box and `DoModal` returns the value **IDCANCEL**.  In that case, no data is exchanged between the dialog box and the dialog object.  
  
## 참고 항목  
 [대화 상자 데이터 교환 및 유효성 검사](../mfc/dialog-data-exchange-and-validation.md)   
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)   
 [대화 상자 데이터 유효성 검사](../mfc/dialog-data-validation.md)