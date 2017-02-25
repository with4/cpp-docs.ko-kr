---
title: "strstreambuf 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.strstreambuf"
  - "strstreambuf"
  - "std::strstreambuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strstreambuf 클래스"
ms.assetid: b040b8ea-0669-4eba-8908-6a9cc159c54b
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# strstreambuf 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`char` 배열 개체에 저장된 요소의 시퀀스로\/에서 요소의 전송을 제어하는 스트림 버퍼를 설명합니다.  
  
## 구문  
  
```  
  
class strstreambuf : public streambuf  
  
```  
  
## 설명  
 개체 생성 방법에 따라 시퀀스의 변경 내용을 수용하도록 필요에 따라 개체를 할당, 확장 및 해제할 수 있습니다.  
  
 `strstreambuf` 클래스의 개체는 모드 정보의 여러 비트를 해당 `strstreambuf` 모드로 저장합니다. 이러한 비트는 제어되는 시퀀스가 다음과 같은지 여부를 나타냅니다.  
  
-   할당되었으며 결국 해제해야 하는지 여부  
  
-   수정할 수 있는지 여부  
  
-   저장소를 다시 할당하여 확장할 수 있는지 여부  
  
-   고정되어 개체가 아닌 에이전시에서 해당 개체를 삭제하거나 해제\(할당된 경우\)하기 전에 고정 해제해야 하는지 여부  
  
 고정된 제어되는 시퀀스는 이러한 별도 모드 비트의 상태에 관계없이 수정하거나 확장할 수 없습니다.  
  
 개체는 `strstreambuf` 할당을 제어하는 두 함수에 대한 포인터를 저장합니다. null 포인터인 경우 개체가 제어되는 시퀀스에 대한 저장소를 할당 및 해제하는 고유한 메서드를 만듭니다.  
  
> [!NOTE]
>  이 클래스는 사용되지 않습니다. 사용 하는 것이 좋습니다 [stringbuf](../Topic/stringbuf.md) 또는 [wstringbuf](../Topic/wstringbuf.md) 대신 합니다.  
  
### 생성자  
  
|||  
|-|-|  
|[strstreambuf](../Topic/strstreambuf::strstreambuf.md)|`strstreambuf` 형식의 개체를 생성합니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[freeze](../Topic/strstreambuf::freeze.md)|스트림 버퍼 작업을 통해 스트림 버퍼를 사용할 수 없게 합니다.|  
|[오버플로](../Topic/strstreambuf::overflow.md)|가득 찬 버퍼에 새 문자를 삽입할 때 호출할 수 있는 보호된 가상 함수입니다.|  
|[pbackfail](../Topic/strstreambuf::pbackfail.md)|요소를 입력 스트림에 다시 넣은 후 다음 포인터에서 가리키는 현재 요소로 설정하려고 하는 보호된 가상 멤버 함수입니다.|  
|[pcount](../Topic/strstreambuf::pcount.md)|제어되는 시퀀스에 기록되는 요소 수의 개수를 반환합니다.|  
|[seekoff](../Topic/strstreambuf::seekoff.md)|제어되는 스트림의 현재 위치를 변경하려고 하는 보호된 가상 멤버 함수입니다.|  
|[seekpos](../Topic/strstreambuf::seekpos.md)|제어되는 스트림의 현재 위치를 변경하려고 하는 보호된 가상 멤버 함수입니다.|  
|[str](../Topic/strstreambuf::str.md)|[freeze](../Topic/strstreambuf::freeze.md)를 호출한 다음 제어되는 시퀀스의 시작 부분에 대한 포인터를 반환합니다.|  
|[underflow](../Topic/strstreambuf::underflow.md)|입력 스트림에서 현재 요소를 추출하는 보호된 가상 함수입니다.|  
  
## 요구 사항  
 **헤더:** \<strstream\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [streambuf](../Topic/streambuf.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)