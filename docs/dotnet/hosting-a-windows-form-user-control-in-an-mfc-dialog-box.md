---
title: "MFC 대화 상자에서 Windows Form 사용자 정의 컨트롤 호스팅 | Microsoft Docs"
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
  - "Windows Forms 컨트롤 호스팅[C++]"
  - "MFC[C++], Windows Forms 지원"
  - "Windows Forms[C++], MFC 지원"
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# MFC 대화 상자에서 Windows Form 사용자 정의 컨트롤 호스팅
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC는 Windows Forms 컨트롤을 특별한 종류의 ActiveX 컨트롤로 호스팅하고 ActiveX 인터페이스 및 속성과 <xref:System.Windows.Forms.Control> 클래스의 메서드를 사용하여 이 컨트롤과 통신합니다.  컨트롤에 대해 연산을 수행하려면 .NET Framework 속성 및 메서드를 사용하는 것이 좋습니다.  
  
 MFC와 함께 사용 하는 Windows Forms을 보여 주는 샘플 응용 프로그램은 [MFC 및 Windows Forms 통합](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)을 참조하십시오.  
  
> [!NOTE]
>  현재 릴리스에서 `CDialogBar` 개체는 Windows Forms 컨트롤을 호스팅할 수 없습니다.  
  
## 단원 내용  
 [방법: 대화 상자에 사용자 정의 컨트롤 및 호스트 만들기](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)  
  
 [방법: Windows Forms에서 DDX\/DDV 데이터 바인딩 수행](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)  
  
 [방법: 네이티브 C\+\+ 클래스에서 Windows Forms 이벤트 싱크](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)  
  
## 참조  
 [CWinFormsControl Class](../mfc/reference/cwinformscontrol-class.md) &#124; [CDialog Class](../mfc/reference/cdialog-class.md) &#124; [CWnd 클래스](../mfc/reference/cwnd-class.md) &#124; <xref:System.Windows.Forms.Control>  
  
## 참고 항목  
 [MFC에서 Windows Form 사용자 정의 컨트롤 사용](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Windows Forms\/MFC 프로그래밍의 차이점](../dotnet/windows-forms-mfc-programming-differences.md)   
 [Windows Forms 사용자 정의 컨트롤을 MFC 뷰로 호스팅](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [Windows Form 사용자 정의 컨트롤을 MFC 대화 상자로 호스팅](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)