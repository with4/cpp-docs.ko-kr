---
title: "Changing a Symbol or Symbol Name (ID) | Microsoft Docs"
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
  - "vc.editors.symbol.changing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "symbol names"
  - "symbols, names"
ms.assetid: 26541832-8dba-4177-b642-e08f94502ea7
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Changing a Symbol or Symbol Name (ID)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

새 리소스 또는 리소스 개체를 만들 때 개발 환경에서 IDD\_DIALOG1과 같은 기본 기호 이름을 할당합니다.  [속성 창](../Topic/Properties%20Window.md)을 사용하여 기본 기호 이름을 변경하거나 이미 리소스와 연결된 기호의 이름을 변경할 수 있습니다.  
  
### 리소스의 기호 이름을 변경하려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md)에서 리소스를 선택합니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  **속성** 창에서 새 기호 이름을 입력하거나 **ID** 상자의 기존 기호 목록에서 선택합니다.  
  
     새 기호 이름을 입력하는 경우 값이 자동으로 할당됩니다.  
  
 [리소스 기호 대화 상자](../windows/resource-symbols-dialog-box.md)를 사용하여 현재 리소스에 할당되지 않은 기호의 이름을 변경할 수 있습니다.  자세한 내용은 [할당되지 않은 기호 변경](../windows/changing-unassigned-symbols.md)을 참조하세요.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
 요구 사항  
  
 Win32  
  
## 참고 항목  
 [Symbol Name Restrictions](../windows/symbol-name-restrictions.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)