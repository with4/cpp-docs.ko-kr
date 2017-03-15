---
title: "Microsoft 전용 한정자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 22c7178c-f854-47fa-9de6-07d23fda58e1
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Microsoft 전용 한정자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 단원에서는 다음 영역의 Microsoft 전용 C\+\+ 확장에 대해 설명합니다.  
  
-   다른 포인터가 오프셋될 수 있는 기준으로 포인터를 사용하는 방식인 [기준 주소 지정](../cpp/based-addressing.md)  
  
-   [함수 호출 규칙](../cpp/calling-conventions.md)  
  
-   [\_\_declspec](../cpp/declspec.md) 키워드로 선언된 확장된 스토리지 클래스 특성  
  
-   [\_\_w64](../cpp/w64.md) 키워드  
  
 Microsoft 전용 키워드 중 대다수는 파생 형식을 형성하는 선언자를 수정하는 데 사용될 수 있습니다.  선언자에 대한 자세한 내용은 [선언자](http://msdn.microsoft.com/ko-kr/8a7b9b51-92bd-4ac0-b3fe-0c4abe771838)를 참조하십시오.  
  
### Microsoft 전용 키워드  
  
|키워드|의미|파생 형식을 만드는 데 사용됩니까?|  
|---------|--------|-------------------------|  
|[\_\_based](../cpp/based-grammar.md)|뒤에 오는 이름이 32비트 오프셋을 선언에 포함된 32비트 기준으로 선언합니다.|예|  
|[\_\_cdecl](../cpp/cdecl.md)|뒤에 오는 이름이 C 명명 및 호출 규칙을 사용합니다.|예|  
|[\_\_declspec](../cpp/declspec.md)|뒤에 오는 이름이 Microsoft 전용 저장소 클래스 특성을 지정합니다.|아니요|  
|[\_\_fastcall](../cpp/fastcall.md)|뒤에 오는 이름이 인수 전달 시 가능하면 스택 대신 레지스터를 사용하는 함수를 선언합니다.|예|  
|[\_\_restrict](../cpp/extension-restrict.md)|\_\_declspec\([제한](../cpp/restrict.md)\)과 유사하지만 변수에서 사용됩니다.|아니요|  
|[\_\_stdcall](../cpp/stdcall.md)|뒤에 오는 이름이 표준 호출 규칙을 준수하는 함수를 지정합니다.|예|  
|[\_\_w64](../cpp/w64.md)|64비트 컴파일러에서 더 큰 형식으로 데이터 형식을 표시합니다.|아니요|  
|[\_\_unaligned](../cpp/unaligned.md)|형식 또는 다른 데이터의 포인터가 정렬되지 않음을 지정합니다.|아니요|  
|[\_\_vectorcall](../cpp/vectorcall.md)|뒤에 오는 이름이 인수 전달 시 가능하면 스택 대신 SSE 레지스터 등의 레지스터를 사용하는 함수를 선언합니다.|예|  
  
## 참고 항목  
 [C\+\+ 언어 참조](../cpp/cpp-language-reference.md)