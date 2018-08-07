---
title: _bstr_t::operator = | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator = [C++], bstr
- operator= [C++], bstr
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3dfed780e0769e342ff368af453fc70764a372f0
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404475"
---
# <a name="bstrtoperator-"></a>_bstr_t::operator =
**Microsoft 전용**  
  
 기존 `_bstr_t` 개체에 새 값을 할당합니다.  
  
## <a name="syntax"></a>구문  
  
```  
_bstr_t& operator=(const _bstr_t& s1) throw ( );  
_bstr_t& operator=(const char* s2);  
_bstr_t& operator=(const wchar_t* s3);  
_bstr_t& operator=(const _variant_t& var);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *s1*  
 기존 `_bstr_t` 개체에 할당될 `_bstr_t` 개체입니다.  
  
 *s2*  
 기존 `_bstr_t` 개체에 할당될 멀티바이트 문자열입니다.  
  
 *s3*  
 기존 `_bstr_t` 개체에 할당될 유니코드 문자열입니다.  
  
 *var*  
 기존 `_variant_t` 개체에 할당될 `_bstr_t` 개체입니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="example"></a>예  
 참조 [_bstr_t:: assign](../cpp/bstr-t-assign.md) 사용 하는 예제에 대 한 **연산자 =** 합니다.  
  
## <a name="see-also"></a>참고자료  
 [_bstr_t 클래스](../cpp/bstr-t-class.md)