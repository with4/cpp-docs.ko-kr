---
title: 'Creatormap:: Activationid 데이터 멤버 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap::activationId
dev_langs:
- C++
helpviewer_keywords:
- activationId data member
ms.assetid: 77518b76-6e6a-4b48-8e2e-a4c7c67769e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9c4ff889f808eda00e5b2ce426cd800678b4829f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881798"
---
# <a name="creatormapactivationid-data-member"></a>CreatorMap::activationId 데이터 멤버
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
union {   
   const IID* clsid;  
   const wchar_t* (*getRuntimeName)();  
} activationId;  
```  
  
## <a name="parameters"></a>매개 변수  
 `clsid`  
 인터페이스 ID입니다.  
  
 `getRuntimeName`  
 개체의 Windows 런타임 이름을 검색 하는 함수입니다.  
  
## <a name="remarks"></a>설명  
 클래식 COM 클래스 ID 또는 Windows 런타임 이름에 의해 식별 되는 개체 ID를 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [CreatorMap 구조체](../windows/creatormap-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)