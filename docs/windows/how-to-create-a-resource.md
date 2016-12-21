---
title: "How to: Create a Resource | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "toolbars [C++], resources"
  - "resource toolbars"
  - "resources [Visual Studio], creating"
ms.assetid: aad44914-9145-45a3-a7d8-9de89b366716
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Create a Resource
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Express 버전에서는 리소스 뷰가 지원되지 않습니다.  
  
### 리소스 뷰에서 새 리소스를 만들려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md)에서 포커스가 .rc 파일에 있을 때 **편집** 메뉴를 클릭하고 **리소스 추가**를 선택하거나, 리소스 뷰에서 .rc 파일을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **리소스 추가**를 선택합니다.  
  
     **참고** 프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  [리소스 추가 대화 상자](../windows/add-resource-dialog-box.md)에서 프로젝트에 추가할 리소스 형식을 선택합니다.  
  
### 솔루션 탐색기에서 새 리소스를 만들려면  
  
1.  **솔루션 탐색기**에서 프로젝트 폴더를 마우스 오른쪽 단추로 클릭하고 **추가**를 선택하고 바로 가기 메뉴에서 **리소스 추가**를 클릭합니다.  
  
     프로젝트에 .rc 파일이 없으면 이 단계에서 해당 파일을 만듭니다. 그런 다음 이 단계를 반복하여 새.rc 파일에 특정 리소스 형식을 추가할 수 있습니다.  
  
2.  [리소스 추가 대화 상자](../windows/add-resource-dialog-box.md)에서 프로젝트에 추가할 리소스 형식을 선택합니다.  
  
### 클래스 뷰에서 새 리소스를 만들려면  
  
1.  [클래스 뷰](http://msdn.microsoft.com/ko-kr/8d7430a9-3e33-454c-a9e1-a85e3d2db925)에서 클래스를 마우스 오른쪽 단추로 클릭하고 **추가**를 선택하고 바로 가기 메뉴에서 **리소스 추가**를 클릭합니다.  
  
2.  [리소스 추가 대화 상자](../windows/add-resource-dialog-box.md)에서 프로젝트에 추가할 리소스 형식을 선택합니다.  
  
### 프로젝트 메뉴에서 새 리소스를 만들려면  
  
1.  **프로젝트** 메뉴에서 **리소스 추가**를 선택합니다.  
  
 새 리소스를 만들 때 Visual C\+\+에서는 IDD\_Dialog1과 같은 고유한 이름을 할당합니다. 연결된 리소스 편집기 또는 [속성 창](../Topic/Properties%20Window.md)에서 리소스에 대한 속성을 편집하여 이 리소스 ID를 사용자 지정할 수 있습니다.  
  
 리소스를 새 기본 리소스\(템플릿에 기반을 두지 않은 리소스\) 또는 [템플릿](../windows/how-to-use-resource-templates.md)을 기반으로 패턴화된 리소스로 만들 수 있습니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 *.NET Framework 개발자 가이드*에서 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요.  
  
 **요구 사항**  
  
 Win32  
  
## 참고 항목  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)   
 [리소스 추가 대화 상자](../windows/add-resource-dialog-box.md)