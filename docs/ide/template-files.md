---
title: "템플릿 파일 | Microsoft Docs"
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
  - "사용자 지정 마법사, 템플릿 파일"
  - "파일[C++], 사용자 지정 마법사로 만들기"
  - "템플릿[C++], 마법사"
ms.assetid: 48fae3d8-3a53-4f62-8010-144c5ffe334e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 템플릿 파일
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

마법사를 구성하는 템플릿은 몇 가지 [간단한 지시문](../ide/template-directives.md)이 포함된 텍스트 파일 모음입니다. 사용자의 입력에 따라 이 파일이 구문 분석되고 렌더링되어 초기 프로젝트에 추가됩니다.  템플릿을 구문 분석하는 데 필요한 정보는 마법사 컨트롤의 기호 테이블에 직접 액세스하여 가져옵니다.  
  
 다음 예제는 마법사의 간단한 템플릿 파일로, 사용자가 A나 B를 선택하도록 합니다.  
  
## 예제  
  
```  
This file has been created by My Custom wizard.  
You selected:  
[!if TYPE_A]  
Type A  
[!else]  
Type B  
[!endif]  
The name of this project is [!output PROJECT_NAME].root.cpp:  
```  
  
 사용자가 Type B를 선택하면 위의 템플릿이 다음과 같이 렌더링됩니다.  
  
  **이 파일은 사용자 지정 마법사로 만들었습니다.  선택:**  
**형식 B**  
**이 프로젝트의 이름은 MyApp8입니다.**    
## Output  
  
```  
This file has been created by My Custom wizard.  
You selected:  
Type B  
The name of this project is MyApp8.  
```  
  
 **참고** 위의 구문은 Visual C\+\+ .NET에 새로 추가된 것입니다.  이전 Visual C\+\+ 버전의 구문은 Visual C\+\+ .NET에서 사용할 수 없습니다.  
  
## 참고 항목  
 [마법사용으로 만들어진 파일](../ide/files-created-for-your-wizard.md)   
 [사용자 지정 마법사](../ide/custom-wizard.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [Templates.inf 파일](../ide/templates-inf-file.md)