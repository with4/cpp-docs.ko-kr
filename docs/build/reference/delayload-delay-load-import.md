---
title: "/DELAYLOAD(가져오기 로드 지연) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/delayload"
  - "VC.Project.VCLinkerTool.DelayLoadDLLS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAYLOAD 링커 옵션"
  - "지연 DLL 로드, /DELAYLOAD 옵션"
  - "DELAYLOAD 링커 옵션"
  - "-DELAYLOAD 링커 옵션"
ms.assetid: 39ea0f1e-5c01-450f-9c75-2d9761ff9b28
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /DELAYLOAD(가져오기 로드 지연)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DELAYLOAD:dllname  
  
```  
  
## 매개 변수  
 `dllname`  
 로드를 지연할 DLL의 이름입니다.  
  
## 설명  
 \/DELAYLOAD 옵션을 사용하면 `dllname`으로 지정된 DLL에서 프로그램이 함수를 처음 호출할 때만 해당 DLL이 로드됩니다.  자세한 내용은 [링커의 지연 로드된 DLL 지원](../../build/reference/linker-support-for-delay-loaded-dlls.md)을 참조하십시오.  이 옵션을 필요한 횟수만큼 사용하여 선택한 수만큼의 DLL을 지정할 수 있습니다.  프로그램을 링크할 때 Delayimp.lib를 사용해야 하거나, 고유한 지연 로드 도우미 함수를 구현할 수 있습니다.  
  
 [\/DELAY](../../build/reference/delay-delay-load-import-settings.md) 옵션은 지연 로드되는 각 DLL에 대해 바인딩 및 로드 옵션을 지정합니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  **링커** 폴더에서 **입력** 속성 페이지를 선택합니다.  
  
3.  **지연 로드된 DLL** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>을 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)