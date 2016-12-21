---
title: "Module::Module 생성자 | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::Module"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "모듈, 생성자"
ms.assetid: 5436fc74-61dc-41b6-81af-4f03177159aa
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::Module 생성자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Module 클래스의 새 인스턴스를 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Module();  
```  
  
## <a name="remarks"></a>설명  
 이 생성자가 보호되고 `new` 키워드로 호출할 수 없습니다. 대신, 호출 [module:: getmodule 메서드](../windows/module-getmodule-method.md) 또는 [module:: create 메서드](../windows/module-create-method.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [모듈 클래스](../windows/module-class.md)