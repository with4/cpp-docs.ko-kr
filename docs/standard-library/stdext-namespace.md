---
title: "stdext 네임스페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_DEFINE_DEPRECATED_HASH_CLASSES 기호"
  - "stdext 네임스페이스"
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# stdext 네임스페이스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[\<hash\_map\>](../standard-library/hash-map.md) 및 [\<hash\_set\>](../standard-library/hash-set.md) 헤더 파일의 멤버는 현재 ISO C\+\+ 표준에 포함되지 않습니다. 따라서 C\+\+ 표준을 계속 준수하기 위해 이러한 형식 및 멤버를 `std` 네임스페이스에서 `stdext` 네임스페이스로 이동했습니다.  
  
 기본값인 [\/Ze](../build/reference/za-ze-disable-language-extensions.md)로 컴파일하는 경우 \<hash\_map\> 및 \<hash\_set\> 헤더 파일의 멤버에 `std`를 사용하면 컴파일러에서 경고를 표시합니다. 이 경고를 사용하지 않도록 설정하려면 [경고](../preprocessor/warning.md) pragma를 사용합니다.  
  
 **\/Ze**를 사용하여 \<hash\_map\> 및 \<hash\_set\> 헤더 파일의 멤버에 `std`를 사용할 경우 컴파일러에서 오류를 생성하도록 하려면 모든 표준 C\+\+ 라이브러리 헤더 파일에서 \#include'ing 앞에 다음 지시문을 추가합니다.  
  
```  
#define _DEFINE_DEPRECATED_HASH_CLASSES 0  
```  
  
 **\/Za**로 컴파일하는 경우 컴파일러에서 오류를 생성합니다.  
  
## 참고 항목  
 [STL 개요](../standard-library/cpp-standard-library-overview.md)