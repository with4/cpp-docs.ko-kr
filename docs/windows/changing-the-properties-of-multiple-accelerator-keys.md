---
title: "Changing the Properties of Multiple Accelerator Keys | Microsoft Docs"
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
  - "keyboard shortcuts [C++], property changing"
  - "accelerator tables [C++], changing properties"
ms.assetid: b55c9bd6-b430-48bb-b942-0e6f21d7abf9
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Changing the Properties of Multiple Accelerator Keys
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### 여러 액셀러레이터 키 속성을 변경하려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md)에서 아이콘을 두 번 클릭하여 액셀러레이터 키 테이블을 엽니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 없으면 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하십시오.  
  
2.  **Ctrl** 키를 누른 채로 변경할 액셀러레이터 키를 모두 클릭하여 선택합니다.  
  
3.  [속성 창](../Topic/Properties%20Window.md)으로 가서 선택한 모든 액셀러레이터 키가 공유할 값을 입력합니다.  
  
    > [!NOTE]
    >  각 한정자 값은 속성 창에 부울 속성으로 표시됩니다.  속성 창에서 [한정자](../windows/accelerator-modifier-property.md) 값을 변경하면 액셀러레이터 키 테이블에서 새 한정자는 기존 한정자에 추가된 것으로 처리됩니다.  따라서 한정자 값을 설정하려면 모든 액셀러레이터 키가 동일한 한정자 설정을 공유하도록 설정해야 합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 **요구 사항**  
  
 Win32  
  
## 참고 항목  
 [Editing Accelerator Tables](../windows/editing-accelerator-tables.md)   
 [Accelerator Editor](../mfc/accelerator-editor.md)