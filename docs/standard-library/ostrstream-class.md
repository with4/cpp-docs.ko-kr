---
title: "ostrstream 클래스 | Microsoft Docs"
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
  - "std.oststream"
  - "oststream"
  - "std::oststream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ostrstream 클래스"
ms.assetid: e2e34679-b266-4728-a8e1-8eda5d400e46
caps.latest.revision: 20
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ostrstream 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 스트림 버퍼에 요소 및 인코드된 개체 삽입을 제어하는 개체를 설명합니다.  
  
## 구문  
  
```  
  
class ostrstream : public ostream  
  
```  
  
## 설명  
 이 개체는 `strstreambuf` 클래스의 개체를 저장합니다.  
  
> [!NOTE]
>  이 클래스는 사용되지 않습니다.  대신 [ostringstream](../Topic/ostringstream.md) 또는 [wostringstream](../Topic/wostringstream.md)을 사용하는 것이 좋습니다.  
  
### 생성자  
  
|||  
|-|-|  
|[ostrstream](../Topic/ostrstream::ostrstream.md)|`ostrstream` 형식의 개체를 생성합니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[freeze](../Topic/ostrstream::freeze.md)|스트림 버퍼 작업을 통해 스트림 버퍼를 사용할 수 없게 합니다.|  
|[pcount](../Topic/ostrstream::pcount.md)|제어되는 시퀀스에 기록되는 요소 수의 개수를 반환합니다.|  
|[rdbuf](../Topic/ostrstream::rdbuf.md)|스트림의 연결된 `strstreambuf` 개체에 대한 포인터를 반환합니다.|  
|[str](../Topic/ostrstream::str.md)|[freeze](../Topic/strstreambuf::freeze.md)를 호출한 다음 제어되는 시퀀스의 시작 부분에 대한 포인터를 반환합니다.|  
  
## 요구 사항  
 **헤더:** \<strstream\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [ostream](../Topic/ostream.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)