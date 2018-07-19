---
title: _bstr_t::copy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::copy
dev_langs:
- C++
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d23f204e7e8a545fbee7ab516495ed711d7984a9
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944638"
---
# <a name="bstrtcopy"></a>_bstr_t::copy
**Microsoft 전용**  
  
 캡슐화된 `BSTR`의 복사본을 구성합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
BSTR copy( bool fCopy = true ) const;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *fCopy*  
 TRUE 이면 `copy` 포함된 된 복사본을 반환 합니다 `BSTR`, 그렇지 않으면 `copy` 는 실제 BSTR을 반환 합니다.  
  
## <a name="remarks"></a>설명  
 캡슐화된 `BSTR` 개체에 새로 할당된 복사본을 반환합니다.  
  
## <a name="example"></a>예  
  
```cpp 
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t  
   *pVal = m_bsConStr.copy();  
}  
```  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_bstr_t 클래스](../cpp/bstr-t-class.md)