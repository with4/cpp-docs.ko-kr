---
title: "How to: Add MFC Support to Resource Script Files | Microsoft Docs"
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
  - "vc.resvw.add.MFC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rc files, adding MFC support"
  - ".rc files, adding MFC support"
  - "MFC, adding support to resource scripts files"
  - "resource script files, adding MFC support"
ms.assetid: 599dfe9d-ad26-4e34-899c-49b56599e37f
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Add MFC Support to Resource Script Files
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

일반적으로 [MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md)를 사용하여 Windows용 MFC 응용 프로그램을 빌드하면 마법사에서 MFC\(Microsoft Foundation Class\)의 핵심 기능이 포함된 기본 파일 집합\(리소스 스크립트\(.rc\) 파일 포함\)을 생성합니다.  그러나 MFC를 기반으로 하지 않는 Windows 응용 프로그램용 .rc 파일을 편집하는 경우에는 MFC 프레임워크와 관련된 다음 기능을 사용할 수 없습니다.  
  
-   MFC 코드 마법사\(이전의 "[MFC ClassWizard](http://msdn.microsoft.com/ko-kr/98dc2434-ba93-4e0b-b084-1a4bc26cdf1e)"\)  
  
-   메뉴 프롬프트 문자열  
  
-   콤보 상자 컨트롤에 대한 내용 나열  
  
-   ActiveX 컨트롤 호스팅  
  
 그러나 MFC 지원이 없는 기존 .rc 파일에 해당 지원을 추가할 수 있습니다.  
  
### .rc 파일에 MFC 지원을 추가하려면  
  
1.  리소스 스크립트 파일을 엽니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  [리소스 뷰](../windows/resource-view-window.md)에서 리소스 폴더\(예: MFC.rc\)를 강조 표시합니다.  
  
3.  [속성](../Topic/Properties%20Window.md) 창에서 **MFC Mode** 속성을 **True**로 설정합니다.  
  
    > [!NOTE]
    >  이 플래그를 설정하는 것 외에도 .rc 파일은 MFC 프로젝트의 일부여야 합니다.  예를 들어 **MFC Mode**를 **True**로 설정하는 것만으로는 Win32 프로젝트의 .rc 파일에서 MFC 기능을 제공하지 않습니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
 **요구 사항**  
  
 MFC  
  
## 참고 항목  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)