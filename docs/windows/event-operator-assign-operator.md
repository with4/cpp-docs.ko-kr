---
title: "Event:: operator = 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: d8fe9820-8856-4899-9553-56226bdc4945
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: de46ba0d6749120fc391b4a55527904ed1321ad9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="eventoperator-operator"></a>Event::operator= 연산자
현재 이벤트 인스턴스를 지정된 이벤트 참조를 할당합니다.  
  
## <a name="syntax"></a>구문  
  
```  
WRL_NOTHROW Event& operator=(  
   _Inout_ Event&& h  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `h`  
 Event 인스턴스에 대한 rvalue 참조입니다.  
  
## <a name="return-value"></a>반환 값  
 현재 Event 인스턴스에 대한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [Event 클래스(Windows Runtime C++ 템플릿 라이브러리)](../windows/event-class-windows-runtime-cpp-template-library.md)