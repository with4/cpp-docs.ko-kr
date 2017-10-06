---
title: _com_error::HelpContext | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::HelpContext
dev_langs:
- C++
helpviewer_keywords:
- HelpContext method
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
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
ms.openlocfilehash: d3eb0678e7d3b7cb4c1824cf17bc25499bf0c0ce
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorhelpcontext"></a>_com_error::HelpContext
**Microsoft 전용**  
  
 호출 **ierrorinfo:: Gethelpcontext** 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
DWORD HelpContext( ) const throw( );  
  
```  
  
## <a name="return-value"></a>반환 값  
 결과 반환 **ierrorinfo:: Gethelpcontext** 에 대 한는 **IErrorInfo** 내에 기록 된 개체는 `_com_error` 개체입니다. 없는 경우 **IErrorInfo** 개체는 기록, 0을 반환 합니다.  
  
## <a name="remarks"></a>설명  
 호출 하는 동안 모든 오류는 **ierrorinfo:: Gethelpcontext** 메서드는 무시 됩니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_error 클래스](../cpp/com-error-class.md)
