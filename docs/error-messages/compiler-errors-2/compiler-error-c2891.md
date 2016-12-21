---
title: "컴파일러 오류 C2891 | Microsoft Docs"
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
  - "C2891"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2891"
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
caps.latest.revision: 7
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2891
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'parameter' : 템플릿 매개 변수의 주소를 가져올 수 없습니다.  
  
 다음과 같은 코드를 사용하는 경우 문제가 발생할 수 있습니다.  
  
```  
template <int i> int* f() { return &i; }  
```  
  
 다음 코드를 대신 사용하십시오.  
  
```  
template <int i> int* f() { return i; }  
```