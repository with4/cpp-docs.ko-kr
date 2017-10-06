---
title: _com_error::Description | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::Description
dev_langs:
- C++
helpviewer_keywords:
- Description method
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
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
ms.openlocfilehash: 0d91f6fded1fa1c4ea4d44cadd0d9285913b5f42
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="comerrordescription"></a>_com_error::Description
**Microsoft 전용**  
  
 호출 **ierrorinfo:: Getdescription** 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
_bstr_t Description( ) const;  
  
```  
  
## <a name="return-value"></a>반환 값  
 결과 반환 **ierrorinfo:: Getdescription** 에 대 한는 **IErrorInfo** 내에 기록 된 개체는 `_com_error` 개체입니다. 결과 `BSTR`은 `_bstr_t` 개체에 캡슐화됩니다. 없는 경우 **IErrorInfo** 는 빈 반환, 기록 `_bstr_t`합니다.  
  
## <a name="remarks"></a>설명  
 호출 된 **ierrorinfo:: Getdescription** 함수와 검색 **IErrorInfo** 내에 기록 된는 `_com_error` 개체입니다. 호출 하는 동안 모든 오류는 **ierrorinfo:: Getdescription** 메서드는 무시 됩니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_error 클래스](../cpp/com-error-class.md)
