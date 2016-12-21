---
title: "Module::Create 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::Create"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Create 메서드"
ms.assetid: bfa97fd7-5226-4604-92a5-3b9697053e64
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::Create 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

모듈의 인스턴스를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
WRL_NOTHROW static Module& Create();  
template<  
   typename T  
>  
WRL_NOTHROW static Module& Create(  
   T callback  
);  
template<  
   typename T  
>  
WRL_NOTHROW static Module& Create(  
   _In_ T* object,  
   _In_ void (T::* method)()  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 모듈 형식입니다.  
  
 `callback`  
 모듈의 마지막 인스턴스 개체가 해제 될 때 호출 됩니다.  
  
 `object`  
  `object` 및 `method` 조합 하 여 매개 변수가 사용 됩니다. 마지막 가리키도록 인스턴스 개체는 모듈의 마지막 인스턴스 개체가 해제 될 때입니다.  
  
 `method`  
  `object` 및 `method` 조합 하 여 매개 변수가 사용 됩니다. 모듈의 마지막 인스턴스 개체가 해제 될 때 마지막 인스턴스 개체의 메서드를 가리킵니다.  
  
## <a name="return-value"></a>반환 값  
 모듈에 대 한 참조입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
[모듈 클래스](../windows/module-class.md)

 