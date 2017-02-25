---
title: "WeakReference::SetUnknown 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::WeakReference::SetUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetUnknown 메서드"
ms.assetid: 5dddb9e3-a7c1-4195-8166-97c5ab6e972f
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# WeakReference::SetUnknown 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
void SetUnknown(  
   _In_ IUnknown* unk  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `unk`  
 에 대 한 포인터는 `IUnknown` 개체의 인터페이스입니다.  
  
## <a name="remarks"></a>설명  
 현재의 강력한 참조를 설정 `WeakReference` 개체를 지정 된 인터페이스 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임 스페이스:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목
[WeakReference 클래스](../windows/weakreference-class1.md)  
 [Microsoft::WRL::Details 네임 스페이스](../windows/microsoft-wrl-details-namespace.md)