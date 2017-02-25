---
title: "Resource Editors | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.editors.resource"
  - "vc.resvw.resource.editors"
  - "vs.resvw.resource.editors"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "editors [C++], resource"
  - "editors [C++]"
  - "resource editors"
  - "Windows [C++], application resource editing"
ms.assetid: e20a29ec-d6fb-4ead-98f3-431a0e23aaaf
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Resource Editors
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

리소스 편집기는 Visual Studio 프로젝트에 포함된 리소스를 만들거나 수정하기 위해 만들어진 특수한 환경입니다. Visual Studio 리소스 편집기는 응용 프로그램 리소스를 쉽고 빠르게 만들고 수정할 수 있도록 기술 및 인터페이스를 공유합니다. 리소스 편집기를 사용하면 [적절한 편집기에서 리소스를 보고 편집](../mfc/viewing-and-editing-resources-in-a-resource-editor.md)하며 [리소스를 미리 볼](../mfc/previewing-resources.md) 수 있습니다.  
  
 리소스를 만들거나 열면 적절한 편집기가 자동으로 열립니다.  
  
 **참고** 관리되는 프로젝트는 리소스 스크립트 파일을 사용하지 않으므로 **솔루션 탐색기**에서 리소스를 열 필요가 없습니다. 관리되는 프로젝트에서 리소스 파일로 작업하려면 [이미지 편집기](../mfc/image-editor-for-icons.md) 및 [바이너리 편집기](../mfc/binary-editor.md)를 사용할 수 있습니다. 편집할 관리되는 리소스는 연결된 리소스여야 합니다. Visual Studio 리소스 편집기에서는 포함된 리소스를 편집할 수 없습니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 *.NET Framework 개발자 가이드*에서 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
|사용...|편집...|  
|-----------|-----------|  
|[액셀러레이터 키 편집기](../mfc/accelerator-editor.md)|Visual C\+\+ 프로젝트의 액셀러레이터 키 테이블입니다.|  
|[바이너리 편집기](../mfc/binary-editor.md)|Visual C\+\+, Visual Basic 또는 Visual C\# 프로젝트의 이진 데이터 정보 및 사용자 지정 리소스입니다.|  
|[대화 상자 편집기](../mfc/dialog-editor.md)|Visual C\+\+ 프로젝트의 대화 상자입니다.|  
|[HTML 디자이너](../Topic/HTML%20Designer.md)|디자인 뷰와 HTML 뷰의 HTML 페이지입니다. 주의 사항: EXE나 DLL의 HTML 페이지를 변경하면 변경 내용을 EXE나 DLL로 다시 가져올 수 없기 때문에 변경할 수 없습니다.|  
|[이미지 편집기](../mfc/image-editor-for-icons.md)|Visual C\+\+, Visual Basic 또는 Visual C\# 프로젝트의 비트맵, 아이콘, 커서 및 기타 이미지 파일입니다.|  
|[메뉴 편집기](../mfc/menu-editor.md)|Visual C\+\+ 프로젝트의 메뉴 리소스입니다.|  
|[리본 편집기](../mfc/ribbon-designer-mfc.md)|MFC 프로젝트의 리본 리소스입니다.|  
|[문자열 편집기](../mfc/string-editor.md)|Visual C\+\+ 프로젝트의 문자열 표입니다.|  
|[도구 모음 편집기](../mfc/toolbar-editor.md)|Visual C\+\+ 프로젝트의 도구 모음 리소스입니다. 도구 모음 편집기는 이미지 편집기의 일부입니다.|  
|[버전 정보 편집기](../mfc/version-information-editor.md)|Visual C\+\+ 프로젝트의 버전 정보입니다.|  
  
## 요구 사항  
 없음  
  
## 참고 항목  
 [Working with Resource Files](../mfc/working-with-resource-files.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)   
 [메뉴 및 기타 리소스](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)