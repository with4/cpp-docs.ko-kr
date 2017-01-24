---
title: "duration_values 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "chrono/std::chrono::duration_values"
dev_langs: 
  - "C++"
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
caps.latest.revision: 13
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# duration_values 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 [duration](../standard-library/duration-class.md) template parameter `Rep` 의 지정된 값을 제공합니다.  
  
## 구문  
  
```  
template<class Rep>  
   struct duration_values;  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[duration\_values::max 메서드](../Topic/duration_values::max%20Method.md)|Static.  이 `Rep` 형식의 값의 상한을 지정합니다.|  
|[duration\_values::min 메서드](../Topic/duration_values::min%20Method.md)|Static.  이 `Rep` 형식의 값의 하한을 지정합니다.|  
|[duration\_values::zero 메서드](../Topic/duration_values::zero%20Method.md)|Static.  `Rep(0)`를 반환합니다.|  
  
## 요구 사항  
 **Header:** chrono  
  
 **네임 스페이스:** std::chrono  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)