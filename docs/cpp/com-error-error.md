---
title: _com_error::Error | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::Error
- Error
dev_langs:
- C++
helpviewer_keywords:
- Error method [C++]
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
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
ms.openlocfilehash: df8f409430b802350c1696592fc7f096283d015d
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorerror"></a>_com_error::Error
**Microsoft 전용**  
  
 생성자에 전달된 `HRESULT`를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
HRESULT Error( ) const throw( );  
  
```  
  
## <a name="return-value"></a>반환 값  
 생성자에 전달된 원시 `HRESULT` 항목입니다.  
  
## <a name="remarks"></a>설명  
 `HRESULT` 개체에서 캡슐화된 `_com_error` 항목을 검색합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_error 클래스](../cpp/com-error-class.md)
