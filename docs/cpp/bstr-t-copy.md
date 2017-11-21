---
title: _bstr_t::copy | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _bstr_t::copy
dev_langs: C++
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5c7a3bb2997bbec1c0e402c14985353dcf0bc768
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="bstrtcopy"></a>_bstr_t::copy
**Microsoft 전용**  
  
 캡슐화된 `BSTR`의 복사본을 구성합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      BSTR copy(  
  bool fCopy = true  
) const;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fCopy`  
 경우 **true**, **복사** 는 포함 된 복사본을 반환 `BSTR`, 그렇지 않으면 **복사** 실제 BSTR을 반환 합니다.  
  
## <a name="remarks"></a>설명  
 캡슐화된 `BSTR` 개체에 새로 할당된 복사본을 반환합니다.  
  
## <a name="example"></a>예제  
  
```  
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t  
   *pVal = m_bsConStr.copy();  
}  
```  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_bstr_t 클래스](../cpp/bstr-t-class.md)