---
title: "상황에 맞는 도움말 표시 | Microsoft Docs"
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
  - "상황에 맞는 도움말"
  - "상황에 맞는 도움말, 사용자 지정 마법사"
  - "사용자 지정 마법사, 도움말 구현"
ms.assetid: c6c4d961-29d3-4d16-9f39-b12545aba540
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 상황에 맞는 도움말 표시
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[사용자 지정 마법사](../ide/application-settings-custom-wizard.md)를 사용하여 마법사를 만들면 마법사에 **도움말** 단추가 추가됩니다.  
  
 마법사에 **도움말** 단추를 추가할 수 있도록 프로젝트의 각 .htm 파일에는 다음 코드가 포함되어 있습니다.  
  
```  
<BUTTON CLASS="BUTTONS" ID="HelpBtn" ACCESSKEY="H"  
 onClick="window.external.OnHelp('vc.appwiz.custom.overview');">  
```  
  
 <xref:Microsoft.VisualStudio.VsWizard.VCWizCtlClass.OnHelp%2A>는 마법사의 해당 페이지와 연결된 HTML 도움말 파일의 키워드를 지정합니다.  해당 페이지와 연결된 HTML 도움말 파일을 만드는 방법은 [HTML Help Start Page](vsconhh1start)를 참조하십시오.  이 마법사 페이지에 사용자가 직접 만든 도움말을 제공하려면 `'vc.appwiz.custom.overview'` 문자열을 해당 페이지의 HTML 도움말 항목을 나타내는 키워드로 바꿔야 합니다.  
  
 **참고** 컴파일된 MSDN 도움말에 이 .htm 파일을 통합할 수는 없습니다.  
  
## 참고 항목  
 [마법사용으로 만들어진 파일](../ide/files-created-for-your-wizard.md)   
 [사용자 지정 마법사](../ide/custom-wizard.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)