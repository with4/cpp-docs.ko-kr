---
title: "컴파일러 경고(수준 4) C4235 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4235"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4235"
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고(수준 4) C4235
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장 사용 : 이 아키텍처에서는 'keyword' 키워드를 사용할 수 없습니다.  
  
 컴파일러에서는 사용한 키워드를 지원하지 않습니다.  
  
 이 경고는 자동으로 오류가 됩니다.  이 동작을 수정하려면 [\#pragma warning](../../preprocessor/warning.md)을 사용하십시오.  예를 들어, C4235를 수준 2의 경고로 만들려면 다음 코드  
  
```  
#pragma warning(2:4235)  
```  
  
 를 소스 코드 파일에 작성합니다.