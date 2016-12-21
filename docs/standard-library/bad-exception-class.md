---
title: "bad_exception 클래스 | Microsoft Docs"
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
  - "std.bad_exception"
  - "bad_exception"
  - "std::bad_exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_exception 클래스"
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# bad_exception 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

클래스는 예기치 않은 처리기에서 throw 될 수 있는 예외를 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class bad_exception    : public exception {};  
```  
  
## <a name="remarks"></a>주의  
 [예기치 않은](../Topic/%3Cexception%3E%20functions.md#unexpected) 를 발생 시킵니다는 `bad_exception` 종료 하는 대신 또는 지정 된 다른 함수를 호출 하는 대신 [set_unexpected](../Topic/%3Cexception%3E%20functions.md#set_unexpected) 경우 `bad_exception` 함수의 throw 목록에 포함 됩니다.  
  
 반환한 값 **어떤** 은 구현 시 정의 C 문자열입니다. 멤버 함수는 예외를 발생시키지 않습니다.  
  
 상속 된 멤버의 목록은 `bad_exception` 클래스를 참조 하십시오 [exception 클래스](../standard-library/exception-class1.md)합니다.  
  
## <a name="example"></a>예제  
 참조 [set_unexpected](../Topic/%3Cexception%3E%20functions.md#set_unexpected) 의 사용에 대 한 예제 [예기치 않은](../Topic/%3Cexception%3E%20functions.md#unexpected) 시 키 지는 `bad_exception`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \< 예외>  
  
 **네임 스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
[exception 클래스](../standard-library/exception-class1.md)
 [c + + 표준 라이브러리의 스레드 안전성](../standard-library/thread-safety-in-the-cpp-standard-library.md)

