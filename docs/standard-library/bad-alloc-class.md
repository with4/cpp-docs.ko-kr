---
title: "bad_alloc 클래스 | Microsoft Docs"
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
  - "std::bad_alloc"
  - "new/std:bad_alloc"
  - "bad_alloc"
  - "std.bad_alloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_alloc 클래스"
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
caps.latest.revision: 26
caps.handback.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# bad_alloc 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 클래스는 할당 요청이 성공하지 못했음을 나타내기 위해 발생하는 예외를 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class bad_alloc : public exception {  
    bad_alloc();
virtual ~bad_alloc();

};  
```  
  
## <a name="remarks"></a>주의  
 반환한 값 **어떤** 은 구현 시 정의 C 문자열입니다. 멤버 함수는 예외를 발생시키지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \< 새로 만들기>  
  
 **네임 스페이스:** std  
  
## <a name="example"></a>예제  
  
```  
// bad_alloc.cpp  
// compile with: /EHsc  
#include<new>  
#include<iostream>  
using namespace std;  
  
int main() {  
   char* ptr;  
   try {  
      ptr = new char[(~unsigned int((int)0)/2) - 1];  
      delete[] ptr;  
   }  
   catch( bad_alloc &ba) {  
      cout << ba.what( ) << endl;  
   }  
}  
```  
  
## <a name="sample-output"></a>샘플 출력  
  
```  
bad allocation  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \< 새로 만들기>  
  
## <a name="see-also"></a>참고 항목
 [exception 클래스](../standard-library/exception-class1.md)  
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)

