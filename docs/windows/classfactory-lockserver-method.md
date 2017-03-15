---
title: "ClassFactory::LockServer 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ClassFactory::LockServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LockServer 메서드"
ms.assetid: 8d859815-956d-4f81-a5af-7cdee7e945de
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ClassFactory::LockServer 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 ClassFactory 개체에서 추적하는 기본 개체 수를 늘리거나 줄입니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDMETHOD(  
   LockServer  
)(BOOL fLock);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fLock`  
추적된 개체 수를 늘리려면  `true`입니다. 추적된 개체 수를 줄이려면 `false`입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 E_FAIL입니다.  
  
## <a name="remarks"></a>설명  
 ClassFactory는를 추적 개체의 기본 인스턴스에서 [모듈](../windows/module-class.md) 클래스입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ClassFactory 클래스](../windows/classfactory-class.md)