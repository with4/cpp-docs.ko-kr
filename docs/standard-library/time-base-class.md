---
title: "time_base 클래스 | Microsoft Docs"
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
  - "std.time_base"
  - "std::time_base"
  - "time_base"
  - "locale/std::time_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "time_base 클래스"
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# time_base 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The class serves as a base class for facets of template class time\_get, defining just the enumerated type **dateorder** and several constants of this type.  
  
## 구문  
  
```  
class time_base : public locale::facet {  
public:  
    enum dateorder {no_order, dmy, mdy, ymd, ydm};  
    time_base(  
        size_t _Refs = 0  
    )  
    ~time_base();  
};  
```  
  
## 설명  
 Each constant characterizes a different way to order the components of a date.  The constants are:  
  
-   **no\_order** specifies no particular order.  
  
-   **dmy** specifies the order day, month, then year, as in 2 December 1979.  
  
-   **mdy** specifies the order month, day, then year, as in December 2, 1979.  
  
-   **ymd** specifies the order year, month, then day, as in 1979\/12\/2.  
  
-   **ydm** specifies the order year, day, then month, as in 1979: 2 Dec.  
  
## 요구 사항  
 **Header:** \<locale\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)