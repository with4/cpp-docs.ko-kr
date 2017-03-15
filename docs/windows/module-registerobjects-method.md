---
title: "Module::RegisterObjects 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::RegisterObjects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RegisterObjects 메서드"
ms.assetid: db4077b7-068d-4534-aaa5-41b5444ccb49
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Module::RegisterObjects 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다른 응용 프로그램이 COM 또는 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 개체에 연결할 수 있도록 COM과 이 개체를 등록합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RegisterObjects(  
   ModuleBase* module,   
   const wchar_t* serverName);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `module`  
 COM 또는 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 개체의 배열입니다.  
  
 `serverName`  
 개체를 생성한 서버의 이름입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 시 S_OK이고, 그렇지 않으면 작업이 실패한 이유를 나타내는 HRESULT입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL
 
## <a name="see-also"></a>참고 항목
[모듈 클래스](../windows/module-class.md)