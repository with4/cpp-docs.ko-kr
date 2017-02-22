---
title: "How to: Copy Resources | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.resvw.resource.copying"
  - "vs.resvw.resource.copying"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], moving between files"
  - "resources [Visual Studio], copying"
  - "resource files, copying or moving resources between"
  - "resource files, tiling"
  - ".rc files, copying resources between"
  - "rc files, copying resources between"
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# How to: Copy Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

리소스를 변경하지 않고 한 파일에서 다른 파일로 복사할 수도 있고, [복사할 때 리소스의 언어 또는 조건을 변경](../windows/how-to-change-the-language-or-condition-of-a-resource-while-copying.md)할 수도 있습니다.  
  
 기존 리소스 파일이나 실행 파일에서 현재 리소스 파일로 쉽게 리소스를 복사할 수 있습니다.  리소스를 복사하려면 리소스가 포함된 두 파일을 동시에 열고 한 파일에서 다른 파일로 항목을 끌거나 복사하여 붙여넣습니다.  실행 파일\(.exe\)뿐 아니라 소스 스크립트 파일\(.rc\)과 리소스 템플릿 파일\(.rct\)에도 이 방법을 사용할 수 있습니다.  
  
> [!NOTE]
>  Visual C\+\+에는 사용자의 응용 프로그램에 사용할 수 있는 샘플 리소스 파일이 있습니다.  자세한 내용은 [CLIPART 샘플: 공용 리소스](http://msdn.microsoft.com/ko-kr/9bac2891-b6b3-49ec-a287-cec850c707e0)를 참조하십시오.  
  
 [프로젝트 외부에서](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md) 열린 .rc 파일 간에는 끌어서 놓기 방법을 사용할 수 있습니다 .  
  
### 끌어서 놓기 방법을 사용하여 파일 사이에 리소스를 복사하려면  
  
1.  리소스 파일 두 개를 독립 실행형으로 엽니다. 자세한 내용은 [프로젝트 외부에서 리소스 스크립트 파일 열기\(독립 실행형\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)를 참조하십시오.  예를 들어, Source1.rc 파일과 Source2.rc 파일을 엽니다.  
  
2.  첫 번째 .rc 파일에서 복사할 리소스를 클릭합니다.  예를 들어, Source1.rc 파일에서 IDD\_DIALOG1을 클릭합니다.  
  
3.  Ctrl 키를 누른 채로 해당 리소스를 두 번째 .rc 파일로 끕니다.  예를 들어, Source1.rc 파일의 IDD\_DIALOG1을 Source2.rc 파일로 끕니다.  
  
    > [!NOTE]
    >  Ctrl 키를 누르지 않은 채로 리소스를 끌면 리소스가 복사되지 않고 이동됩니다.  
  
### 복사하여 붙여넣기를 사용하여 리소스를 복사하려면  
  
1.  리소스 파일 두 개를 독립 실행형으로 엽니다. 자세한 내용은 [프로젝트 외부에서 리소스 스크립트 파일 열기\(독립 실행형\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)를 참조하십시오.  예를 들어, Source1.rc 파일과 Source2.rc 파일을 엽니다.  
  
2.  복사할 리소스가 있는 소스 파일\(예: Source1.rc\)에서 마우스 오른쪽 단추로 리소스를 클릭하고 바로 가기 메뉴에서 **복사**를 선택합니다.  
  
3.  리소스를 붙여넣을 리소스 파일\(예: Source2.rc\)을 마우스 오른쪽 단추로 클릭합니다.  바로 가기 메뉴에서 **붙여넣기**를 선택합니다.  
  
    > [!NOTE]
    >  리소스 뷰에서 연 프로젝트 내의 리소스 파일과 문서 창에서 연 독립 실행형 .rc 파일 사이에는 끌어서 놓기, 복사, 잘라내기, 붙여넣기 등의 방법을 사용할 수 없습니다.  이전 버전에서는 이 작업을 할 수 있었습니다.  
  
    > [!NOTE]
    >  리소스를 새 파일로 복사할 때 기존 파일에 있는 기호 이름이나 값과 충돌하지 않도록 Visual C\+\+에서 복사되는 리소스의 기호 값이나 기호 이름을 변경할 수도 있습니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 요구 사항  
  
 Win32  
  
## 참고 항목  
 [How to: Open a Resource Script File Outside of a Project \(Standalone\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)