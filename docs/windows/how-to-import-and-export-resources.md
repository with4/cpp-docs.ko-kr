---
title: "How to: Import and Export Resources | Microsoft Docs"
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
  - "vs.resvw.resource.importing"
  - "vc.resvw.resource.importing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], exporting"
  - "graphics [C++], exporting"
  - "graphics [C++], importing"
  - "resources [Visual Studio], importing"
  - "bitmaps [C++], importing and exporting"
  - "toolbars [C++], importing"
  - "images [C++], importing"
  - "toolbars [C++], exporting"
  - "cursors [C++], importing and exporting"
  - "images [C++], exporting"
ms.assetid: 3c9329dc-dcb8-4edd-a600-78e3e572bd89
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Import and Export Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+에서 사용하도록 그래픽 리소스\(비트맵, 아이콘, 커서 및 도구 모음\), HTML 파일 및 사용자 지정 리소스를 가져올 수 있습니다.  Visual C\+\+ 프로젝트에서 동일한 형식의 파일을 개발 환경 외부에서 사용할 수 있는 별도의 파일로 내보낼 수 있습니다.  
  
> [!NOTE]
>  액셀러레이터 키, 대화 상자 및 문자열 테이블과 같은 리소스 종류는 독립 실행형 파일 형식이 아니므로 가져오거나 내보낼 수 없습니다.  
  
### 현재 리소스 파일로 개별 리소스를 가져오려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md)에서 리소스를 추가할 리소스 스크립트\(\*.rc\) 파일에 대한 노드를 마우스 오른쪽 단추로 클릭합니다.  
  
2.  바로 가기 메뉴에서 **가져오기**를 클릭합니다.  
  
3.  비트맵\(.bmp\), 아이콘\(.ico\), 커서\(.cur\), Html 파일\(.htm\) 또는 기타 가져오려는 파일의 파일 이름을 찾아 선택합니다.  
  
4.  **확인**을 클릭하여 **리소스** 보기에서 선택한 파일에 리소스를 추가합니다.  
  
    > [!NOTE]
    >  가져오기 프로세스는 선택한 특정 리소스 종류에 관계없이 동일한 방식으로 작동합니다.  가져온 리소스는 해당 리소스 종류에 적합한 노드에 자동으로 추가됩니다.  
  
### Visual C\+\+ 외부에서 사용하도록 비트맵, 아이콘 또는 커서를 별도의 파일로 내보내려면  
  
1.  **리소스** 보기에서 내보낼 리소스를 마우스 오른쪽 단추로 클릭합니다.  
  
2.  바로 가기 메뉴에서 **내보내기**를 클릭합니다.  
  
3.  **리소스 내보내기** 대화 상자에서 현재 파일 이름을 사용하거나 새 이름을 입력합니다.  
  
4.  파일을 저장하려는 폴더로 이동하고 **내보내기**를 클릭합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
 요구 사항  
  
 Win32  
  
## 참고 항목  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)