---
title: "마법사의 메커니즘 검사 | Microsoft Docs"
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
  - "사용자 지정 마법사, 마법사 프로젝트"
ms.assetid: 79917075-a843-40f6-abf8-64d98e5f6bdc
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# 마법사의 메커니즘 검사
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

마법사 프로젝트를 컴파일하지 않고도 사용자가 바로 마법사를 시작하도록 할 수 있습니다.  필요한 요소를 만들고 나면 VSDIR은 마법사 아이콘을 표시하도록 `New Project` 대화 상자에 지시하고 바로 가기 메뉴에 마법사 이름을 표시하도록 `Add New Item` 대화 상자에 지시합니다.  사용자는 아이콘과 메뉴를 선택하여 바로 마법사를 실행할 수 있습니다.  
  
 사용자가 마법사를 시작하면 환경 셸에서는 마법사 엔진을 공동으로 만들고 <xref:EnvDTE.IDTWizard>에 대한 쿼리를 실행합니다.  그런 다음에 <xref:EnvDTE.IDTWizard.Execute%2A>를 호출하여 마법사를 시작합니다.  
  
> [!NOTE]
>  마법사에 인터페이스가 없으면 제공된 기본값을 사용하여 프로젝트가 만들어지고 .vsz 파일에 있는 노드 구조를 사용하여 솔루션 탐색기에 표시됩니다.  지금부터는 마법사에 UI가 있는 경우에 대하여 설명합니다.  
  
 마법사에 UI가 있으면 사용자는 마법사의 HTML 기반 UI에 있는 각 컨트롤의 기본값을 그대로 사용하거나 변경합니다.  사용자가 마법사의 페이지를 이동하면서 설정을 변경하는 경우, <xref:Microsoft.VisualStudio.VsWizard.VCWizCtlClass.Navigate%2A>, <xref:Microsoft.VisualStudio.VsWizard.VCWizCtlClass.Next%2A> 등의 함수가 HTML의 Script 섹션에서 호출됩니다.  
  
 사용자가 마법사에서 다른 옵션을 선택하면 마법사 컨트롤의 기호 테이블에 선택한 내용이 캡처됩니다.  기호 테이블에서는 마법사의 HTML 페이지에 있는 컨트롤의 ID를 일치시켜 사용자 선택과 기호 테이블 사이의 일대일 대응 관계를 유지합니다.  
  
 사용자가 마법사 UI에서 **마침**을 클릭하면 HTML 스크립트에서 JScript 함수 **OnFinish**가 호출됩니다.  
  
> [!NOTE]
>  Default.js에서 **OnFinish**를 사용자 지정하여 원하는 추가 작업을 수행할 수 있습니다.  
  
 그러면 마법사 엔진은 사용자 선택을 기반으로 템플릿 파일을 구문 분석하고 렌더링하면서 검색합니다.  렌더링된 파일은 프로젝트 디렉터리에 복사되고 이 파일이 프로젝트에 추가됩니다.  새로 만든 프로젝트가 Visual Studio 환경에 로드되고 프로젝트의 노드와 파일은 솔루션 탐색기에 표시됩니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.VsWizard.VCWizCtl>   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인 단계](../ide/steps-to-designing-a-wizard.md)   
 [마법사 사용자 지정](../ide/customizing-your-wizard.md)