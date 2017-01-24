---
title: "runtime_error 클래스 | Microsoft Docs"
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
  - "std.runtime_error"
  - "runtime_error"
  - "stdexcept/std::runtime_error"
  - "std::runtime_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "runtime_error 클래스"
ms.assetid: 4d0227bf-847b-45a2-a320-2351ebf98368
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# runtime_error 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 클래스는 프로그램이 실행되는 경우에만 검색될 수 있는 오류를 보고하기 위해 발생하는 모든 예외에 대한 기본 클래스로 사용됩니다.  
  
## 구문  
  
```  
class runtime_error : public exception {  
public:  
    explicit runtime_error(const string& message);  
    explicit runtime_error(const char *message);  
};  
```  
  
## 설명  
 반환한 값 [exception 클래스](../standard-library/exception-class1.md) 의 복사본 **메시지**`.`[데이터](../Topic/basic_string::data.md)합니다.  
  
## 예제  
  
```  
// runtime_error.cpp  
// compile with: /EHsc /GR  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
// runtime_error  
   try   
   {  
      locale loc( "test" );  
   }  
   catch ( exception &e )   
   {  
      cerr << "Caught " << e.what( ) << endl;  
      cerr << "Type " << typeid( e ).name( ) << endl;  
   };  
}  
```  
  
 **잘못 된 로캘 이름 형식 클래스 std::runtime\_error를 발견 되었습니다.**   
## 요구 사항  
 **머리글:** \< stdexcept \>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [exception 클래스](../standard-library/exception-class1.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)