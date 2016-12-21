---
title: "QueryInterface | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "QueryInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "인터페이스, 가용성"
  - "인터페이스, 포인터"
  - "QueryInterface 메서드"
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# QueryInterface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

수 여 개체 기능을 제공 정적으로 \(그 전에\) 익스프레스 메커니즘 이지만 기본적인 COM 메커니즘을 사용 하는 것은  **IUnknown**  메서드 호출  [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521).  
  
 모든 인터페이스에서 파생 된  **IUnknown**, 모든 인터페이스의 구현 된 `QueryInterface`.  구현에 관계 없이이 메서드를 호출자에 게 포인터 원하는 인터페이스의 IID를 사용 하 여 개체를 쿼리 합니다.  개체는 해당 인터페이스를 지 원하는 경우 `QueryInterface` 도 호출 하는 동안 사용 하 여 인터페이스 포인터를 검색 `AddRef`.  그렇지 않으면 반환 된  **인터페이스** 오류 코드입니다.  
  
 준수 해야 하는 참고  [참조 횟수](../atl/reference-counting.md) 규칙을 항상.  호출 하는 경우  **릴리스** 인터페이스 포인터에서 참조 횟수가 0으로 감소 하 여 해당 포인터가 다시 사용해 서는 안 됩니다.  약한 개체 참조 해야 하는 경우가 있습니다 \(즉, 참조 횟수가 증가 하지 않고에 대 한 포인터를 해당 인터페이스 중 하나를 원하는 수 있습니다\), 있지만 호출 하 여이 작업을 수행 하려면 적합 `QueryInterface` 뒤  **릴리스**.  이러한 방식으로 가져온 포인터 잘못 되어 사용 하지 않아야 합니다.  이 보다 쉽게 때 드러납니다  [\_ATL\_DEBUG\_INTERFACES](../Topic/_ATL_DEBUG_INTERFACES.md) 이 매크로 정의 하므로 쉽게 찾기 참조 카운팅 버그의 정의입니다.  
  
## 참고 항목  
 [COM 소개](../atl/introduction-to-com.md)   
 [QueryInterface: Navigating in an Object](http://msdn.microsoft.com/library/windows/desktop/ms687230)