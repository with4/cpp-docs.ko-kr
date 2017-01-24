---
title: "Module::GetActivationFactory 메서드 | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::GetActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetActivationFactory 메서드"
ms.assetid: 59da8844-072e-414b-b89c-1db1cc4fd81d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::GetActivationFactory 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

모듈에 대한 활성화 팩터리를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
WRL_NOTHROW HRESULT GetActivationFactory(  
   _In_ HSTRING pActivatibleClassId,  
   _Deref_out_ IActivationFactory **ppIFactory,  
   wchar_t* serverName = nullptr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pActivatibleClassId`  
 런타임 클래스의 IID입니다.  
  
 `ppIFactory`  
 지정된 런타임 클래스에 대한 IActivationFactory입니다.  
  
 `serverName`  
 현재 모듈의 클래스 팩터리 하위 집합 이름입니다. 사용 되는 서버 이름을 지정는 [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) 매크로 지정 하거나 `nullptr` 기본 서버 이름을 가져올 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 GetActivationFactory에서 반환된 HRESULT입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
[모듈 클래스](../windows/module-class.md)
 [ActivatableClass 매크로](../windows/activatableclass-macros.md)