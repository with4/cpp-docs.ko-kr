---
title: "Adding Version Information for Another Language | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.version"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "languages, version information"
  - "New Version Info Block"
  - "blocks, adding"
  - "resources [Visual Studio], adding version information"
  - "version information, adding for languages"
ms.assetid: 17f6273c-e1cc-441a-a3d8-f564341cbf20
caps.latest.revision: 14
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Version Information for Another Language
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### 다른 언어의 버전 정보\(새로운 정보 블록\)를 추가하려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md)에서 버전 정보 리소스를 두 번 클릭하여 이를 엽니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  버전 정보 테이블 내에서 마우스 오른쪽 단추를 클릭하고 바로 가기 메뉴에서 **새 버전 정보 블록**을 선택합니다.  
  
     이 명령은 현재 버전 정보 리소스에 추가 정보 블록을 추가하고 [속성 창](../Topic/Properties%20Window.md)에서 해당 속성을 엽니다.  
  
3.  **속성** 창에서 새 블록에 적절한 언어 및 문자 집합을 선택합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 *.NET Framework 개발자 가이드*에서 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
 **요구 사항**  
  
 Win32  
  
## 참고 항목  
 [Version Information Editor](../mfc/version-information-editor.md)   
 [버전 정보\(Windows\)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)