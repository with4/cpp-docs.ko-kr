---
title: "future_error 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: future/std::future_error
dev_langs: C++
ms.assetid: 6071c545-ac2a-49ef-9967-07b0125da861
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1fc5ba9a34ee5c1a29892e4ba6ebc25366e408be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="futureerror-class"></a>future_error 클래스
[future](../standard-library/future-class.md) 개체를 관리하는 형식의 메서드에서 throw될 수 있는 예외 개체를 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```
class future_error : public logic_error {
public:
    future_error(error_code code);

const error_code& code() const throw();

const char *what() const throw();

};
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<이후 >  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [logic_error 클래스](../standard-library/logic-error-class.md)   
 [error_code 클래스](../standard-library/error-code-class.md)
