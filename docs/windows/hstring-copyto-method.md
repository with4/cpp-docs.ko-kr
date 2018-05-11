---
title: 'Hstring:: Copyto 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: a1fd2ef0-e175-4c18-927b-550e02a89e43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b44974faf5fc1f068d28d7febe3ed2a266f4869e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="hstringcopyto-method"></a>HString::CopyTo 메서드
현재 HString 복사본 개체 HSTRING 개체입니다.  
  
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
 [HString 클래스](../windows/hstring-class.md)