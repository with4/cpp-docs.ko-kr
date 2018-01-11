---
title: "ctype_base 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: locale/std::ctype_base
dev_langs: C++
helpviewer_keywords: ctype_base class
ms.assetid: ccffe891-d7ab-4d22-baf8-8eb6d438a96d
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 83f467f8d06956678795bf97fed60fe9f22c32f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ctypebase-class"></a>ctype_base 클래스
이 클래스는 템플릿 클래스 [ctype](../standard-library/ctype-class.md)의 패싯에 대한 기본 클래스로 사용됩니다. 개별적으로 또는 전체 범위 내에서 특성을 분류 또는 테스트하는 데 사용하는 열거형을 정의하는 데 사용하는 ctype 클래스의 기본 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```
struct ctype_base : public locale::facet
{
    enum
 {
    alnum,
 alpha,
    cntrl,
 digit,
    graph,
 lower,
    print,
 punct,
    space,
 upper,
    xdigit
 };
    typedef short mask;
    ctype_base(
 size_t _Refs = 0);

 ~ctype_base();

};
```  
  
## <a name="remarks"></a>설명  
 열거형 마스크를 정의합니다. 각 열거형 상수는 \<ctype.h> 헤더에 선언된 비슷한 이름의 함수에 정의된 것처럼 문자를 분류하는 다양한 방법의 특징을 지정합니다. 상수는 다음과 같습니다.  
  
- **space**([isspace](../standard-library/locale-functions.md#isspace) 함수)  
  
- **print**([isprint](../standard-library/locale-functions.md#isprint) 함수)  
  
- **cntrl**([iscntrl](../standard-library/locale-functions.md#iscntrl) 함수)  
  
- **upper**(함수 [isupper](../standard-library/locale-functions.md#isupper))  
  
- **lower**([islower](../standard-library/locale-functions.md#islower) 함수)  
  
- **digit**([isdigit](../standard-library/locale-functions.md#isdigit) 함수)  
  
- **punct**([ispunct](../standard-library/locale-functions.md#ispunct) 함수)  
  
- **xdigit**([isxdigit](../standard-library/locale-functions.md#isxdigit) 함수)  
  
- **alpha**([isalpha](../standard-library/locale-functions.md#isalpha) 함수)  
  
- **alnum**([isalnum](../standard-library/locale-functions.md#isalnum) 함수)  
  
- **graph**([isgraph](../standard-library/locale-functions.md#isgraph) 함수)  
  
 이러한 상수를 OR 연산하여 분류의 조합을 특징지을 수 있습니다. 항상 true를 특히 **alnum과** = = ( **알파** &#124; **자리** \) 및 **그래프** \= \= \( **alnum과** &#124; **좁 힘**).  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<locale>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)



