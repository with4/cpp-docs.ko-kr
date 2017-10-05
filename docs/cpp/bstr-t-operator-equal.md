---
title: _bstr_t::operator = | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator =, bstr
- operator=, bstr
- = operator, with specific Visual C++ objects
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
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
ms.openlocfilehash: 445c18ece9b998d5cfa75a1c9fe5bde3b60b2e52
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="bstrtoperator-"></a>_bstr_t::operator =
**Microsoft 전용**  
  
 기존 `_bstr_t` 개체에 새 값을 할당합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      _bstr_t& operator=(  
   const _bstr_t& s1   
) throw ( );  
_bstr_t& operator=(  
   const char* s2   
);  
_bstr_t& operator=(  
   const wchar_t* s3   
);  
_bstr_t& operator=(  
   const _variant_t& var   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *s1*  
 기존 `_bstr_t` 개체에 할당될 `_bstr_t` 개체입니다.  
  
 *s2*  
 기존 `_bstr_t` 개체에 할당될 멀티바이트 문자열입니다.  
  
 `s3`  
 기존 `_bstr_t` 개체에 할당될 유니코드 문자열입니다.  
  
 `var`  
 기존 `_variant_t` 개체에 할당될 `_bstr_t` 개체입니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="example"></a>예제  
 참조 [_bstr_t:: assign](../cpp/bstr-t-assign.md) 사용 하는 예제에 대 한 `operator=`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [_bstr_t 클래스](../cpp/bstr-t-class.md)
