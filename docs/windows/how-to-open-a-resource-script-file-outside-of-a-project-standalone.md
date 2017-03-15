---
title: "How to: Open a Resource Script File Outside of a Project (Standalone) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.resource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], viewing"
  - "rc files, viewing resources"
  - ".rc files, viewing resources"
  - "resource script files, viewing resources"
ms.assetid: bc350c60-178d-4c5d-9a7e-6576b0c936e4
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# How to: Open a Resource Script File Outside of a Project (Standalone)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로젝트를 열지 않고도 .rc 파일에서 리소스를 볼 수 있습니다.  .rc 파일은 프로젝트 내부에서 파일이 열릴 때처럼 [리소스 뷰](../windows/resource-view-window.md) 창에서 열리지 않고 문서 창에서 열립니다.  
  
> [!NOTE]
>  일부 명령은 파일이 프로젝트 외부에서 독립 실행형으로 열릴 때만 사용할 수 있으므로 이는 중요한 차이점입니다.  예를 들어 파일이 프로젝트 외부에서 열릴 경우 파일을 다른 형식 또는 다른 파일 이름으로만 저장할 수 있습니다. 파일이 프로젝트 내부에서 열리면 **다른 이름으로 저장** 명령을 사용할 수 없습니다.  
  
### 프로젝트 외부에서 .rc 파일을 열려면  
  
1.  **파일** 메뉴에서 **열기**를 선택하고 **파일**을 클릭합니다.  
  
2.  **파일 열기** 대화 상자에서 보려는 리소스 스크립트 파일로 이동하고 파일을 강조 표시하고 **열기**를 클릭합니다.  
  
    > [!NOTE]
    >  프로젝트를 먼저 열면\(**파일**, **열기**, **프로젝트**\) 일부 명령을 사용할 수 없습니다.  파일을 "독립 실행형"으로 여는 것은 프로젝트를 먼저 로드하지 않고 파일을 여는 것입니다.  
  
 리소스 파일을 텍스트 형식으로 열고 보려면 [리소스 스크립트\(.rc\) 파일 편집](../windows/how-to-open-a-resource-script-file-in-text-format.md)을 참조하세요.  
  
#### 프로젝트 외부에서 여러 .rc 파일을 열려면  
  
1.  두 리소스 파일을 모두 독립 실행형으로 엽니다.  예를 들어 Source1.rc 및 Source2.rc를 엽니다.  
  
    1.  **파일** 메뉴에서 **열기**를 선택하고 **파일**을 클릭합니다.  
  
    2.  **파일 열기** 대화 상자에서 열려는 리소스 스크립트 파일\(Source1.rc\)로 이동하고 파일을 강조 표시하고 **열기**를 클릭합니다.  
  
    3.  이전 단계를 반복해서 두 번째 .rc 파일\(Source2.rc\)을 엽니다.  
  
         .rc 파일이 이제 개별 문서 창으로 열려 있습니다.  
  
2.  두 .rc 파일이 모두 열리면 두 파일을 동시에 볼 수 있도록 창을 바둑판식으로 배열합니다.  
  
    -   **창** 메뉴에서 **새 가로 탭 그룹** 또는 **새 세로 탭 그룹**을 선택합니다.  
  
         또는  
  
    -   .rc 파일의 하나를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **새 가로 탭 그룹** 또는 **새 세로 탭 그룹**을 선택합니다.  
  
> [!NOTE]
>  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
### 요구 사항  
 Win32  
  
## 참고 항목  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)