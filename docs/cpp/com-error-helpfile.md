---
title: _com_error::HelpFile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::HelpFile
dev_langs:
- C++
helpviewer_keywords:
- HelpFile method
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
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
ms.openlocfilehash: 7e1e9ec8c7d6684bb7b244fd9ba6773b6f1460e1
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorhelpfile"></a>_com_error::HelpFile
**Microsoft 전용**  
  
 호출 **ierrorinfo:: Gethelpfile** 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
_bstr_t HelpFile() const;  
  
```  
  
## <a name="return-value"></a>반환 값  
 결과 반환 **ierrorinfo:: Gethelpfile** 에 대 한는 **IErrorInfo** 내에 기록 된 개체는 `_com_error` 개체입니다. 결과 BSTR은 `_bstr_t` 개체에 캡슐화됩니다. 없는 경우 **IErrorInfo** 는 빈 반환, 기록 `_bstr_t`합니다.  
  
## <a name="remarks"></a>설명  
 호출 하는 동안 모든 오류는 **ierrorinfo:: Gethelpfile** 메서드는 무시 됩니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_error 클래스](../cpp/com-error-class.md)
