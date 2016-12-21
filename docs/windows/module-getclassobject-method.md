---
title: "Module::GetClassObject 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::GetClassObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetClassObject 메서드"
ms.assetid: 95b0de1b-f728-4f96-9f44-f6ea71ce56e4
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::GetClassObject 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

클래스 팩터리의 캐시를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
 HRESULT GetClassObject(  
   REFCLSID clsid,  
   REFIID riid,  
   _Deref_out_ void **ppv,  
   wchar_t* serverName = nullptr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `clsid`  
 클래스 ID입니다.  
  
 `riid`  
 요청하는 인터페이스 ID입니다.  
  
 `ppv`  
 반환된 개체에 대한 포인터입니다.  
  
 `serverName`  
 `ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx` 또는 `ActivatableClass` 매크로에 지정된 서버 이름 또는 기본 서버 이름을 가져오는 `nullptr`입니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="remarks"></a>설명  
 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]가 아닌 COM에만 이 메서드를 사용합니다. 이 메서드는 IClassFactory 메서드만 노출합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [모듈 클래스](../windows/module-class.md)