---
title: "이벤트 처리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], event handling
- intrinsic functions [C++], event handling
- event handling [C++], Visual C++
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: a05886ade7ff9369dfae29accf7c47d1890998b8
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="event-handling"></a>이벤트 처리
이벤트 처리는 기본적으로 COM 클래스에 대 한 지원 (대개 ATL 클래스를 사용 하 여 COM 개체를 구현 하는 c + + 클래스 또는 [coclass](../windows/coclass.md) 특성).  자세한 내용은 참조 [COM에서 이벤트 처리](../cpp/event-handling-in-com.md)합니다.  
  
 네이티브 C++ 클래스(COM 개체를 구현하지 않는 C++ 클래스)에 대해서도 이벤트 처리가 지원되지만 이 지원은 더 이상 사용되지 않으며 향후 릴리스에서 제거됩니다.  자세한 내용은 참조 [네이티브 c + +에서 이벤트 처리](../cpp/event-handling-in-native-cpp.md)합니다.  
  
 이벤트 처리는 단일 및 다중 스레드 사용을 지원하며 동시 다중 스레드 액세스로부터 데이터를 보호합니다. 이벤트 처리를 사용하면 이벤트 소스나 수신기 클래스에서 하위 클래스를 파생시키고 파생된 클래스에서 확장된 이벤트 소싱/수신을 지원할 수 있습니다.  
  
 Visual C++에는 이벤트와 이벤트 처리기를 선언하는 특성과 키워드가 있습니다. CLR 프로그램과 네이티브 C++ 프로그램에서 이벤트 특성과 키워드를 사용할 수 있습니다.  
  
|항목|설명|  
|-----------|-----------------|  
|[event_source](../windows/event-source.md)|이벤트 소스를 만듭니다.|  
|[event_receiver](../windows/event-receiver.md)|이벤트 수신기(싱크)를 만듭니다.|  
|[__event](../cpp/event.md)|이벤트를 선언합니다.|  
|[__raise](../cpp/raise.md)|이벤트의 호출 사이트를 강조합니다.|  
|[__hook](../cpp/hook.md)|처리기 메서드를 이벤트와 연결합니다.|  
|[__unhook](../cpp/unhook.md)|처리기 메서드를 이벤트에서 분리합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [C + + 언어 참조](../cpp/cpp-language-reference.md)   
 [키워드](../cpp/keywords-cpp.md)   
 [이벤트 처리 샘플](http://msdn.microsoft.com/en-us/cc0287d4-f92b-4da5-85fc-a0f186e16424)
