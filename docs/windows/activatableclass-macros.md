---
title: "ActivatableClass 매크로 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ActivatableClass"
  - "ActivatableClassWithFactory"
  - "ActivatableClassWithFactoryEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivatableClassWithFactory"
  - "ActivatableClass"
  - "ActivatableClassWithFactoryEx"
ms.assetid: 9bd64709-ec2c-4678-8c96-ea5982622bdd
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ActivatableClass 매크로
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 된 클래스의 인스턴스를 만들 수 있는 팩터리를 포함 하는 내부 캐시를 채웁니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
ActivatableClass(  
   className  
);  
  
ActivatableClassWithFactory(  
   className,   
   factory  
);  
  
ActivatableClassWithFactoryEx(  
   className,   
   factory,   
   serverName  
);  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `className`  
 만들 클래스의 이름입니다.  
  
 `factory`  
 지정된 된 클래스의 인스턴스를 만드는 팩터리입니다.  
  
 `serverName`  
 모듈의 팩터리 하위 집합을 지정 하는 이름입니다.  
  
## <a name="remarks"></a>설명  
 사용 하지 않는 경우 클래식 com이 매크로 사용 하지 마십시오는 `#undef` 되도록 지시문은 **__WRL_WINRT_STRICT\_\_** 매크로 정의 제거 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [모듈 클래스](../windows/module-class.md)