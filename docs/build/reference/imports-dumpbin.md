---
title: "/IMPORTS(DUMPBIN) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/imports"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/IMPORTS dumpbin 옵션"
  - "IMPORTS dumpbin 옵션"
  - "-IMPORTS dumpbin 옵션"
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /IMPORTS(DUMPBIN)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/IMPORTS[:file]  
```  
  
 이 옵션은 실행 파일 또는 DLL로 가져온 DLL\(정적 링크 또는 [지연 로드된](../../build/reference/linker-support-for-delay-loaded-dlls.md) DLL 모두\)의 목록과 이러한 각 DLL에서의 모든 개별 가져오기 목록을 표시합니다.  
  
 `file` 사양 옵션을 사용하면 해당 DLL의 가져오기만 표시하도록 지정할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
dumpbin /IMPORTS:msvcrt.dll  
```  
  
## 설명  
 이 옵션으로 표시된 출력은 [\/EXPORTS](../../build/reference/dash-exports.md) 출력과 유사합니다.  
  
 [\/HEADERS](../../build/reference/headers.md) DUMPBIN 옵션은 [\/GL](../../build/reference/gl-whole-program-optimization.md) 컴파일러 옵션으로 만든 파일에만 사용할 수 있습니다.  
  
## 참고 항목  
 [DUMPBIN 옵션](../../build/reference/dumpbin-options.md)