---
title: "ActiveX 컨트롤 컨테이너: ActiveX 컨트롤을 멤버 변수에 연결 | Microsoft Docs"
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
  - "ActiveX 컨트롤 컨테이너[C++], ActiveX 컨트롤 액세스"
  - "ActiveX 컨트롤 컨테이너[C++], ActiveX 컨트롤을 멤버 변수로"
  - "ActiveX 컨트롤[C++], 액세스"
  - "ActiveX 컨트롤[C++], 프로젝트의 멤버 변수"
  - "컨테이너 멤버 변수에 ActiveX 컨트롤 연결"
  - "멤버 변수[C++], 프로젝트의 ActiveX 컨트롤"
ms.assetid: 7898a336-440d-4a60-be43-cb062b807aee
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ActiveX 컨트롤 컨테이너: ActiveX 컨트롤을 멤버 변수에 연결
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The easiest way to access an ActiveX control from within its control container application is to associate the ActiveX control with a member variable of the dialog class that will contain the control.  
  
> [!NOTE]
>  This is not the only way to access an embedded control from within a container class, but for the purposes of this article it is sufficient.  
  
### Adding a member variable to the dialog class  
  
1.  From Class View, right\-click the main dialog class to open the shortcut menu.  예를 들면 `CContainerDlg`와 같습니다.  
  
2.  From the shortcut menu, click **Add** and then **Add Variable**.  
  
3.  In the Add Member Variable Wizard, click **Control variable**.  
  
4.  In the **Control ID** list box, select the control ID of the embedded ActiveX control.  예를 들면 `IDC_CIRCCTRL1`와 같습니다.  
  
5.  In the **Variable Name** box, enter a name.  
  
     예를 들면 `m_circctl`와 같습니다.  
  
6.  Click **Finish** to accept your choices and exit the Add Member Variable Wizard.  
  
## 참고 항목  
 [ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)