---
title: _bstr_t::operator + =, + | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
dev_langs:
- C++
helpviewer_keywords:
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a2ea7cd3b93f7445190f16a92a580fe9628a976
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944230"
---
# <a name="bstrtoperator--"></a>_bstr_t::operator +=, +
**Microsoft 전용**  
  
 `_bstr_t` 개체의 끝에 문자를 추가하거나 두 문자열을 연결합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
_bstr_t& operator+=( const _bstr_t& s1 );  
_bstr_t operator+( const _bstr_t& s1 );  
friend _bstr_t operator+( const char* s2, const _bstr_t& s1);  
friend _bstr_t operator+( const wchar_t* s3, const _bstr_t& s1);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *s1*  
 `_bstr_t` 개체입니다.  
  
 *s2*  
 멀티바이트 문자열입니다.  
  
 *s3*  
 유니코드 문자열입니다.  
  
## <a name="remarks"></a>설명  
 이러한 연산자는 다음과 같이 문자열 연결을 수행합니다.  
  
-   **operator + = (***s1***)** 캡슐화 된 문자를 추가 `BSTR` 의 *s1* 캡슐화 가이개체의끝에`BSTR`.      
  
-   **operator + (***s1***)** 새 반환 `_bstr_t` 이 개체를 연결 하 여 형성 된 `BSTR` 의 지 문으로 *s1*합니다.      
  
-   **operator + (***s2***&#124;***s1***)** 새 반환 `_bstr_t` 연결 하 여 형성 된를 멀티 바이트 문자열 *s2*유니코드로 변환 된와 `BSTR` 캡슐화 *s1*합니다.          
  
-   **operator + (***s3* **하십시오***s1***)** 반환 된 새 `_bstr_t` 유니코드 문자열을 연결 하 여 형성 된 *s3* 사용 하 여 합니다 `BSTR` 캡슐화 *s1*합니다.        
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_bstr_t 클래스](../cpp/bstr-t-class.md)