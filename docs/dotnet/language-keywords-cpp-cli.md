---
title: "언어 키워드(C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "키워드[C++]"
ms.assetid: 021013b2-70ac-4df9-aa77-4af1c67a1a67
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 언어 키워드(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 몇 가지 언어 키워드가 Managed Extensions for C\+\+와 다르게 변경되었습니다.  
  
 새로운 [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] 구문에서는 모든 키워드에 접두사로 사용하던 두 개의 밑줄을 더 이상 사용하지 않습니다. 예외적으로 `__identifier`의 경우는 밑줄이 계속 사용됩니다.  예를 들어, 속성은 이제 `__property`가 아닌 `property`로 선언됩니다.  
  
 Managed Extensions에서 두 개의 밑줄을 접두사로 사용한 데는 크게 두 가지 이유가 있습니다.  
  
-   이 방법을 사용하면 ISO\-C\+\+ 표준을 준수하면서 로컬 확장을 제공할 수 있습니다.  Managed Extensions를 디자인할 때의 주된 목표는 새로운 키워드나 토큰 등과 같이 표준 언어와 호환되지 않는 요소를 배제하는 데 있었습니다.  이는 관리되는 참조 형식의 개체 선언에 대한 포인터 구문을 선택할 때 중요한 기준으로 사용되었습니다.  
  
-   표준 준수라는 측면 이외에도 두 개의 밑줄을 사용하면 대부분의 경우 언어 사용자의 기존 코드베이스를 침해하지 않는다는 이점이 있습니다.  이는 Managed Extensions 디자인의 두 번째 주된 목표였습니다.  
  
 Microsoft의 방침은 두 개의 밑줄을 제거하지 않고 표준을 계속 준수하는 것입니다.  그러나 CLR 동적 개체 모델을 지원하면 새롭고 강력한 프로그래밍 패러다임이 제공됩니다.  이 새로운 패러다임을 지원하려면 자체적인 고급 키워드 및 토큰을 사용해야 합니다.  결국 이 새 패러다임을 완벽하게 표현하면서도 이를 통합하고 표준 언어를 지원할 수 있는 방법을 모색하기 시작했습니다.  새로운 구문 디자인을 통해 이러한 서로 다른 두 가지 개체 모델을 지원하는 최상의 프로그래밍 환경이 제공됩니다.  
  
 또한 이러한 새 언어 키워드가 사용자의 기존 코드베이스를 가능한 한 침해하지 않도록 하는 데도 많은 노력을 기울였습니다.  이를 위해 컨텍스트 키워드와 공백이 포함된 키워드를 도입했습니다.  새로운 언어 구문을 직접 살펴보기 전에 키워드의 이러한 두 가지 특징을 이해할 필요가 있습니다.  
  
 컨텍스트 키워드는 특정 프로그램 컨텍스트 내에서 특별한 의미를 지닙니다.  예를 들어, 일반적인 프로그램에서 `sealed`는 일반 한정자로 취급됩니다.  그러나 이를 관리되는 참조 클래스 형식의 선언 부분 안에서 사용하면 해당 클래스 선언의 컨텍스트 내에서 키워드로 취급됩니다.  이렇게 하면 언어에 새 키워드를 도입함으로써 발생할 수 있는 파급 효과를 최소화할 수 있습니다. 이는 기존의 코드베이스를 사용하여 작업하는 경우 매우 중요한 부분이 될 수 있습니다.  동시에 이를 통해 Managed Extensions에서는 사용할 수 없는 고급 언어 기능을 추가로 활용할 수 있습니다.  `sealed`를 사용하는 방법에 대한 예제를 보려면 [관리되는 클래스 형식 선언](../dotnet/declaration-of-a-managed-class-type.md)을 참조하십시오.  
  
 `value class`와 같이 공백이 포함된 키워드는 컨텍스트 키워드의 특수한 경우입니다.  이는 기존 키워드와 컨텍스트 한정자가 공백으로 구분된 쌍입니다.  이 쌍은 별개의 두 키워드가 아니라 하나의 단위로 취급됩니다.  
  
## 참고 항목  
 [C\+\+\/CLI 마이그레이션 입문](../dotnet/cpp-cli-migration-primer.md)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)