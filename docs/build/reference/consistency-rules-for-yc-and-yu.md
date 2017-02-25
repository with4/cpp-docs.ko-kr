---
title: "/Yc 및 /Yu에 대한 일관성 규칙 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/yc"
  - "/yu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Yc 컴파일러 옵션[C++]"
  - "/Yu 컴파일러 옵션[C++]"
  - "Yc 컴파일러 옵션[C++]"
  - "-Yc 컴파일러 옵션[C++]"
  - "Yu 컴파일러 옵션[C++]"
  - "-Yu 컴파일러 옵션[C++]"
ms.assetid: 9dfb0e32-ec9b-4a36-9355-27a0e5fba512
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /Yc 및 /Yu에 대한 일관성 규칙
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/Yc 또는 \/Yu를 사용하여 만든 미리 컴파일된 헤더를 사용하면 컴파일러는 해당 .pch 파일을 만들 때의 컴파일 환경과 현재 컴파일 환경을 비교합니다.  현재 컴파일에 대한 환경은 이전 환경과 일치하도록\(일치하는 컴파일러 옵션, pragma 등을 사용\) 지정해야 합니다.  불일치가 발견되는 경우 컴파일러는 경고를 표시하고 가능한 경우 해당 불일치 내용을 확인합니다.  이러한 경고는 반드시 해당 .pch 파일에 문제가 있음을 나타내는 것이 아니라 충돌 가능성에 대한 단순한 경고일 뿐입니다.  다음 단원에서는 미리 컴파일된 헤더의 일관성 요구 사항에 대해 설명합니다.  
  
## 컴파일러 옵션 일관성  
 다음 표에는 미리 컴파일된 헤더 사용 시 불일치 경고를 발생시킬 수 있는 컴파일러 옵션이 나열되어 있습니다.  
  
|옵션|Name|규칙|  
|--------|----------|--------|  
|\/D|상수 및 매크로 정의|미리 컴파일된 헤더를 만든 컴파일과 현재 컴파일 간에 동일해야 합니다.  정의된 상수의 상태는 확인되지 않지만 파일이 변경된 상수의 값에 따라 달라지는 경우에는 예측하지 못한 결과가 발생할 수 있습니다.|  
|\/E 또는 \/EP|전처리기 출력을 표준 출력에 복사|\/E 또는 \/EP 옵션을 사용하면 미리 컴파일된 헤더가 작동하지 않습니다.|  
|\/Fr 또는 \/FR|Microsoft 소스 브라우저 정보 생성|\/Fr 및 \/FR 옵션을 \/Yu 옵션과 함께 사용하려면 미리 컴파일된 헤더를 만들었을 때에도 이 옵션들을 적용했어야 합니다.  미리 컴파일된 헤더를 사용하는 후속 컴파일도 소스 브라우저 정보를 생성합니다.  브라우저 정보는 하나의 .sbr 파일에 포함되고 CodeView 정보와 동일한 방식으로 다른 파일에 의해 참조됩니다.  소스 브라우저 정보의 배치는 재정의할 수 없습니다.|  
|\/GA, \/GD, \/GE, \/Gw 또는 \/GW|Windows 프로토콜 옵션|미리 컴파일된 헤더를 만든 컴파일과 현재 컴파일 간에 동일해야 합니다.  이 옵션이 서로 다른 경우에는 경고 메시지가 나타납니다.|  
|\/Zi|전체 디버깅 정보 생성|미리 컴파일된 헤더를 만들 때 이 옵션을 적용한 경우, 이 미리 컴파일된 헤더를 사용하는 후속 컴파일은 해당 디버깅 정보를 사용할 수 있습니다.  미리 컴파일된 헤더를 만들 때 \/Zi를 적용하지 않은 경우, 이 미리 컴파일된 헤더와 \/Zi 옵션을 사용하는 후속 컴파일에서는 경고가 발생됩니다.  디버깅 정보는 현재 개체 파일에 포함되며, 디버거는 미리 컴파일된 헤더에 정의된 지역 기호를 사용할 수 없습니다.|  
  
> [!NOTE]
>  미리 컴파일된 헤더 기능은 C 및 C\+\+ 소스 파일을 사용하는 파일만을 위한 것입니다.  
  
## 포함 경로 일관성  
 \/Yc를 사용하여 만든 미리 컴파일된 헤더에는 해당 .pch 파일을 만들 때 적용한 포함 경로에 대한 정보가 들어 있지 않습니다.  사용자가 .pch 파일을 사용할 때 컴파일러는 항상 현재 컴파일에서 지정된 포함 경로를 사용합니다.  
  
## 소스 파일 일관성  
 미리 컴파일된 헤더를 사용할 때 컴파일러는 hdrstop pragma보다 앞에 있는 모든 전처리기 지시문\(pragma 포함\)을 무시합니다.  이러한 전처리기 지시문에 의해 지정되는 컴파일은 미리 컴파일된 헤더 파일을 만드는 데 사용된 컴파일과 동일해야 합니다.  
  
## pragma 일관성  
 미리 컴파일된 헤더의 컴파일 도중 처리된 pragma는 대개 이후에 이 미리 컴파일된 헤더를 사용하는 파일에 영향을 줍니다.  다음 pragma는 .pch 파일 내의 코드에만 영향을 주며 이후에 해당 .pch 파일을 사용하는 코드에는 영향을 주지 않습니다.  
  
||||  
|-|-|-|  
|주석|page|subtitle|  
|Linesize|pagesize|제목|  
|메시지|skip||  
  
 다음 pragma는 미리 컴파일된 헤더의 일부로 유지되며 이 미리 컴파일된 헤더를 사용하는 나머지 컴파일에 영향을 줍니다.  
  
||||  
|-|-|-|  
|alloc\_text|function|optimize|  
|auto\_inline|inline\_depth|Pack|  
|check\_pointer|inline\_recursion|same\_seg|  
|check\_stack|intrinsic|warning|  
|code\_seg|\+loop\_opt||  
|data\_seg|native\_caller||  
  
## 참고 항목  
 [미리 컴파일된 헤더의 일관성 규칙](../../build/reference/precompiled-header-consistency-rules.md)   
 [\/Yc\(미리 컴파일된 헤더 파일 만들기\)](../../build/reference/yc-create-precompiled-header-file.md)   
 [\/Yu\(미리 컴파일된 헤더 파일 사용\)](../../build/reference/yu-use-precompiled-header-file.md)