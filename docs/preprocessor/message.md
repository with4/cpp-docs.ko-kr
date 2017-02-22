---
title: "message | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "message_CPP"
  - "vc-pragma.message"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메시지 pragma"
  - "pragma, message"
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# message
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

컴파일이 종료되지 않은 상태에서 문자열 리터럴을 표준 출력에 보냅니다.  
  
## 구문  
  
```  
  
#pragma message( messagestring )  
```  
  
## 설명  
 **message** pragma는 컴파일 타임에 알림 메시지를 표시하는 데 일반적으로 사용됩니다.  
  
 *messagestring* 매개 변수는 문자열 리터럴로 확장되는 매크로일 수 있으며 이러한 매크로를 문자열 리터럴과 원하는 조합으로 연결할 수 있습니다.  
  
 **message** pragma에 미리 정의된 매크로를 사용하는 경우 매크로가 문자열을 반환해야 합니다. 그렇지 않으면 매크로의 출력을 문자열로 변환해야 합니다.  
  
 다음 코드 조각은 컴파일 중 메시지를 표시하기 위해 **message** pragma를 사용합니다.  
  
```  
// pragma_directives_message1.cpp  
// compile with: /LD  
#if _M_IX86 >= 500  
#pragma message("_M_IX86 >= 500")  
#endif  
  
#pragma message("")  
  
#pragma message( "Compiling " __FILE__ )   
#pragma message( "Last modified on " __TIMESTAMP__ )  
  
#pragma message("")  
  
// with line number  
#define STRING2(x) #x  
#define STRING(x) STRING2(x)  
  
#pragma message (__FILE__ "[" STRING(__LINE__) "]: test")  
  
#pragma message("")  
```  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)