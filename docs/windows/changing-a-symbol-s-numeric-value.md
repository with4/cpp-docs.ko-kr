---
title: "Changing a Symbol&#39;s Numeric Value | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.symbol.changing.value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "numeric values"
  - "symbols, numeric values"
  - "numeric values, changing symbols"
ms.assetid: 468e903b-9c07-4251-ae09-3b6cb754cc2b
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Changing a Symbol&#39;s Numeric Value
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

단일 리소스와 연결된 기호의 경우 [속성 창](../Topic/Properties%20Window.md)을 사용하여 기호 값을 변경할 수 있습니다.  [리소스 기호 대화 상자](../windows/resource-symbols-dialog-box.md)를 사용하여 현재 리소스에 할당되지 않은 기호의 값을 변경할 수 있습니다.  자세한 내용은 [할당되지 않은 기호 변경](../windows/changing-unassigned-symbols.md)을 참조하세요.  
  
### 단일 리소스 또는 개체에 할당된 기호 값을 변경하려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md)에서 리소스를 선택합니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  **속성** 창에서 다음과 같이 기호 이름을 입력한 다음 등호 기호와 정수를 **ID** 상자에 입력합니다.  
  
    ```  
    IDC_EDITNAME=5100  
    ```  
  
 새 값은 다음에 프로젝트를 저장할 때 기호 헤더 파일에 저장됩니다.  기호 이름만 ID 상자에 표시되고, 유효성 검사가 완료된 후에는 등호 기호와 값이 표시되지 않습니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
 요구 사항  
  
 Win32  
  
## 참고 항목  
 [Symbol Value Restrictions](../windows/symbol-value-restrictions.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)