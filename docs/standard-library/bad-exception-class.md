---
title: "bad_exception 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: exception/std::bad_exception
dev_langs: C++
helpviewer_keywords: bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c3a322ce0ed9621e1413009092b0afb9572196a9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="badexception-class"></a>bad_exception 클래스
이 클래스는 예기치 않은 처리기에서 throw할 수 있는 예외를 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class bad_exception    : public exception {};  
```  
  
## <a name="remarks"></a>설명  
 [unexpected](../standard-library/exception-functions.md#unexpected)는 함수의 throw 목록에 `bad_exception`이 포함된 경우 [set_unexpected](../standard-library/exception-functions.md#set_unexpected)로 지정된 또 다른 함수를 종료하거나 호출하는 대신 `bad_exception`을 throw합니다.  
  
 **what**에서 반환된 값은 구현 시 정의된 C 문자열입니다. 멤버 함수는 예외를 발생시키지 않습니다.  
  
 `bad_exception` 클래스에 의해 상속된 멤버 목록은 [exception 클래스](../standard-library/exception-class.md)를 참조하세요.  
  
## <a name="example"></a>예제  
 `bad_exception`을 throw하는 [unexpected](../standard-library/exception-functions.md#unexpected) 사용의 예는 [set_unexpected](../standard-library/exception-functions.md#set_unexpected)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<exception>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
[exception 클래스](../standard-library/exception-class.md) [c + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)

