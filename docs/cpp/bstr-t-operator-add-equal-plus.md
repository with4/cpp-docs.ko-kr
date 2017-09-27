---
title: _bstr_t::operator + =, + | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
dev_langs:
- C++
helpviewer_keywords:
- += operator, appending strings
- + operator, _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 0ba8936df56359523a76992866642521f899af69
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="bstrtoperator--"></a>_bstr_t::operator +=, +
**Microsoft 전용**  
  
 `_bstr_t` 개체의 끝에 문자를 추가하거나 두 문자열을 연결합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      _bstr_t& operator+=(  
   const _bstr_t& s1   
);  
_bstr_t operator+(  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const char* s2,  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const wchar_t* s3,  
   const _bstr_t& s1   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *s1*  
 `_bstr_t` 개체입니다.  
  
 *s2*  
 멀티바이트 문자열입니다.  
  
 `s3`  
 유니코드 문자열입니다.  
  
## <a name="remarks"></a>설명  
 이러한 연산자는 다음과 같이 문자열 연결을 수행합니다.  
  
-   **operator + = (***s1***)** 에 캡슐화 된 문자를 추가 `BSTR` 의 *s1* 이 개체의 캡슐화 된 의끝에`BSTR`.      
  
-   **operator + (***s1***)** 반환 새 `_bstr_t` 이 개체를 연결 하 여 형식이 `BSTR` 의 *s1*합니다.      
  
-   **operator + (***s2***&#124;** *s1***)** 반환 새 `_bstr_t` 멀티 바이트 문자열을 연결 하 여 형식이 *s2*유니코드로 변환 된와 `BSTR` 에 캡슐화 된 *s1*합니다.          
  
-   **operator + (** `s3` **,***s1***)** 반환 새 `_bstr_t` 유니코드 문자열을 연결 하 여 형식이 `s3` 와 `BSTR` 에 캡슐화 된 *s1*합니다.        
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_bstr_t 클래스](../cpp/bstr-t-class.md)
