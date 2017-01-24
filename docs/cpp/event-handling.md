---
title: "이벤트 처리 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "특성[C++], 이벤트 처리"
  - "이벤트 처리, Visual C++"
  - "내장 함수, 이벤트 처리"
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 이벤트 처리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기본적으로 COM 클래스\(대개 ATL 클래스나 [coclass](../windows/coclass.md) 특성을 사용하여 COM 개체를 구현하는 C\+\+ 클래스\)에 대해 이벤트 처리가 지원됩니다.  자세한 내용은 [COM에서 이벤트 처리](../cpp/event-handling-in-com.md)를 참조하십시오.  
  
 네이티브 C\+\+ 클래스\(COM 개체를 구현하지 않는 C\+\+ 클래스\)에 대해서도 이벤트 처리가 지원되지만 이 지원은 더 이상 사용되지 않으며 향후 릴리스에서 제거됩니다.  자세한 내용은 [네이티브 C\+\+에서 이벤트 처리](../cpp/event-handling-in-native-cpp.md)를 참조하십시오.  
  
 이벤트 처리는 단일 및 다중 스레드 사용을 지원하며 동시 다중 스레드 액세스로부터 데이터를 보호합니다.  이벤트 처리를 사용하면 이벤트 소스나 수신기 클래스에서 하위 클래스를 파생시키고 파생된 클래스에서 확장된 이벤트 소싱\/수신을 지원할 수 있습니다.  
  
 Visual C\+\+에는 이벤트와 이벤트 처리기를 선언하는 특성과 키워드가 있습니다.  CLR 프로그램과 네이티브 C\+\+ 프로그램에서 이벤트 특성과 키워드를 사용할 수 있습니다.  
  
|항목|설명|  
|--------|--------|  
|[event\_source](../windows/event-source.md)|이벤트 소스를 만듭니다.|  
|[event\_receiver](../windows/event-receiver.md)|이벤트 수신기\(싱크\)를 만듭니다.|  
|[\_\_event](../cpp/event.md)|이벤트를 선언합니다.|  
|[\_\_raise](../cpp/raise.md)|이벤트의 호출 사이트를 강조합니다.|  
|[\_\_hook](../cpp/hook.md)|처리기 메서드를 이벤트와 연결합니다.|  
|[\_\_unhook](../cpp/unhook.md)|처리기 메서드를 이벤트에서 분리합니다.|  
  
## 참고 항목  
 [C\+\+ 언어 참조](../cpp/cpp-language-reference.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [Event Handling Samples](http://msdn.microsoft.com/ko-kr/cc0287d4-f92b-4da5-85fc-a0f186e16424)