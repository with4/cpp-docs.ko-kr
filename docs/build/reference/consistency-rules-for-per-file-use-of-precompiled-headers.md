---
title: "미리 컴파일된 헤더의 파일별 사용에 대한 일관성 규칙 | Microsoft Docs"
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
  - ".pch 파일, 일관성 규칙"
  - "PCH 파일, 일관성 규칙"
  - "미리 컴파일된 헤더 파일, 일관성 규칙"
ms.assetid: afd49365-48bc-41f4-b700-fe8297b944a1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 미리 컴파일된 헤더의 파일별 사용에 대한 일관성 규칙
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러 옵션 [\/Yu](../../build/reference/yu-use-precompiled-header-file.md)를 사용하면 사용할 미리 컴파일된 헤더\(PCH\) 파일을 지정할 수 있습니다.  
  
 PCH 사용 시, 컴파일러는 사용자가 달리 지정하지 않은 경우 PCH를 만들 때 적용된 것과 동일한 컴파일 환경\(일치하는 컴파일러 옵션, pragma 등을 사용\)을 가정합니다.  불일치가 발견되는 경우 컴파일러는 경고를 표시하고 가능한 경우 해당 불일치 내용을 확인합니다.  이러한 경고는 반드시 해당 PCH에 문제가 있음을 나타내는 것이 아니라 충돌 가능성에 대한 단순한 경고일 뿐입니다.  PCH에 대한 일관성 요구 사항은 다음 단원에서 자세히 설명합니다.  
  
## 컴파일러 옵션 일관성  
 다음의 컴파일러 옵션은 PCH 사용 시 불일치 경고를 발생시킬 수 있습니다.  
  
-   전처리기\(\/D\) 옵션을 사용하여 만들어진 매크로는 해당 PCH를 만든 컴파일과 현재 컴파일 간에 동일해야 합니다.  정의된 상수의 상태는 확인되지 않지만 이 상수가 변경될 경우에는 예측하지 못한 결과가 발생할 수 있습니다.  
  
-   PCH는 \/E 및 \/EP 옵션과 함께 작동하지 않습니다.  
  
-   \/FR\(찾아보기 정보 생성\) 옵션 또는 \/Fr\(지역 변수 제외\) 옵션 중 하나를 사용하여 PCH를 만들어야만 해당 PCH를 사용하는 후속 컴파일에서 이 옵션들을 사용할 수 있습니다.  
  
## C 7.0 호환\(\/Z7\)  
 PCH를 만들 때 이 옵션이 적용된 경우, 이PCH를 사용하는 후속 컴파일에서 해당 디버깅 정보를 사용할 수 있습니다.  
  
 PCH를 만들 때 C 7.0 호환\(\/Z7\) 옵션이 적용되지 않은 경우에는 해당 PCH와 \/Z7을 사용하는 후속 컴파일에서 경고가 발생됩니다.  디버깅 정보는 현재의 .obj 파일에 포함되며, 디버거는 해당 PCH에 정의된 지역 기호를 사용할 수 없습니다.  
  
## 포함 경로 일관성  
 PCH에는 해당 PCH가 만들어질 때 적용된 포함 경로에 대한 정보가 들어 있지 않습니다.  사용자가 .pch 파일을 사용할 때 컴파일러는 항상 현재 컴파일에서 지정된 포함 경로를 사용합니다.  
  
## 소스 파일 일관성  
 \/Yu\(미리 컴파일된 헤더 파일 사용\) 옵션을 지정하면 컴파일러는 미리 컴파일될 소스 코드에 나타나는 모든 전처리기 지시문\(pragma 포함\)을 무시합니다.  이러한 전처리기 지시문에 의해 지정되는 컴파일은 \/Yc\(미리 컴파일된 헤더 파일 만들기\) 옵션에 사용되는 컴파일과 동일해야 합니다.  
  
## pragma 일관성  
 PCH를 만드는 도중 처리되는 pragma는 대개 해당 PCH가 후속으로 사용되는 파일에 영향을 줍니다.  그러나 주석 및 메시지 pragma는 나머지 컴파일에 영향을 주지 않습니다.  
  
 다음 pragma는 PCH의 일부로 유지되며 해당 PCH를 사용하는 나머지 컴파일에 영향을 줍니다.  
  
||||  
|-|-|-|  
|alloc\_text|include\_alias|pack|  
|auto\_inline|init\_seg|pointers\_to\_members|  
|check\_stack|inline\_depth|setlocale|  
|code\_seg|inline\_recursion|vtordisp|  
|data\_seg|intrinsic|warning|  
|function|optimize||  
  
## 참고 항목  
 [미리 컴파일된 헤더의 일관성 규칙](../../build/reference/precompiled-header-consistency-rules.md)   
 [\/Yu\(미리 컴파일된 헤더 파일 사용\)](../../build/reference/yu-use-precompiled-header-file.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)