---
title: "마법사를 여러 언어로 지역화 | Microsoft Docs"
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
  - "사용자 지정 마법사, 지역화"
  - "전역화[C++], 마법사"
  - "지역화[C++], 마법사"
  - "마법사[C++], 지역화"
ms.assetid: 879885c2-fafd-44fd-8032-bf0c301f4f45
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 마법사를 여러 언어로 지역화
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio에서 지원하는 모든 언어로 마법사를 만들 수 있습니다.  기본적으로, Visual Studio를 설치할 경우 레지스트리에서 로캘을 식별하여 해당 로캘에 대한 적절한 템플릿을 제공합니다.  
  
 Visual Studio에서는 언어 ID를 사용하여 마법사에 필요한 언어 지원을 식별합니다.  기본적으로 언어 ID는 HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\7.0\\General\\UILanguage 레지스트리 항목에 십진수 값으로 설정되어 있습니다.  마법사에서 언어 항목을 찾을 수 없으면 기본적으로 영어\(1033\)로 설정됩니다.  
  
> [!NOTE]
>  십진수 언어 값 목록은 [다른 언어에 대한 마법사 지원](../ide/wizard-support-for-other-languages.md)을 참조하십시오.  
  
 언어 ID는 [HTML 파일](../ide/html-files.md) 및 [템플릿 파일](../ide/template-files.md)이 포함된 경로에 있는 .[VSZ 파일](../Topic/Configuring%20.Vsz%20Files%20to%20Start%20Wizards.md)에 사용자 지정 매개 변수로 지정됩니다.  
  
 .htm 파일을 제공하는 각 언어에 대하여 경로를 지정해야 합니다.  
  
## 예제  
 .vsz 파일에 다음과 같은 사용자 지정 매개 변수를 설정하면 영어\(1033\), 일본어\(1041\) 및 독일어\(1031\)로 작성된 HTML이 제공됩니다.  
  
```  
Param="START_PATH\HTML\1033"  
Param="START_PATH\HTML\1041"  
Param="START_PATH\HTML\1031"  
Param="START_PATH\Templates\1033"  
Param="START_PATH\Templates\1041"  
Param="START_PATH\Templates\1031"  
```  
  
 위의 사용자 지정 매개 변수를 설정하면 다음과 같은 구조로 마법사 디렉터리가 설치됩니다.  
  
```  
MyWizard1  
   HTML  
      1033  
         default.htm  
         myEnglishHTML.htm  
      1041  
         default.htm  
         myJapaneseHTML.htm  
      1031  
         default.htm  
         myGermanHTML.htm  
   Templates  
      1033  
         stdafx.h  
         stdafx.cpp  
      1041  
         stdafx.h  
         stdafx.cpp  
      1031  
         stdafx.h  
         stdafx.cpp  
   Images  
      HtmlPage1.bmp  
      HtmlPage2.jpg  
   Scripts  
      Default.js  
```  
  
## 참고 항목  
 [마법사용으로 만들어진 파일](../ide/files-created-for-your-wizard.md)   
 [사용자 지정 마법사](../ide/custom-wizard.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [마법사 .Vsz 파일의 사용자 지정 매개 변수](../ide/custom-parameters-in-the-wizard-dot-vsz-file.md)