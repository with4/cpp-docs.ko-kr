---
title: "Module:: module 생성자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::Module
dev_langs: C++
helpviewer_keywords: Module, constructor
ms.assetid: 5436fc74-61dc-41b6-81af-4f03177159aa
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 24e74bf30f932fa8029c64d27ce55dd2a75a99aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="modulemodule-constructor"></a>Module::Module 생성자
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
 [Module 클래스](../windows/module-class.md)