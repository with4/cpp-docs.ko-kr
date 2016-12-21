---
title: "/WX(링커 경고를 오류로 처리) | Microsoft Docs"
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
  - "/WX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/WX 링커 옵션"
  - "WX 링커 옵션"
  - "-WX 링커 옵션"
ms.assetid: e4ba97c7-93f7-43ae-a4bb-d866790926c9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /WX(링커 경고를 오류로 처리)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/WX[:NO]  
```  
  
## 설명  
 \/WX를 사용하면 링커에서 경고가 생성될 경우 출력 파일이 생성되지 않습니다.  
  
 이는 컴파일러의 **\/WX** 옵션과 비슷합니다. 자세한 내용은 [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won\(경고 수준\)](../../build/reference/compiler-option-warning-level.md)을 참조하십시오.  그러나 컴파일에 **\/WX**를 지정해도 링크 단계에서 **\/WX**가 적용되지는 않습니다. 각 도구에 대해 **\/WX**를 명시적으로 지정해야 합니다.  
  
 기본적으로 **\/WX**는 설정되어 있지 않습니다.  링커 경고를 오류로 취급하려면 **\/WX**를 지정합니다.  **\/WX:NO**는 **\/WX**를 지정하지 않은 것과 같습니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)