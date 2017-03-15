---
title: "WeakReference::DecrementStrongReference 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::WeakReference::DecrementStrongReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DecrementStrongReference 메서드"
ms.assetid: 97d70d9f-41b8-4f8d-a6fa-4137cc4f9029
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# WeakReference::DecrementStrongReference 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
ULONG DecrementStrongReference();  
```  
  
## <a name="remarks"></a>설명  
 현재 WeakReference 개체의 강력한 참조 횟수를 감소 시킵니다.  
  
 강력한 참조로 설정 되어 강력한 참조 횟수가 0 인 경우 `nullptr`합니다.  
  
## <a name="return-value"></a>반환 값  
 감소 된 강력한 참조 수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임 스페이스:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
[WeakReference 클래스](../windows/weakreference-class1.md)  
 [Microsoft::WRL::Details 네임 스페이스](../windows/microsoft-wrl-details-namespace.md)