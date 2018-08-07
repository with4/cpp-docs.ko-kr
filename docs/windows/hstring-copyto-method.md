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
ms.openlocfilehash: 65d8e259b74bcdffbf11c6c96172d918f9db1b50
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570875"
---
# <a name="hstringcopyto-method"></a>HString::CopyTo 메서드
현재 복사 **HString** 개체를 HSTRING 개체로 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CopyTo(  
   _Out_ HSTRING *str  
   ) const throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 *str*  
 복사본을 받는 HSTRING입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 호출 합니다 [WindowsDuplicateString](http://msdn.microsoft.com/library/br224634.aspx) 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HString 클래스](../windows/hstring-class.md)