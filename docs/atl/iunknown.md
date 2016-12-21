---
title: "IUnknown | Microsoft Docs"
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
  - "IUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM 인터페이스, base interface"
  - "IUnknown interface"
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IUnknown
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)은 모든 COM 인터페이스의 기본 인터페이스입니다.  이 인터페이스는 [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521), [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) 및 [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317)의 세 가지 메서드를 정의합니다.  [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)를 사용하면 인터페이스 사용자가 다른 인터페이스에 포인터 개체를 요청할 수 있습니다.  [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) 및 [릴리스](http://msdn.microsoft.com/library/windows/desktop/ms682317)는 인터페이스의 참조 횟수를 구현합니다.  
  
## 참고 항목  
 [COM 소개](../atl/introduction-to-com.md)   
 [IUnknown and Interface Inheritance](http://msdn.microsoft.com/library/windows/desktop/ms692713)