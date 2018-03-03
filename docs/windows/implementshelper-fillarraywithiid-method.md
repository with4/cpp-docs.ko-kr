---
title: "Implementshelper:: Fillarraywithiid 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid
dev_langs:
- C++
helpviewer_keywords:
- FillArrayWithIid method
ms.assetid: f60035ee-b7d6-4a08-966d-f88c646944c3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eeb2254933dc0f9f5e4b99ba4e010dbe3afbb7cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="implementshelperfillarraywithiid-method"></a>ImplementsHelper::FillArrayWithIid 메서드
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
void FillArrayWithIid(  
   _Inout_ unsigned long *index,   
   _Inout_ IID* iids) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `index`  
 이 작업에 대 한 시작 배열 요소를 나타내는 0부터 시작 인덱스입니다. 이 작업이 완료 되 면 `index` 1 씩 증가 합니다.  
  
 `iids`  
 Iid 형식의 배열입니다.  
  
## <a name="remarks"></a>설명  
 지정 된 배열 요소에 현재 0 번째 템플릿 매개 변수로 지정 된 인터페이스 ID를 삽입 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [ImplementsHelper 구조체](../windows/implementshelper-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)