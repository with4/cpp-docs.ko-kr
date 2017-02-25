---
title: "How to: Change the Language or Condition of a Resource While Copying | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.resvw.resource.changing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Language property"
  - "condition property of resource"
ms.assetid: 8f622ab0-bac2-468f-ae70-78911afc4759
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# How to: Change the Language or Condition of a Resource While Copying
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

리소스에서 복사하는 동안 언어 속성이나 조건 속성 또는 두 가지 모두를 변경할 수 있습니다.  
  
-   리소스의 언어는 말 그대로 리소스용 언어를 식별합니다.  찾고 있는 리소스를 식별하기 위해 [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042)에서 사용됩니다.  \(그러나 언어별로 리소스에 텍스트와 관련 없는 차이점이 있을 수 있습니다. 예를 들어 액셀러레이터가 일본어 자판에서만 작동하거나 비트맵이 중국어로 지역화된 빌드에서만 적절하게 작동하는 경우가 있을 수 있습니다.\)  
  
-   리소스의 조건은 리소스의 해당 특정 복사본이 사용되는 조건을 식별하는 정의된 기호입니다.  
  
 리소스의 언어와 조건은 작업 영역 창에서 리소스 이름 뒤에 오는 괄호 안에 표시됩니다.  이 예제에서는 IDD\_AboutBox라는 리소스가 언어로 핀란드 어를 사용하며 조건이 XX33입니다.  
  
```  
IDD_AboutBox (Finnish – XX33)  
```  
  
### 기존 리소스를 복사하고 해당 언어 또는 조건을 변경하려면  
  
1.  .rc 파일이나 [리소스 뷰](../windows/resource-view-window.md) 창에서 복사하려는 리소스를 마우스 오른쪽 단추로 클릭합니다.  
  
2.  바로 가기 메뉴에서 **복사본 삽입**을 선택합니다.  
  
3.  **리소스 복사본 삽입** 대화 상자에서 다음을 수행합니다.  
  
    -   **언어** 목록 상자에서 언어를 선택합니다.  
  
    -   **조건** 상자에 조건을 입력합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
 요구 사항  
  
 Win32  
  
## 참고 항목  
 [How to: Copy Resources](../windows/how-to-copy-resources.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)