---
title: "ATL 연결 지점 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, 연결 지점"
  - "연결 지점[C++], 연결 지점 정보"
  - "연결, 연결 지점"
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ATL 연결 지점
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

연결 가능 개체는 송신 인터페이스를 지원합니다.  송신 인터페이스에서는 개체가 클라이언트와 통신할 수 있습니다.  연결 가능 개체는 각 송신 인터페이스에 대해 연결 지점을 노출합니다.  각 송신 인터페이스는 싱크라는 개체에서 클라이언트에 의해 구현됩니다.  
  
 ![연결 지점](../atl/media/vc2zw31.png "vc2ZW31")  
  
 각 연결 지점은 [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318) 인터페이스를 지원합니다.  연결 가능 개체는 [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857) 인터페이스를 통해 클라이언트에 해당 연결 지점을 노출합니다.  
  
## 단원 내용  
 [ATL 연결 지점 클래스](../atl/atl-connection-point-classes.md)  
 연결 지점을 지원하는 ATL 클래스에 대해 간략하게 설명합니다.  
  
 [개체에 연결 지점 추가](../atl/adding-connection-points-to-an-object.md)  
 개체에 연결 지점을 추가하는 데 사용되는 단계에 대해 설명합니다.  
  
 [ATL 연결 지점 예제](../atl/atl-connection-point-example.md)  
 연결 지점 선언 예제를 제공합니다.  
  
## 관련 단원  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 액티브 템플릿 라이브러리를 사용하여 프로그래밍하는 방법에 대한 개념 항목의 링크를 제공합니다.  
  
## 참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)