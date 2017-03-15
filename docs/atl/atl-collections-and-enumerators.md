---
title: "ATL 컬렉션 및 열거자 | Microsoft Docs"
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
  - "컬렉션 인터페이스"
  - "컬렉션, ATL 클래스"
  - "열거자 인터페이스"
  - "열거자, ATL 클래스"
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ATL 컬렉션 및 열거자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A `collection` \(원시 데이터 또는 다른 개체\) 데이터 항목의 그룹을 액세스할 수 있는 인터페이스를 제공 하는 COM 개체입니다.  그룹 개체에 액세스를 제공 하 라고에 대 한 표준을 따르는 인터페이스는  *컬렉션 인터페이스*.  
  
 최소한 컬렉션 인터페이스를 제공 해야는  **수** 컬렉션의 항목 개수를 반환 하는 속성은  **항목** 인덱스를 기준으로 컬렉션에서 항목을 반환 하는 속성 a `_NewEnum` 컬렉션에 대 한 열거자를 반환 하는 속성.  컬렉션 인터페이스를 선택적으로 제공할 수 있습니다  **추가** 및  **제거** 항목을 컬렉션에서 삭제 또는 삽입 될 수 있도록 하는 메서드 a  **일반** 모든 항목을 제거 하는 방법.  
  
 `enumerator` 컬렉션에 있는 항목을 반복에 대 한 인터페이스를 제공 하는 COM 개체입니다.  열거자 인터페이스에 필요한 네 개의 메서드를 통해 컬렉션의 요소를 직렬 액세스를 제공 합니다: `Next`,  **건너뛰기**,  **재설정**, 및 `Clone`.  
  
 전형적인 \(하지만 완전히 가상의\)에 대 한 읽기에서 열거자 인터페이스에 자세히 알아볼 수  [IEnumXXXX](https://msdn.microsoft.com/en-us/library/ms680089.aspx) 인터페이스.  
  
## 단원 내용  
 [ATL 컬렉션 및 열거자 클래스](../atl/atl-collection-and-enumerator-classes.md)  
 간단 하 게 설명 하 고 연결 하는 데 도움이 되는 ATL 클래스에 컬렉션 및 열거자 구현 제공 합니다.  
  
 [컬렉션 및 열거자 인터페이스 디자인 원칙](../atl/design-principles-for-collection-and-enumerator-interfaces.md)  
 각 인터페이스 형식은 다른 디자인 원리에 설명 합니다.  
  
 [STL 기반 컬렉션을 구현](../atl/implementing-an-stl-based-collection.md)  
 표준 템플릿 라이브러리 STL 기반 컬렉션의 구현을 통해 안내 확장된 예입니다.  
  
## 관련 단원  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 액티브 템플릿 라이브러리를 사용 하 여 프로그래밍 하는 방법에 개념 항목에 대 한 링크를 제공 합니다.  
  
 [ATLCollections 샘플](../top/visual-cpp-samples.md)  
 사용 하는 방법을 보여 주는 샘플 `ICollectionOnSTLImpl` 및 `CComEnumOnSTL`, 및 사용자 지정 복사 정책 클래스의 구현입니다.  
  
## 참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)