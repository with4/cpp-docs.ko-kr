---
title: "Comptr:: Getaddressof 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::GetAddressOf
dev_langs: C++
helpviewer_keywords: GetAddressOf method
ms.assetid: 972a41d0-c2ef-4ae3-b2cd-77cc45156ac9
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d62a1bca258e0903ddd4e71b161d87d926588248
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="comptrgetaddressof-method"></a>ComPtr::GetAddressOf 메서드
이 ComPtr이 나타내는 인터페이스에 대한 포인터를 포함하는, [ptr_](../windows/comptr-ptr-data-member.md) 데이터 멤버의 주소를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
T* const* GetAddressOf() const;  
T** GetAddressOf();  
```  
  
## <a name="return-value"></a>반환 값  
 변수의 주소입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)