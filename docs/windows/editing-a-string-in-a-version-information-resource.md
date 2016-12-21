---
title: "Editing a String in a Version Information Resource | Microsoft Docs"
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
  - "version information resources"
  - "resources [Visual Studio], editing version information"
ms.assetid: d3a7d4e4-7d31-47c2-902c-f50b8404ba4f
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Editing a String in a Version Information Resource
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### 버전 정보 리소스의 문자열을 편집하려면  
  
1.  항목을 한 번 클릭하여 선택하고 다시 클릭하여 편집을 시작합니다. 버전 정보 테이블에서 직접 변경하거나 [속성 창](../Topic/Properties%20Window.md)에서 변경합니다. 변경 내용은 두 위치에 모두 반영됩니다.  
  
     **참고** 버전 정보 편집기에서 **FILEFLAGS** 키를 편집할 때 속성 창에서 .rc 파일에 대한 **디버그**, **개인 빌드** 또는 **특수 빌드** 속성을 편집할 수 없습니다.  
  
    -   버전 정보 편집기에서는 **\_DEBUG** 빌드 플래그에 따라 리소스 스크립트의 \#ifdef를 사용하여 **디버그** 속성을 설정합니다.  
  
    -   **Private Build** 키에 버전 정보 테이블에서 설정된 **값**이 있으면 속성 창에서 **FILEFLAGS** 키에 해당하는 **개인 빌드** 속성이 **True**가 됩니다.**값**이 비어 있으면 속성이 **False**가 됩니다. 마찬가지로 버전 정보 테이블의 **Special Build** 키는 **FILEFLAGS** 키에 대한 **특수 빌드** 속성에 연결됩니다.  
  
 키 또는 값 열 머리글을 클릭하여 문자열 블록의 정보 시퀀스를 정렬할 수 있습니다. 이들 머리글은 정보를 선택한 시퀀스로 자동으로 다시 정렬합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 *.NET Framework 개발자 가이드*에서 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
 **요구 사항**  
  
 Win32  
  
## 참고 항목  
 [Version Information Editor](../mfc/version-information-editor.md)   
 [버전 정보\(Windows\)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)