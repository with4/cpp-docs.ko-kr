---
title: "Files Affected by Resource Editing | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resource editing"
  - "resources [Visual Studio], editing"
ms.assetid: d0820df1-ba84-40ac-bce9-29ea5ee7e3f8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Files Affected by Resource Editing
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio 환경은 리소스 편집 세션 중 다음 표에 표시된 파일에서 작동합니다.  
  
|파일 이름|설명|  
|-----------|--------|  
|Resource.h|개발 환경에서 생성된 헤더 파일로, 기호 정의를 포함합니다.|  
|Filename.aps|현재 리소스 스크립트 파일의 이진 버전으로, 빠른 로드를 위해 사용됩니다.<br /><br /> 리소스 편집기에서 .rc 또는 resource.h 파일을 직접 읽지 않습니다.  리소스 컴파일러는 리소스 편집기에서 사용되는 이러한 파일을 .aps 파일로 컴파일합니다.  이 파일은 컴파일 단계이며 기호화된 데이터만 저장합니다.  일반적인 컴파일 프로세스에서처럼 기호화되지 않은 정보\(예: 주석\)는 컴파일 프로세스 중에 삭제됩니다.  .aps 파일이 .rc 파일과 동기화되지 않을 때마다 .rc 파일이 다시 생성됩니다. 예를 들어 저장하면 리소스 편집기에서 .rc 파일 및 resource.h 파일을 덮어씁니다.  리소스 자체의 모든 변경 내용은 .rc 파일에 통합된 상태로 유지되지만 주석은 .rc 파일을 덮어쓰면 항상 손실됩니다.  주석을 유지하는 방법에 대한 자세한 내용은 [컴파일 타임에 리소스 포함](../windows/how-to-include-resources-at-compile-time.md)을 참조하세요.|  
|.rc|현재 프로젝트의 리소스에 대한 스크립트가 포함된 리소스 스크립트 파일입니다.  저장할 때마다 .aps 파일이 이 파일을 덮어씁니다.|  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
## 요구 사항  
 Win32  
  
## 참고 항목  
 [Resource Files](../mfc/resource-files-visual-studio.md)