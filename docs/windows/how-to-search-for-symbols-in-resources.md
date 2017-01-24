---
title: "How to: Search for Symbols in Resources | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "symbols, finding"
  - "resources [Visual Studio], searching for symbols"
ms.assetid: 6efef8e8-d0d4-4c49-b895-314974e7791a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Search for Symbols in Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### 리소스에서 기호를 찾으려면  
  
1.  **편집** 메뉴에서 **기호 찾기**를 선택합니다.  
  
2.  [기호 찾기](http://msdn.microsoft.com/ko-kr/63e93d9c-784f-418d-a76a-723da5ff5d96) 대화 상자의 **찾을 내용** 상자에 있는 드롭다운 목록에서 이전 검색 문자열을 선택하거나 찾으려는 액셀러레이터 키\(예: ID\_ACCEL1\)를 입력합니다.  
  
    > [!TIP]
    >  검색에 [정규식](../Topic/Using%20Regular%20Expressions%20in%20Visual%20Studio.md)을 사용하려면 **기호 찾기** 명령 대신 **편집** 메뉴에 있는 [파일에서 찾기](../Topic/Find%20Command.md) 명령을 사용해야 합니다.  정규식을 사용하도록 설정하려면 [찾기](http://msdn.microsoft.com/ko-kr/dad03582-4931-4893-83ba-84b37f5b1600) 대화 상자에서 **사용: 정규식** 확인란을 선택해야 합니다.  그런 다음, **찾을 내용** 상자 오른쪽에 있는 오른쪽 화살표 단추를 클릭하여 정규 검색 식의 목록을 표시합니다.  목록에서 식을 선택하면 이 식이 **찾을 내용** 상자의 검색 텍스트로 대체됩니다.  
  
3.  **찾기** 옵션 중에서 선택합니다.  
  
4.  **다음 찾기**를 클릭합니다.  
  
    > [!NOTE]
    >  문자열, 액셀러레이터 또는 이진 리소스에서 기호를 검색할 수 없습니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
 **요구 사항**  
  
 Win32  
  
## 참고 항목  
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)