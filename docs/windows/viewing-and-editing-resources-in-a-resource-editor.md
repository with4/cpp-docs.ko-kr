---
title: "Viewing and Editing Resources in a Resource Editor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.resourceview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], viewing"
  - "rc files, viewing resources"
  - "Resource View pane"
  - "layouts, previewing resource"
  - "code, viewing resources"
  - "resource editors, viewing resources"
  - ".rc files, viewing resources"
  - "resources [Visual Studio], editing"
ms.assetid: ba8bdc07-3f60-43c7-aa5c-d5dd11f0966e
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Viewing and Editing Resources in a Resource Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

리소스 형식마다 사용할 수 있는 리소스 편집기가 있습니다.  연결된 편집기를 사용하여 컨트롤과 기능을 추가하고 재조정하고 크기를 변경할 수도 있고 리소스의 항목들을 수정할 수도 있습니다.  [텍스트 형식](../windows/how-to-open-a-resource-script-file-in-text-format.md)과 [바이너리 형식](../mfc/opening-a-resource-for-binary-editing.md) 리소스를 편집할 수도 있습니다.  
  
 비트맵, 아이콘, 커서, 도구 모음 및 html 파일과 같은 일부 리소스 형식은 여러 가지 방법으로 가져와 사용할 수 있는 독립된 파일입니다.  이러한 리소스에는 [리소스 식별자](../mfc/symbols-resource-identifiers.md)뿐 아니라 파일 이름도 있습니다.  Win32 프로젝트에 있는 대화 상자, 메뉴, 문자열 테이블 등과 같은 다른 리소스는 리소스 스크립트 파일\(.rc\)이나 리소스 템플릿 파일\(.rct\)에만 포함됩니다.  
  
> [!NOTE]
>  리소스 속성은 [속성 창을 통해 변경](../windows/changing-the-properties-of-a-resource.md)할 수 있습니다.  
  
## Win32 리소스  
 [리소스 뷰](../windows/resource-view-window.md) 창에서 다음과 같은 방법으로 Win32 리소스에 액세스할 수 있습니다.  
  
#### Win32 리소스 편집기에서 리소스를 보려면  
  
1.  **보기** 메뉴에서 **리소스 뷰**를 선택합니다.  
  
2.  리소스 뷰 창이 맨 위 창이 아니면 **리소스 뷰** 탭을 클릭하여 맨 위로 이동합니다.  
  
3.  리소스 뷰 창에서 보려는 리소스가 있는 프로젝트의 폴더를 확장합니다.  예를 들어, 대화 상자 리소스를 보려면 Dialog 폴더를 확장합니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 없으면 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하십시오.  
  
4.  IDD\_ABOUTBOX와 같은 리소스를 두 번 클릭합니다.  
  
     해당 편집기에 리소스가 열립니다.  예를 들어, 대화 상자 리소스는 대화 상자 편집기에서 열립니다.  
  
     [프로젝트를 열지 않고 .rc\(리소스 스크립트\) 파일에서 리소스를 볼](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md) 수도 있습니다.  
  
#### 기존 Win32 리소스를 삭제하려면  
  
1.  리소스 뷰에서 리소스 형식 노드를 확장합니다.  
  
2.  마우스 오른쪽 단추로 삭제할 리소스를 클릭하고 바로 가기 메뉴에서 **삭제**를 선택합니다.  
  
    > [!NOTE]
    >  프로젝트 외부의 .rc 파일을 문서 창에 열었을 경우에도 동일한 바로 가기 메뉴 명령을 사용하여 리소스를 삭제할 수 있습니다.  
  
## 관리되는 프로젝트의 리소스  
 관리되는 프로젝트에서는 리소스 스크립트 파일을 사용하지 않으므로 **솔루션 탐색기**에서 리소스를 열어야 합니다.  관리되는 프로젝트에서 리소스 파일에 대해 작업할 때는 [이미지 편집기](../mfc/image-editor-for-icons.md)와 [바이너리 편집기](../mfc/binary-editor.md)를 사용할 수 있습니다.  편집할 관리되는 리소스는 연결된 리소스여야 합니다.  Visual Studio 리소스 편집기에서는 포함된 리소스를 편집할 수 없습니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
#### 리소스 편집기에서 관리되는 리소스를 보려면  
  
1.  솔루션 탐색기에서 리소스\(예: Bitmap1.bmp\)를 두 번 클릭합니다.  
  
     해당 편집기에 리소스가 열립니다.  
  
#### 기존 관리되는 리소스를 삭제하려면  
  
1.  솔루션 탐색기에서 마우스 오른쪽 단추로 리소스를 클릭하고 바로 가기 메뉴에서 **삭제**를 선택합니다.  
  
### 요구 사항  
 없음  
  
## 참고 항목  
 [Resource Editors](../mfc/resource-editors.md)