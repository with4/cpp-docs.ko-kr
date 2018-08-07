---
title: 'Hstring:: Getaddressof 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::GetAddressOf
dev_langs:
- C++
ms.assetid: 6050decf-5f99-49f0-9497-1c8192c485ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7d4804373045d12c2e251e2de61b7aefd52ec916
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874670"
---
# <a name="hstringgetaddressof-method"></a>HString::GetAddressOf 메서드
기본 HSTRING 핸들에 대 한 포인터를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HSTRING* GetAddressOf() throw()  
```  
  
## <a name="return-value"></a>반환 값  
 기본 HSTRING 핸들에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 이 작업 후에 기본 HSTRING 핸들의 문자열 값이 제거됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HString 클래스](../windows/hstring-class.md)