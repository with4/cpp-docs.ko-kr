---
title: _com_error::ErrorInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorInfo
- ErrorInfo
- _com_error.ErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- ErrorInfo method
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
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
ms.openlocfilehash: e80dafb5d1472ec28631b13ab05a0dea0b4de4ba
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorerrorinfo"></a>_com_error::ErrorInfo
**Microsoft 전용**  
  
 검색 된 **IErrorInfo** 개체 생성자에 전달 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
IErrorInfo * ErrorInfo( ) const throw( );  
  
```  
  
## <a name="return-value"></a>반환 값  
 원시 **IErrorInfo** 항목은 생성자에 전달 합니다.  
  
## <a name="remarks"></a>설명  
 캡슐화 된 검색 **IErrorInfo** 항목에 `_com_error` 개체 또는 **NULL** 없으면 **IErrorInfo** 항목이 기록 됩니다. 호출자에 게 호출 해야 **릴리스** 완료 되 면 반환된 된 개체에 사용 하 여 것입니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_error 클래스](../cpp/com-error-class.md)
