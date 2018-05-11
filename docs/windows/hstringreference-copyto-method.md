---
title: 'Hstringreference:: Copyto 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 179d9b14-1ced-4b16-b297-19ca1e92a462
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f65c08cad438328eb1a0e15495774dbde6845f4d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="hstringreferencecopyto-method"></a>HStringReference::CopyTo 메서드
복사본은 현재 HStringReference 개체 HSTRING 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
HRESULT CopyTo(  
   _Out_ HSTRING *str  
   ) const throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `str`  
 복사본을 받는 HSTRING 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 [WindowsDuplicateString](http://msdn.microsoft.com/library/br224634.aspx) 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HStringReference 클래스](../windows/hstringreference-class.md)