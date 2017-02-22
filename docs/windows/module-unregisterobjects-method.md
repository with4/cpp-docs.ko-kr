---
title: "Module::UnregisterObjects 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::UnregisterObjects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UnregisterObjects 메서드"
ms.assetid: 3d8119a7-991d-45e9-b8c5-ed36c0be0332
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Module::UnregisterObjects 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다른 응용 프로그램에서 지정된 모듈의 개체에 연결할 수 없도록 이 개체의 등록을 취소합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT UnregisterObjects(  
   ModuleBase* module,  
   const wchar_t* serverName);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `module`  
 모듈에 대한 포인터입니다.  
  
 `serverName`  
 이 작업으로 영향을 받는 개체의 하위 집합을 지정하는 정규화 이름입니다.  
  
## <a name="return-value"></a>반환 값  
 이 작업에 성공하면 S_OK이고, 그렇지 않으면 이 작업에 실패한 이유를 나타내는 HRESULT 오류가 발생합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [모듈 클래스](../windows/module-class.md)