---
title: 'Module:: module 생성자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Module
dev_langs:
- C++
helpviewer_keywords:
- Module, constructor
ms.assetid: 5436fc74-61dc-41b6-81af-4f03177159aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d63b90bb3622129589fca41c029f548a07ec21b8
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017658"
---
# <a name="modulemodule-constructor"></a>Module::Module 생성자
새 인스턴스를 초기화 합니다 **모듈** 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
Module();  
```  
  
## <a name="remarks"></a>설명  
 이 생성자는 보호 되 고 사용 하 여 호출할 수 없습니다는 **새** 키워드입니다. 대신, 호출 [module:: getmodule 메서드](../windows/module-getmodule-method.md) 하거나 [module:: create 메서드](../windows/module-create-method.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [Module 클래스](../windows/module-class.md)