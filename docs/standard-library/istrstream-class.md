---
title: "istrstream 클래스 | Microsoft Docs"
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
  - "istrstream"
  - "std::istrstream"
  - "std.istrstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "istrstream 클래스"
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
caps.latest.revision: 20
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# istrstream 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 스트림 버퍼에서 요소 및 인코드된 개체 추출을 제어하는 개체를 설명합니다.  
  
## 구문  
  
```  
  
class istrstream : public istream  
  
```  
  
## 설명  
 이 개체는 `strstreambuf` 클래스의 개체를 저장합니다.  
  
> [!NOTE]
>  이 클래스는 사용되지 않습니다. 사용 하는 것이 좋습니다 [istringstream](../Topic/istringstream.md) 또는 [wistringstream](../Topic/wistringstream.md) 대신 합니다.  
  
### 생성자  
  
|||  
|-|-|  
|[istrstream](../Topic/istrstream::istrstream.md)|`istrstream` 형식의 개체를 생성합니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[rdbuf](../Topic/istrstream::rdbuf.md)|스트림의 연결된 `strstreambuf` 개체에 대한 포인터를 반환합니다.|  
|[str](../Topic/istrstream::str.md)|[freeze](../Topic/strstreambuf::freeze.md)를 호출한 다음 제어되는 시퀀스의 시작 부분에 대한 포인터를 반환합니다.|  
  
## 요구 사항  
 **헤더:** \<strstream\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [istream](../Topic/istream.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)