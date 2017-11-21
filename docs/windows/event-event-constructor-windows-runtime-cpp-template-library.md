---
title: "Event:: event 생성자 (Windows 런타임 c + + 템플릿 라이브러리) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Event::Event
dev_langs: C++
ms.assetid: 21495297-9612-4095-9256-16e168cc0021
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 88fafd4bb345d8e70f84aa87c04592e91703b5c2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="eventevent-constructor-windows-runtime-c-template-library"></a>Event::Event 생성자(Windows Runtime C++ 템플릿 라이브러리)
이벤트 클래스의 새 인스턴스를 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
explicit Event(  
   HANDLE h = HandleT::Traits::GetInvalidValue()  
);  
WRL_NOTHROW Event(  
   _Inout_ Event&& h  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `h`  
 이벤트에 대한 핸들. 기본적으로 `h`는 `nullptr`로 초기화됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [Event 클래스(Windows Runtime C++ 템플릿 라이브러리)](../windows/event-class-windows-runtime-cpp-template-library.md)