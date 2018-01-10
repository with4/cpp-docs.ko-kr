---
title: "Roinitializewrapper:: Roinitializewrapper 생성자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper
dev_langs: C++
ms.assetid: c6f7fb07-14af-4574-9135-cea164607f30
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f5af6ca55445a5b8ed17a685cc0a81e8058a0eb2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="roinitializewrapperroinitializewrapper-constructor"></a>RoInitializeWrapper::RoInitializeWrapper 생성자
RoInitializeWrapper 클래스의 새 인스턴스를 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
RoInitializeWrapper(   RO_INIT_TYPE flags)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `flags`  
 Windows 런타임에서 제공 하는 지원을 지정 하는 RO_INIT_TYPE 열거 중 하나입니다.  
  
## <a name="remarks"></a>설명  
 RoInitializeWrapper 클래스 호출 Windows::Foundation::Initialize (*플래그*).  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HandleT 클래스](../windows/handlet-class.md)