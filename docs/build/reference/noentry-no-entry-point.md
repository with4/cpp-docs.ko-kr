---
title: "/NOENTRY(진입점 없음) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.ResourceOnlyDLL"
  - "/noentry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NOENTRY 링커 옵션[C++]"
  - "DLL[C++], 만들기"
  - "진입점[C++], 링커 지정"
  - "NOENTRY 링커 옵션"
  - "-NOENTRY 링커 옵션"
  - "리소스 전용 DLL[C++], 만들기"
ms.assetid: 0214dd41-35ad-43ab-b892-e636e038621a
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /NOENTRY(진입점 없음)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/NOENTRY  
```  
  
## 설명  
 실행 코드가 없는 리소스 전용 DLL을 만들려면 \/NOENTRY 옵션을 지정해야 합니다.  자세한 내용은 [리소스 전용 DLL 만들기](../../build/creating-a-resource-only-dll.md)을 참조하십시오.  
  
 이 옵션을 사용하면 LINK가 `_main`에 대한 참조를 DLL로 링크하는 것을 방지할 수 있습니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 선택합니다.  
  
3.  **고급** 속성 페이지를 클릭합니다.  
  
4.  **진입점 없음** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL%2A>을 참조하십시오.  
  
## 참고 항목  
 [리소스 전용 DLL 만들기](../../build/creating-a-resource-only-dll.md)   
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)