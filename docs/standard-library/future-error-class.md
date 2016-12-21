---
title: "future_error 클래스 | Microsoft Docs"
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
  - "future/std::future_error"
dev_langs: 
  - "C++"
ms.assetid: 6071c545-ac2a-49ef-9967-07b0125da861
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# future_error 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Describes an exception object that can be thrown by methods of types that manage [future](../standard-library/future-class.md) objects.  
  
## 구문  
  
```  
class future_error : public logic_error {  
public:  
   future_error(error_code code);  
   const error_code& code() const throw();  
   const char *what() const throw();  
};  
```  
  
## 요구 사항  
 **헤더:** future  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [logic\_error 클래스](../standard-library/logic-error-class.md)   
 [error\_code 클래스](../standard-library/error-code-class.md)