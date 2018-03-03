---
title: "Factorycache:: Cookie 데이터 멤버 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache::cookie
dev_langs:
- C++
helpviewer_keywords:
- cookie data member
ms.assetid: b1bc79af-a896-4e3b-8afa-64733022eddf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 31f1b4e6cdeb2ec18d196d369f25053e91daec95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="factorycachecookie-data-member"></a>FactoryCache::cookie 데이터 멤버
Windows 런타임 c + + 템플릿 라이브러리 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
union {   
   WINRT_REGISTRATION_COOKIE winrt;  
   DWORD com;   
} cookie;  
```  
  
## <a name="remarks"></a>설명  
 등록된 된 Windows 런타임 또는 COM 클래스 개체를 식별 하 고 나중에 개체를 등록 취소를 사용 하는 값을 포함 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [FactoryCache 구조체](../windows/factorycache-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)