---
title: "링커 도구 오류 LNK2011 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2011"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2011"
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK2011
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

미리 컴파일된 개체가 링크되지 않았습니다. 이미지가 실행되지 않을 수 있습니다.  
  
 미리 컴파일된 헤더를 사용하는 경우 LINK는 미리 컴파일된 헤더를 사용하여 만든 개체 파일을 모두 링크하도록 요청합니다.  다른 소스 파일에서 사용할 미리 컴파일된 헤더를 생성하는 데 사용되는 소스 파일을 포함하는 경우에는 만든 개체 파일을 미리 컴파일된 헤더와 함께 포함시켜야 합니다.  
  
 예를 들어, STUB.cpp라는 파일을 컴파일하여 다른 소스 파일에서 사용할 미리 컴파일된 헤더를 만드는 경우에는 STUB.obj를 링크해야 합니다. 그렇지 않으면 이 오류가 발생합니다.  다음 명령줄에서 첫째 줄은 둘째 및 셋째 줄의 PROG1.cpp와 PROG2.cpp에 사용되는, 미리 컴파일된 헤더인 COMMON.pch를 만드는 데 사용됩니다.  STUB.cpp 파일은 `#include` 줄\(PROG1.cpp 및 PROG2.cpp에서와 같은 `#include` 줄\)만 포함하며 미리 컴파일된 헤더를 생성하는 데에만 사용됩니다.  마지막 줄에서 STUB.obj를 링크시켜야 LNK2011을 방지할 수 있습니다.  
  
```  
cl /c /Yccommon.h stub.cpp  
cl /c /Yucommon.h prog1.cpp  
cl /c /Yucommon.h prog2.cpp  
link /out:prog.exe stub.obj prog1.obj prog2.obj  
```