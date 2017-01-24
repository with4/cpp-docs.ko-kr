---
title: "Adding Controls to a Dialog Causes the Dialog to No Longer Function | Microsoft Docs"
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
  - "C++"
helpviewer_keywords: 
  - "controls [C++], troubleshooting"
  - "common controls, troubleshooting"
  - "troubleshooting controls"
  - "dialog boxes, troubleshooting"
  - "dialog box controls, troubleshooting"
  - "InitCommonControls"
ms.assetid: b2dd4574-ea59-4343-8d65-b387cead5da6
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Controls to a Dialog Causes the Dialog to No Longer Function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

공용 컨트롤이나 rich edit 컨트롤을 대화 상자에 추가하고 대화 상자를 테스트하면 컨트롤이 표시되지 않거나 대화 상자 자체가 표시되지 않습니다.  
  
 **문제의 예**  
  
1.  Win32 프로젝트를 만들고 응용 프로그램 설정을 수정하여 콘솔 응용 프로그램이 아닌 Windows 응용 프로그램을 만듭니다.  
  
2.  [리소스 뷰](../windows/resource-view-window.md)에서 .rc 파일을 두 번 클릭합니다.  
  
3.  대화 상자 옵션에서 **정보** 상자를 두 번 클릭합니다.  
  
4.  대화 상자에 **IP Address 컨트롤**을 추가합니다.  
  
5.  저장하고 **모두 다시 빌드**를 실행합니다.  
  
6.  프로그램을 실행합니다.  
  
7.  대화 상자의 **도움말** 메뉴에서 **정보** 명령을 클릭해도 대화 상자가 표시되지 않습니다.  
  
 **원인**  
  
 현재는 대화 상자 편집기에서 다음과 같은 공용 컨트롤이나 rich edit 컨트롤을 대화 상자에 끌어서 놓을 때 사용자의 프로젝트에 코드가 자동으로 추가되지 않습니다.  Visual Studio에서도 이러한 문제에 대한 오류나 경고 메시지를 표시하지 않습니다.  따라서 다음 컨트롤의 코드는 직접 추가해야 합니다.  
  
||||  
|-|-|-|  
|Slider 컨트롤|Tree 컨트롤|Date Time Picker|  
|Spin 컨트롤|Tab 컨트롤|Month Calendar|  
|Progress 컨트롤|Animation 컨트롤|IP Address 컨트롤|  
|액셀러레이터 키|Rich Edit 컨트롤|Extended combo box 컨트롤|  
|List 컨트롤|Rich Edit 2.0 컨트롤|사용자 지정 컨트롤|  
  
## 공용 컨트롤에 대한 해결 방법  
 대화 상자에서 공용 컨트롤을 사용하려면 이 대화 상자를 만들기 전에 [InitCommonControlsEx](http://msdn.microsoft.com/library/windows/desktop/bb775697) 또는 **AFXInitCommonControls**를 호출해야 합니다.  
  
## RichEdit 컨트롤에 대한 해결 방법  
 rich edit 컨트롤용 **LoadLibrary**를 호출해야 합니다.  자세한 내용은 [MFC에 RichEdit 1.0 컨트롤 사용](../mfc/using-the-richedit-1-0-control-with-mfc.md), [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)]의 [About Rich Edit Controls](http://msdn.microsoft.com/library/windows/desktop/bb787873) 및 [Overview of the Rich Edit Control](../mfc/overview-of-the-rich-edit-control.md)을 참조하십시오.  
  
## 요구 사항  
 Win32  
  
## 참고 항목  
 [Troubleshooting the Dialog Editor](../mfc/troubleshooting-the-dialog-editor.md)   
 [Dialog Editor](../mfc/dialog-editor.md)