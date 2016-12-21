---
title: "Version Information Editor | Microsoft Docs"
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
  - "vc.editors.version.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Version Information editor, about Version Information editor"
  - "editors, Version Information"
  - "resource editors, Version Information editor"
ms.assetid: 772e6f19-f765-4cec-9521-0ad3eeb99f9b
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Version Information Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

버전 정보는 회사 및 제품 ID, 제품 릴리스 번호, 저작권 및 상표 알림 등으로 이루어져 있습니다. 버전 정보 편집기를 사용하면 버전 정보 리소스에 저장되는 이 데이터를 만들고 유지 관리할 수 있습니다. 버전 정보 리소스는 응용 프로그램에 필요하지 않지만 응용 프로그램을 식별하는 정보를 수집하기에 유용한 장소입니다. 버전 정보는 설치 API에도 사용됩니다.  
  
 버전 정보 리소스에는 하나의 상위 블록과 하나 이상의 하위 블록이 있습니다. 위쪽에는 단일 고정 정보 블록이 있고, 아래쪽에는 하나 이상의 버전 정보 블록\(다른 언어 및\/또는 문자 집합에 대한 정보 블록\)이 있습니다. 위쪽 블록에는 편집 가능한 숫자 상자와 선택 가능한 드롭다운 목록이 모두 있습니다. 하위 블록에는 편집 가능한 텍스트 상자만 있습니다.  
  
> [!NOTE]
>  Windows 표준은 VS\_VERSION\_INFO라고 하는 하나의 버전 리소스만 포함합니다.  
  
 버전 정보 편집기를 사용하면 다음 작업을 수행할 수 있습니다.  
  
-   [버전 정보 리소스의 문자열 편집](../mfc/editing-a-string-in-a-version-information-resource.md)  
  
-   [다른 언어의 버전 정보\(새 버전 정보 블록\) 추가](../mfc/adding-version-information-for-another-language.md)  
  
-   [버전 정보 블록 삭제](../mfc/deleting-a-version-information-block.md)  
  
-   [프로그램 내에서 버전 정보 액세스](../mfc/accessing-version-information-from-within-your-program.md)  
  
    > [!NOTE]
    >  버전 정보 편집기를 사용하는 동안 대개 마우스 오른쪽 단추를 클릭하면 리소스별 명령의 바로 가기 메뉴를 표시할 수 있습니다. 예를 들어 블록 헤더 항목을 가리키는 동안 클릭하면 바로 가기 메뉴에 새 버전 블록 정보 및 버전 블록 정보 삭제 명령이 표시됩니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 *.NET Framework 개발자 가이드*에서 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
## 요구 사항  
 Win32  
  
## 참고 항목  
 [Resource Editors](../mfc/resource-editors.md)   
 [메뉴 및 기타 리소스](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)