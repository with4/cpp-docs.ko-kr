---
title: "&lt;exception&gt; | Microsoft Docs"
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
  - "<exception>"
  - "std::<exception>"
  - "std.<exception>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exception 헤더"
ms.assetid: 28900768-5dd7-4834-b907-5e37ab3407db
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;exception&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

여러 가지 형식 및 예외 처리와 관련된 함수를 정의합니다. 시스템이 오류에서 복구될 수 있는 경우에 예외 처리가 사용됩니다. 함수에서 프로그램으로 반환되는 컨트롤에 대한 방법을 제공합니다. 예외 처리를 통합하는 목표는 프로그램의 견고성을 높이는 동시에 오류 발생 시 체계적으로 복구하는 방법을 제공하는 것입니다.  
  
## <a name="syntax"></a>구문  
  
```  
#include <exception>  
  
```  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[exception_ptr](../Topic/%3Cexception%3E%20typedefs.md#exception_ptr)|예외에 대한 포인터를 설명하는 형식입니다.|  
|[terminate_handler](../Topic/%3Cexception%3E%20typedefs.md#terminate_handler)|`terminate_handler`로 사용하는 데 적합한 함수에 대한 포인터를 설명하는 형식입니다.|  
|[unexpected_handler](../Topic/%3Cexception%3E%20typedefs.md#unexpected_handler)|`unexpected_handler`로 사용하는 데 적합한 함수에 대한 포인터를 설명하는 형식입니다.|  
  
### <a name="functions"></a>함수  
  
|||  
|-|-|  
|[current_exception](../Topic/%3Cexception%3E%20functions.md#current_exception)|현재 예외에 대한 포인터를 가져옵니다.|  
|[get_terminate](../Topic/%3Cexception%3E%20functions.md#get_terminate)|현재 `terminate_handler` 함수를 가져옵니다.|  
|[get_unexpected](../Topic/%3Cexception%3E%20functions.md#get_unexpected)|현재 `unexpected_handler` 함수를 가져옵니다.|  
|[make_exception_ptr](../Topic/%3Cexception%3E%20functions.md#make_exception_ptr)|예외의 복사본이 들어있는 `exception_ptr` 개체를 만듭니다.|  
|[rethrow_exception](../Topic/%3Cexception%3E%20functions.md#rethrow_exception)|매개 변수로 전달되는 예외를 throw합니다.|  
|[set_terminate](../Topic/%3Cexception%3E%20functions.md#set_terminate)|프로그램을 종료할 때 호출할 새 `terminate_handler`를 설정합니다.|  
|[set_unexpected](../Topic/%3Cexception%3E%20functions.md#set_unexpected)|예기치 않은 예외가 발생할 경우를 위해 새 `unexpected_handler`를 설정합니다.|  
|[종료](../Topic/%3Cexception%3E%20functions.md#terminate)|종료 처리기를 호출합니다.|  
|[uncaught_exception](../Topic/%3Cexception%3E%20functions.md#uncaught_exception)|반환 **true** throw 된 예외가 현재 처리 중인 경우에 합니다.|  
|[예기치 않은](../Topic/%3Cexception%3E%20functions.md#unexpected)|예기치 않은 처리기를 호출합니다.|  
  
### <a name="classes"></a>클래스  
  
|||  
|-|-|  
|[bad_exception 클래스](../standard-library/bad-exception-class.md)|이 클래스는 `unexpected_handler`에서 throw할 수 있는 예외를 설명합니다.|  
|[exception 클래스](Exception%20Class.xml)|이 클래스는 특정 식과 표준 C++ 라이브러리로 throw된 모든 예외에 대한 기본 클래스로 사용됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)

