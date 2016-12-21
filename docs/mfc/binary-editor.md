---
title: "Binary Editor | Microsoft Docs"
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
  - "vc.editors.binary.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "editors, Binary"
  - "resources [Visual Studio], editing"
  - "resource editors, Binary editor"
  - "Binary editor"
ms.assetid: 2483c48b-1252-4dbc-826b-82e6c1a0e9cb
caps.latest.revision: 14
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Binary Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!WARNING]
>  Express 버전에서는 바이너리 편집기를 사용할 수 없습니다.  
  
 바이너리 편집기를 사용하면 16진수 또는 ASCII 형식으로 바이너리 수준에서 리소스를 편집할 수 있습니다. 또한 [찾기 명령](../Topic/Find%20Command.md)을 사용하여 ASCII 문자열 또는 16진수 바이트를 검색할 수도 있습니다. Visual Studio 환경에서 지원하지 않는 사용자 지정 리소스 또는 리소스 형식을 보거나 조금 변경해야 하는 경우에만 바이너리 편집기를 사용해야 합니다.  
  
 바이너리 편집기를 열려면 먼저 주 메뉴에서 **파일 &#124; 새로 만들기 &#124; 파일**을 선택하고 편집할 파일을 선택한 다음 **열기** 단추 옆의 드롭다운 화살표를 클릭하고 **열기 &#124; 바이너리 편집기**를 선택합니다.  
  
> [!CAUTION]
>  바이너리 편집기에서 대화 상자, 이미지 또는 메뉴와 같은 리소스를 편집하는 것은 위험합니다. 잘못된 편집으로 리소스가 손상되어 해당 네이티브 편집기에서 읽지 못하게 될 수 있습니다.  
  
> [!TIP]
>  여러 인스턴스에서 바이너리 편집기를 사용하는 동안 마우스 오른쪽 단추를 클릭하여 리소스와 관련된 명령의 바로 가기 메뉴를 표시할 수 있습니다. 사용할 수 있는 명령은 커서가 가리키는 내용에 따라 달라집니다. 예를 들어 16진수 값을 선택하고 바이너리 편집기를 가리키는 동안 클릭하면 바로 가기 메뉴에 **잘라내기**, **복사** 및 **붙여넣기** 명령이 표시됩니다.  
  
 바이너리 편집기를 사용하면 다음과 같은 작업을 할 수 있습니다.  
  
-   [바이너리 편집을 위해 리소스 열기](../mfc/opening-a-resource-for-binary-editing.md)  
  
-   [이진 데이터 편집](../mfc/editing-binary-data.md)  
  
-   [이진 데이터 찾기](../mfc/finding-binary-data.md)  
  
-   [새 사용자 지정 또는 데이터 리소스 만들기](../mfc/creating-a-new-custom-or-data-resource.md)  
  
## 관리되는 리소스  
 관리되는 프로젝트에서 리소스 파일에 대해 작업하는 데 [이미지 편집기](../mfc/image-editor-for-icons.md) 및 바이너리 편집기를 사용할 수 있습니다. 편집할 관리되는 리소스는 연결된 리소스여야 합니다. Visual Studio 리소스 편집기에서는 포함된 리소스를 편집할 수 없습니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 *.NET Framework 개발자 가이드*에서 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
### 요구 사항  
 없음  
  
## 참고 항목  
 [Resource Editors](../mfc/resource-editors.md)