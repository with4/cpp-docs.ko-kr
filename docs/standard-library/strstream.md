---
title: "&lt;strstream&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.<strstream>"
  - "std::<strstream>"
  - "<strstream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strstream 헤더"
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# &lt;strstream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`char` 개체의 할당된 배열에 저장된 시퀀스에 대한 Iostreams 작업을 지원하는 여러 클래스를 정의합니다.  이러한 시퀀스는 C 문자열로\/에서 쉽게 변환됩니다.  
  
## 구문  
  
```  
  
#include <strstream>  
  
```  
  
## 설명  
 `strstream` 형식의 개체는 C 문자열인 `char` \*로 작업합니다.  [basic\_string](../standard-library/basic-string-class.md) 형식의 개체로 작업하려면 [\<sstream\>](../standard-library/sstream.md)을 사용합니다.  
  
> [!NOTE]
>  `<strstream>`의 클래스는 사용되지 않습니다.  `<sstream>`의 클래스를 대신 사용하는 것이 좋습니다.  
  
### 클래스  
  
|||  
|-|-|  
|[strstreambuf 클래스](../standard-library/strstreambuf-class.md)|이 클래스는 `char` 배열 개체에 저장된 요소의 시퀀스로\/에서 요소의 전송을 제어하는 스트림 버퍼를 설명합니다.|  
|[istrstream 클래스](../standard-library/istrstream-class.md)|이 클래스는 [strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 스트림 버퍼에서 요소 및 인코드된 개체 추출을 제어하는 개체를 설명합니다.|  
|[ostrstream 클래스](../standard-library/ostrstream-class.md)|이 클래스는 [strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 스트림 버퍼로 요소 및 인코드된 개체 삽입을 제어하는 개체를 설명합니다.|  
|[strstream 클래스](../standard-library/strstream-class.md)|이 클래스는 [strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 스트림 버퍼를 사용한 요소 및 인코드된 개체 삽입 및 추출을 제어하는 개체를 설명합니다.|  
  
## 참고 항목  
 [\<strstream\>](../standard-library/strstream.md)   
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)