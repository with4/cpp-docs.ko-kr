---
title: _bstr_t::GetBSTR | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::GetBSTR
dev_langs:
- C++
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 376951862a82d6588221b592238c9346d31bad4d
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="bstrtgetbstr"></a>_bstr_t::GetBSTR
**Microsoft 전용**  
  
 `BSTR`에 의해 래핑되는 `_bstr_t`의 시작 부분을 가리킵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
BSTR& GetBSTR( );  
  
```  
  
## <a name="return-value"></a>반환 값  
 `BSTR`에 의해 래핑되는 `_bstr_t`의 시작 부분입니다.  
  
## <a name="remarks"></a>설명  
 `GetBSTR`는 `_bstr_t`을 공유하는 모든 `BSTR` 개체에 영향을 줍니다. 두 개 이상의 `_bstr_t`는 복사 생성자와 `BSTR`를 사용하여 `operator=`을 공유할 수 있습니다.  
  
## <a name="example"></a>예제  
 참조 [_bstr_t:: assign](../cpp/bstr-t-assign.md) 사용 하는 예제 `GetBSTR`합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_bstr_t 클래스](../cpp/bstr-t-class.md)
