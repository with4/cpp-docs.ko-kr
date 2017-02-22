---
title: "TerminateMap 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::TerminateMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TerminateMap 함수"
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# TerminateMap 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
inline bool TerminateMap(  
   _In_ ModuleBase *module,   
   _In_opt_z_ const wchar_t *serverName,   
    bool forceTerminate) throw()  
```  
  
## <a name="parameters"></a>매개 변수  
 `module`  
 A [모듈](../windows/module-class.md)합니다.  
  
 `serverName`  
 매개 변수에 의해 지정 된 모듈의 클래스 팩터리 하위 집합의 이름을 `module`합니다.  
  
 `forceTerminate`  
 `true` 에 관계 없이 팩터리 클래스를 종료 하려면 활성 상태는 `false` 모든 팩터리 활성 상태 이면 클래스 팩터리를 종료 하지에 있습니다.  
  
## <a name="return-value"></a>반환 값  
 `true` 클래스는 모든 팩터리가 종료 되었습니다; 하는 경우 그렇지 않으면 `false`합니다.  
  
## <a name="remarks"></a>설명  
 지정된 된 모듈의 클래스 팩터리를 종료합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임 스페이스:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임 스페이스](../windows/microsoft-wrl-details-namespace.md)