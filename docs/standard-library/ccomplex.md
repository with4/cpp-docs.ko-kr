---
title: "&lt;ccomplex&gt; | Microsoft Docs"
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
  - "<ccomplex>"
dev_langs: 
  - "C++"
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
caps.latest.revision: 15
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;ccomplex&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

효율적으로 표준 C 라이브러리 헤더 \<complex.h\>를 포함하고 `std` 네임스페이스에 연결된 이름을 추가하는 STL 헤더 [\<complex\>](../standard-library/complex.md)를 포함합니다.  
  
## 구문  
  
```cpp  
  
#include <ccomplex>  
  
```  
  
## 설명  
 이 헤더를 포함하는 경우 표준 C 라이브러리 헤더의 외부 링크를 사용하여 선언한 이름이 `std` 네임스페이스에도 선언됩니다.  
  
 [\<iostream\>](../standard-library/iostream.md)에 선언된 `clog`와 잠재적으로 충돌할 수 있으므로 \<complex.h\>에 선언된 이름 `clog`는 `std` 네임스페이스에는 정의되어 있지 않습니다.  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [STL 개요](../standard-library/cpp-standard-library-overview.md)