---
title: "공용 JScript 함수를 사용하여 C++ 마법사 사용자 지정 | Microsoft Docs"
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
  - "마법사 JScript 메서드, C++ 마법사 만들기"
ms.assetid: c602978f-a2c4-462f-85c3-50b5897bec46
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 공용 JScript 함수를 사용하여 C++ 마법사 사용자 지정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[사용자 지정 마법사](../ide/creating-a-custom-wizard.md)를 사용하여 만든 마법사 프로젝트에는 Common.js가 포함됩니다.  마법사에 사용자 인터페이스를 지정하면 해당 프로젝트에는 다음과 같이 Common.js 파일을 포함하고 JScript 스크립트 언어를 지정하는 HTML 페이지가 포함됩니다.  
  
```  
<SCRIPT ID="INCLUDE_COMMON" LANGUAGE ="JSCRIPT"></SCRIPT>  
```  
  
 이 마법사에서는 Default.js라는 고유한 파일도 만듭니다.  Default.js에서 사용자 고유의 JScript 함수를 사용자 지정할 수 있습니다.  자세한 내용은 [JScript 파일](../ide/jscript-file.md)을 참조하십시오.  
  
 Common.js에는 각 마법사의 HTML 페이지와 Default.js에서 호출할 수 있는 함수가 포함되어 있습니다.  다른 마법사에서도 같은 함수를 사용하려면 이를 Common.js에 포함합니다.  
  
## 참고 항목  
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)