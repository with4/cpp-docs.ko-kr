---
title: "컴파일러 경고 (수준 4) C4233 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4233"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4233"
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 4) C4233
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장이 사용됨: 'keyword' 키워드는 C\+\+에서만 지원되고 C에서는 지원되지 않습니다.  
  
 컴파일러가 C\+\+에서만 사용할 수 있는 키워드를 포함한 소스 코드를 컴파일러에서 C\+\+가 아닌 C로 컴파일했습니다.  소스 파일의 확장명이 .c이거나 [\/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)를 사용한 경우 컴파일러에서는 소스 코드를 C로 컴파일합니다.  
  
 이 경고는 자동으로 오류가 됩니다.  이 동작을 수정하려면 [\#pragma warning](../../preprocessor/warning.md)을 사용하십시오.  예를 들어, C4233를 수준 4의 경고로 만들려면 다음 코드  
  
```  
#pragma warning(2:4233)  
```  
  
 를 소스 코드 파일에 작성합니다.