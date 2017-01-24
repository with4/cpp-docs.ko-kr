---
title: "Using a Template Library | Microsoft Docs"
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
  - "template libraries"
ms.assetid: 5e80ec6e-a61c-41ce-b34b-9a6252c46265
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Using a Template Library
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

매크로 처럼 템플릿입니다.  때 매크로, 템플릿은 호출 \(적절 한 매개 변수 대체 사용\) 확장에 작성 한 코드를 발생 합니다.  그러나 템플릿 매개 변수로 전달 하는 형식을 기반으로 새 클래스를 만들 수 있도록 하려면이 보다 더 이동 합니다.  이러한 새 클래스는 템플릿 코드에 표시 된 작업을 수행 하는 형식 안전적인 방법을 구현 합니다.  
  
 ATL과 같은 템플릿 라이브러리 들만 소스 코드 \(또는 소스 코드를 약간, 런타임 지원\) 일반적으로 제공 되는 기존의 C\+\+ 클래스 라이브러리에서 다르고 성격에 기본적으로 또는 반드시 계층 구조가 아닙니다.  원하는 기능을 얻을 수 있는 클래스에서 파생 하지 않고 템플릿에서 클래스를 인스턴스화합니다.  
  
## 참고 항목  
 [ATL 소개](../atl/introduction-to-atl.md)