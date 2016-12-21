---
title: "컴파일러 경고 (수준 4) C4234 | Microsoft Docs"
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
  - "C4234"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4234"
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4234
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장이 사용됨 : 'keyword' 키워드는 나중에 사용할 수 있도록 예약되었습니다.  
  
 사용한 키워드를 컴파일러에서 아직 구현하지 않습니다.  
  
 이 경고는 자동으로 오류가 됩니다.  이 동작을 수정하려면 [\#pragma warning](../../preprocessor/warning.md)을 사용하십시오.  예를 들어, C4234를 수준 4의 경고로 만들려면 다음 코드  
  
```  
#pragma warning(2:4234)  
```  
  
 를 소스 코드 파일에 작성합니다.