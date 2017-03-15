---
title: "컴파일러 경고 (수준 1) C4727 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4727"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4727"
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# 컴파일러 경고 (수준 1) C4727
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

타임스탬프가 동일한 pch\_file PCH가 obj\_file\_1 및 obj\_file\_2에 있습니다.  첫 번째 PCH를 사용합니다.  
  
 C4727은 **\/Yc**를 사용하여 여러 번 컴파일하고, 컴파일러에서 동일한 .pch 타임스탬프를 사용하여 모든 .obj 파일에 표시할 수 있는 경우에 발생합니다.  
  
 이 오류를 해결하려면 **\/Yc \/c**\(pch 생성\)를 사용하여 소스 파일 하나를 컴파일하고, **\/Yu \/c**\(pch 사용\)를 사용하여 나머지 파일을 따로 컴파일한 다음 이들을 링크합니다.  
  
 따라서, 다음과 같이 했을 때 C4727 오류가 발생했다면  
  
 **cl \/clr \/GL a.cpp b.cpp c.cpp \/Ycstdafx.h**  
  
 대신 아래와 같이 합니다.  
  
 **cl \/clr \/GL a.cpp \/Ycstdafx.h \/c**  
  
 **cl \/clr \/GL b.cpp c.cpp \/Yustdafx.h \/link a.obj**  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [\/Yc\(미리 컴파일된 헤더 파일 만들기\)](../../build/reference/yc-create-precompiled-header-file.md)  
  
-   [\/Yu\(미리 컴파일된 헤더 파일 사용\)](../../build/reference/yu-use-precompiled-header-file.md)