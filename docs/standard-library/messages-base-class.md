---
title: "messages_base 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocmes/std::messages_base
dev_langs:
- C++
helpviewer_keywords:
- messages_base class
ms.assetid: 9aad38c6-4c13-445d-b096-364bd0836efb
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: e95f92d910919ed0fc07943ff7b452ddd7d6b203
ms.contentlocale: ko-kr
ms.lasthandoff: 10/03/2017

---
# <a name="messagesbase-class"></a>messages_base 클래스
기본 클래스는 메시지 카탈로그에 대한 `int` 형식을 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```
struct messages_base : locale::facet {
    typedef int catalog;
    explicit messages_base(size_t _Refs = 0)
};
```  
  
## <a name="remarks"></a>설명  
 형식 카탈로그는 messages:: [do_open](../standard-library/messages-class.md#do_open)에서 가능한 반환 값을 설명하는 `int` 형식의 동의어입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<locale>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)




