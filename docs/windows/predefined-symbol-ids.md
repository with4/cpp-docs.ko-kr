---
title: "Predefined Symbol IDs | Microsoft Docs"
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
  - "symbols, predefined IDs"
  - "predefined symbol IDs"
ms.assetid: 91a5d610-1a04-47e8-b8a4-63ad650a90df
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Predefined Symbol IDs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

새 프로젝트를 시작하면 프로젝트 형식에 따라 일부 기호 ID가 바로 사용할 수 있도록 미리 정의되어 있습니다.  이러한 기호 ID는 다양한 라이브러리와 MFC 등의 프로젝트 형식을 지원합니다.  이 ID는 응용 프로그램에 대체로 포함되는 일반 작업 또는 마우스나 프린터와 같은 하드웨어 항목의 작업 등을 나타냅니다.  
  
 이러한 기호 ID는 리소스 작업을 할 때 중요해집니다.  액셀러레이터 키 테이블을 편집할 때 사용할 수 있으며, 일부는 이미 가상 키와 연결되어 있습니다.  [속성 창](../Topic/Properties%20Window.md)을 통해 사용할 수도 있습니다.  미리 정의된 기호 ID 중 하나를 새 리소스에 지정하거나 ID에 액셀러레이터 키를 할당할 수 있습니다. 그러면 해당 기호 ID와 관련된 기능이 해당 키 조합과 자동 연결됩니다.  
  
 다음 라이브러리에는 프로젝트의 일부로 나타나는 미리 정의된 기호가 있습니다.  
  
-   [미리 정의된 MFC 기호](../windows/mfc-predefined-symbols.md)  
  
-   [미리 정의된 ATL 기호](../windows/atl-predefined-symbols.md)  
  
-   [미리 정의된 Win32 기호](../windows/win32-predefined-symbols.md)  
  
    > [!NOTE]
    >  미리 정의된 기호는 항상 읽기 전용입니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
## 요구 사항  
 Win32, MFC 또는 ATL  
  
## 참고 항목  
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)