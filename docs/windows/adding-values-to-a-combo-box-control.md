---
title: "Adding Values to a Combo Box Control | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.dialog.combo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "combo boxes [C++], Data property"
  - "controls [Visual Studio], testing values in combo boxes"
  - "combo boxes [C++], adding values"
  - "combo boxes [C++], previewing values"
  - "controls [C++], testing values in combo boxes"
  - "Data property"
  - "combo boxes [C++], testing values"
ms.assetid: 22a78f98-fada-48b3-90d8-7fa0d8e4de51
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Values to a Combo Box Control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대화 상자 편집기가 열려 있으면 콤보 상자 컨트롤에 값을 추가할 수 있습니다.  
  
> [!TIP]
>  대화 상자 편집기에서 상자 크기를 조정하기 *전에* 콤보 상자에 모든 값을 추가하는 것이 좋습니다. 값을 먼저 추가하지 않으면 콤보 상자 컨트롤에 표시되는 텍스트가 잘릴 수 있습니다.  
  
#### 콤보 상자 컨트롤에 값을 입력하려면  
  
1.  콤보 상자 컨트롤을 클릭하여 선택합니다.  
  
2.  [속성 창](../Topic/Properties%20Window.md)에서 **데이터** 속성이 나올 때까지 아래로 스크롤합니다.  
  
    > [!NOTE]
    >  속성을 형식별로 그룹화하여 표시하면 **기타** 속성에 **데이터**가 표시됩니다.  
  
3.  **데이터** 속성의 값 영역을 클릭하고 데이터 값을 세미콜론으로 구분하여 입력합니다.  
  
    > [!NOTE]
    >  공백을 사용하면 드롭다운 목록이 사전순으로 정렬되지 않으므로 값 사이에 공백을 넣지 마십시오.  
  
4.  값 추가가 완료되면 **Enter** 키를 누릅니다.  
  
 콤보 상자의 드롭다운 부분 확대에 대한 자세한 내용은 [콤보 상자 및 드롭다운 목록의 크기 설정](../mfc/setting-the-size-of-the-combo-box-and-its-drop-down-list.md)을 참조하십시오.  
  
> [!NOTE]
>  Win32 프로젝트의 **데이터** 속성은 비활성화되어 있기 때문에 Win32 프로젝트에는 이러한 방법으로 값을 추가할 수 없습니다.  Win32 프로젝트에는 이 기능을 추가하는 라이브러리가 없으므로 Win32 프로젝트에서는 프로그래밍을 통해 콤보 상자에 값을 추가해야 합니다.  
  
#### 콤보 상자에서 표시 값을 테스트하려면  
  
1.  **데이터** 속성에 값을 입력한 후 [대화 상자 편집기 도구 모음](../mfc/showing-or-hiding-the-dialog-editor-toolbar.md)에서 **테스트** 단추를 클릭합니다.  
  
     전체 값 목록을 아래로 스크롤합니다.  속성 창의 **데이터** 속성에 입력한 대로 값이 표시됩니다.  맞춤법이나 대\/소문자 검사는 하지 않습니다.  
  
     대화 상자 편집기로 돌아가려면 Esc 키를 누릅니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
### 요구 사항  
 Win32  
  
## 참고 항목  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [컨트롤](../mfc/controls-mfc.md)