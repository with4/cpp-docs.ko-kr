---
title: "How to: Use Resource Templates | Microsoft Docs"
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
  - "language-specific template files"
  - "resource templates"
  - "resources [Visual Studio], creating"
  - "rct files"
  - "templates, resource templates"
  - "resources [Visual Studio], templates"
  - ".rct files"
ms.assetid: bdfe7060-f98e-4859-8285-9c8570360e9d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# How to: Use Resource Templates
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

리소스 템플릿은 .rct 파일로 저장한 사용자 지정 리소스입니다.  리소스 템플릿을 다른 리소스를 만들기 위한 시작 지점으로 사용할 수 있습니다.  리소스 템플릿을 사용하면 표준 컨트롤 및 기타 반복 요소와 같이 기능을 공유하는 추가 리소스 또는 리소스 그룹을 개발하는 시간을 절약할 수 있습니다.  예를 들어 여러 대화 상자에 도움말 단추와 회사 로고 아이콘을 포함할 수 있습니다.  이 작업을 빠르게 하려면 새 대화 상자 템플릿을 만들고 로고와 도움말 단추를 사용하여 템플릿을 사용자 지정합니다.  
  
 리소스 템플릿을 사용자 지정하고 나면 새 리소스 템플릿이 [리소스 추가 대화 상자](../windows/add-resource-dialog-box.md)의 리소스 형식 아래 표시되도록 템플릿 폴더\(또는 포함 경로에 지정된 위치\)에 변경 내용을 저장해야 합니다.  그다음에 새 리소스 템플릿을 필요할 때마다 사용할 수 있습니다.  
  
> [!NOTE]
>  주 템플릿 디렉터리의 하위 디렉터리에 언어 관련 템플릿 파일을 배치할 수 있습니다.  예를 들어 영어 전용 템플릿 파일을 \\\<리소스 템플릿 디렉터리\>\\1033에 배치할 수 있습니다.  
  
### 리소스에 대한 템플릿을 만들려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭합니다.  
  
2.  바로 가기 메뉴에서 **추가**를 선택하고 **새 항목 추가**를 클릭합니다.  
  
3.  **새 항목 추가** 대화 상자의 **템플릿:** 창에서 **리소스 템플릿 파일\(.rct\)**을 선택합니다.  
  
4.  새 .rct 파일의 이름 및 위치를 제공하고 **열기**를 클릭합니다.  
  
5.  새 .rct 파일이 프로젝트에 추가되고 솔루션 탐색기의 **리소스** 폴더 아래에 표시됩니다.  
  
     이제 .rct 파일을 두 번 클릭하여 문서 창에서 열고 리소스를 추가합니다\(문서 창에서 파일을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **리소스 추가**를 선택\).  그다음에 해당 리소스를 사용자 지정하고 .rct 파일을 저장할 수 있습니다.  
  
    > [!NOTE]
    >  새 RCT 파일을 만들 때 Visual Studio에서는 \\Program Files\\Microsoft Visual Studio 9.0\\VC\\VCResourceTemplates, \\Program Files\\Microsoft Visual Studio 9.0\\VC\\VCResourceTemplates\\*LCID*\(예: 영어의 경우 1033\) *또는* [포함 경로](../windows/how-to-specify-include-directories-for-resources.md)의 임의 위치에서 파일을 검색합니다.  RCT 파일을 다른 파일 폴더\(예: \\My Documents\)에 저장하려는 경우 이 폴더를 포함 경로에 추가하면 Visual Studio에서 RCT 파일을 찾습니다.  
  
### 기존 .rc 파일을 .rct 파일로 변환하려면  
  
1.  [.rc 파일을 독립 실행형 파일로 엽니다](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
2.  **파일** 메뉴에서 **다른 이름으로 \<*파일 이름*\> 저장**을 클릭합니다.  
  
3.  위치를 지정하고 **확인**을 클릭합니다.  
  
### 템플릿에서 새 리소스를 만들려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md) 창에서 .rc 파일을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **리소스 추가**를 선택합니다.  
  
2.  **리소스 추가** 대화 상자에서 리소스 옆에 있는 더하기 기호\(**\+**\)를 클릭하여 리소스 노드를 확장하고 해당 리소스에 사용 가능한 모든 템플릿을 확인합니다.  
  
3.  사용할 템플릿을 두 번 클릭합니다.  
  
4.  리소스 편집기에서 추가된 리소스를 필요에 따라 수정합니다.  
  
     리소스 편집기에서 자동으로 고유한 리소스 ID를 제공합니다.  필요에 따라 [리소스 속성](../windows/changing-the-properties-of-a-resource.md)을 수정할 수 있습니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요.  
  
 요구 사항  
  
 Win32  
  
## 참고 항목  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)