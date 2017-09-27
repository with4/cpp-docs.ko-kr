---
title: "_bstr_t 관계형 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator>
- _bstr_t::operator==
- _bstr_t::operator>=
- _bstr_t::operator!=
- _bstr_t::operator<
- _bstr_t::operator<=
- _bstr_t::operator!
dev_langs:
- C++
helpviewer_keywords:
- '>= operator, comparing specific objects'
- operator<=, bstr
- '!= operator'
- operator ==, bstr
- operator!=, relational operators
- < operator, comparing specific objects
- relational operators, _bstr_t class
- operator==, bstr
- <= operator, with specific objects
- operator <=, bstr
- operator >=, bstr
- operator !=, relational operators
- '> operator, comparing specific objects'
- operator<, bstr
- == operator, with specific Visual C++ objects
- operator>=, bstr
- operator <, bstr
- operator >, bstr
ms.assetid: e153da72-37c3-4d8a-b8eb-730d65da64dd
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
ms.openlocfilehash: 4af54cf348765453fea3dd59959e00f623bef7e0
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="bstrt-relational-operators"></a>_bstr_t 관계형 연산자
**Microsoft 전용**  
  
 두 `_bstr_t` 개체를 비교합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      bool operator!( ) const throw( );   
bool operator==(  
   const _bstr_t& str   
) const throw( );  
bool operator!=(  
   const _bstr_t& str   
) const throw( );  
bool operator<(  
   const _bstr_t& str   
) const throw( );  
bool operator>(  
   const _bstr_t& str   
) const throw( );  
bool operator<=(  
   const _bstr_t& str   
) const throw( );  
bool operator>=(  
   const _bstr_t& str   
) const throw( );  
```  
  
## <a name="remarks"></a>설명  
 이러한 연산자는 두 `_bstr_t` 개체를 사전순으로 비교합니다. 할당 연산자는 반환 **true** 는 비교가 유효 하면 그렇지 않으면 반환 **false**합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_bstr_t 클래스](../cpp/bstr-t-class.md)
