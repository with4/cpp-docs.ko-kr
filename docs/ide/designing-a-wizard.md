---
title: "마법사 디자인 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "사용자 지정 마법사[C++], 프로젝트 디자인"
  - "프로젝트[C++], 사용자 지정 마법사"
  - "Visual C++ 프로젝트, 사용자 지정 마법사"
  - "마법사[C++], 사용자 지정"
ms.assetid: a7c0be7e-9297-4fed-83e3-5645c896d56b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 마법사 디자인
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+에 있는 응용 프로그램 마법사와 다른 표준화된 기능을 사용하여 프로젝트를 만들어야 할 수도 있습니다.  이 경우에는 쉽게 확장하고 사용자 지정할 수 있도록 디자인된 Visual C\+\+ 마법사 아키텍처를 사용할 수 있습니다.  [Visual C\+\+ 사용자 지정 마법사](../ide/creating-a-custom-wizard.md)를 사용하면 마법사를 만들 수 있습니다.  마법사를 만들고 나면 프로젝트에 필요한 시작 파일을 만들도록 마법사를 구성할 수 있습니다.  
  
 Visual C\+\+ 마법사는 HTML 컨트롤입니다.  Visual C\+\+ 마법사에서는 <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI.NavigateToCommandHandler%2A>, <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI.OkCancelAlert%2A> 등의 공용 서비스를 제공하는 Visual C\+\+ 마법사 엔진인 <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI>를 사용합니다.  또한 마법사에서는 VBScript 및 [JScript .NET](http://msdn.microsoft.com/ko-kr/c7e636ee-c10f-45b1-85ec-fe2daca30bf5)를 인식할 수 있도록 스크립트 엔진을 사용합니다.  
  
 마법사 아키텍처를 사용하면 마법사에서 다음과 같은 개체 모델에 직접 액세스할 수 있고 JScript 또는 HTML 파일에서 메서드, 속성 및 이벤트를 호출할 수 있습니다.  자세한 내용은 [HTML 파일](../ide/html-files.md) 및 [JScript 파일](../ide/jscript-file.md)의 예제를 참조하십시오.  
  
-   [DTE\(Developer Tools Environment\) 개체 모델](../Topic/Extending%20the%20Visual%20Studio%20Environment.md)  
  
-   [Visual C\+\+ 코드 모델](http://msdn.microsoft.com/ko-kr/dd6452c2-1054-44a1-b0eb-639a94a1216b)  
  
-   [Visual C\+\+ 프로젝트 모델](http://msdn.microsoft.com/ko-kr/06c1bbd9-4c79-4f97-ad6d-2b1dea8ecd1f)  
  
-   [Visual C\+\+ 마법사 모델](http://msdn.microsoft.com/ko-kr/159395ac-33c7-47bf-ad42-4e1435ddc758)  
  
 마법사를 디자인하는 각 요소에 대한 설명은 [마법사에 사용하도록 만들어지는 파일](../ide/files-created-for-your-wizard.md)을 참조하십시오.  
  
## 참고 항목  
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인 단계](../ide/steps-to-designing-a-wizard.md)   
 [마법사 사용자 지정](../ide/customizing-your-wizard.md)