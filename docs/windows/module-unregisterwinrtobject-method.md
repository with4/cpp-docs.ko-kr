---
title: "Module::UnregisterWinRTObject 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::UnregisterWinRTObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UnregisterWinRTObject 메서드"
ms.assetid: 32334aa7-2293-40d2-9a89-4b02e2e31f3c
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Module::UnregisterWinRTObject 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다른 응용 프로그램이 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 개체에 연결할 수 없도록 하나 이상의 이 개체의 등록을 취소합니다.  
  
## <a name="syntax"></a>구문  
  
```  
virtual HRESULT UnregisterWinRTObject(  
   unsigned int,  
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie  
);  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cookie`  
 등록이 해지된 클래스 개체를 식별하는 값에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [모듈 클래스](../windows/module-class.md)