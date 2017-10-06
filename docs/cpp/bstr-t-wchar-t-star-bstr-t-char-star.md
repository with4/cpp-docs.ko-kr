---
title: _bstr_t::wchar_t *, _bstr_t::char * | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::wchar_t*
- _bstr_t::char*
dev_langs:
- C++
helpviewer_keywords:
- operator wchar_t* [C++]
- operator char* [C++]
ms.assetid: acd9f4a7-b427-42c2-aaae-acae21cab317
caps.latest.revision: 9
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
ms.openlocfilehash: 159186e053a43396c4589fafd142c78a75dbebde
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="bstrtwchart-bstrtchar"></a>_bstr_t::wchar_t*, _bstr_t::char*
**Microsoft 전용**  
  
 BSTR 문자는 좁거나 넓은 문자 배열로 반환됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      operator const wchar_t*( ) const throw( );   
operator wchar_t*( ) const throw( );   
operator const char*( ) const;   
operator char*( ) const;  
```  
  
## <a name="remarks"></a>설명  
 이러한 연산자는 `BSTR` 개체로 캡슐화된 문자 데이터를 추출하는 데 사용될 수 있습니다. 반환된 포인터에 새 값을 할당하면 원래 BSTR 데이터는 수정되지 않습니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_bstr_t 클래스](../cpp/bstr-t-class.md)
