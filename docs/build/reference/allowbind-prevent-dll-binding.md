---
title: "/ALLOWBIND(DLL 바인딩 방지) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.PreventDLLBinding"
  - "/allowbind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ALLOWBIND 링커 옵션"
  - "ALLOWBIND 링커 옵션"
  - "-ALLOWBIND 링커 옵션"
  - "DLL 바인딩"
  - "DLL[C++], 바인딩 방지"
  - "DLL 바인딩 방지"
ms.assetid: 30e37e24-12e4-407e-988a-39d357403598
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /ALLOWBIND(DLL 바인딩 방지)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ALLOWBIND[:NO]  
```  
  
## 설명  
 \/ALLOWBIND:NO는 DLL의 헤더에서 이미지 바인딩을 허용하지 않는 Bind.exe를 가리키는 비트를 설정합니다.  바인딩이 서명을 무효화하므로 디지털 서명된 경우 DLL을 바인딩하지 않으려고 할 수 있습니다.  
  
 EDITBIN 유틸리티의 [\/ALLOWBIND](../../build/reference/allowbind.md) 옵션을 사용하여 \/ALLOWBIND 기능의 기존 DLL을 편집할 수 있습니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  **구성 속성**, **링커**를 확장하고 **명령줄**을 선택합니다.  
  
3.  **추가 옵션**에 `/ALLOWBIND:NO`를 입력합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)   
 [BindImage 함수](http://msdn.microsoft.com/library/windows/desktop/ms679278.aspx)   
 [BindImageEx 함수](http://msdn.microsoft.com/library/windows/desktop/ms679279.aspx)