---
title: ATL 컬렉션 및 열거자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enumerator interfaces
- collections, ATL classes
- enumerators, ATL classes
- collection interfaces
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 537d7e8b7264beddc68805ab8b8dec2ce7883859
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="atl-collections-and-enumerators"></a>ATL 컬렉션 및 열거자
A `collection` (원시 데이터 또는 기타 개체) 데이터 항목의 그룹에 대 한 액세스를 허용 하는 인터페이스를 제공 하는 COM 개체입니다. 개체의 그룹에 대 한 액세스를 제공 하 라고에 대 한 표준을 따르는 인터페이스는 *컬렉션 인터페이스*합니다.  
  
 여기에 최소한 컬렉션 인터페이스를 제공 해야는 **Count** 속성 컬렉션에서 항목의 수를 반환 하는 **항목** 인덱스를 기반으로 컬렉션에서 항목을 반환 하는 속성 및 `_NewEnum` 컬렉션에 대 한 열거자를 반환 하는 속성입니다. 컬렉션 인터페이스를 제공할 수 필요에 따라 **추가** 및 **제거** 에 삽입 또는 삭제 컬렉션에서 항목을 허용 하도록 메서드 및 **지우기** 제거 하는 메서드 모든 항목입니다.  
  
 `enumerator` 컬렉션에서 항목을 반복 하는 인터페이스를 제공 하는 COM 개체입니다. 4 개의 필요한 메서드를 통해 컬렉션의 요소에 대 한 직렬 액세스를 제공 하는 열거자 인터페이스: `Next`, **Skip**, **재설정**, 및 `Clone`합니다.  
  
 읽어 전형적인 (않음 완전히 가상의)에 대 한 자세한 내용은 열거자 인터페이스에 대 한 [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx) 인터페이스입니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [ATL 컬렉션 및 열거자 클래스](../atl/atl-collection-and-enumerator-classes.md)  
 간략하게 설명 하 고 컬렉션 및 열거자를 구현 하는 데 도움이 되는 ATL 클래스에 대 한 링크를 제공 합니다.  
  
 [컬렉션 및 열거자 인터페이스에 대한 디자인 원칙](../atl/design-principles-for-collection-and-enumerator-interfaces.md)  
 각 유형의 인터페이스 뒤에 있는 다른 디자인 원칙을 설명 합니다.  
  
 [C++ 표준 라이브러리 기반 컬렉션 구현](../atl/implementing-an-stl-based-collection.md)  
 C + + 표준 라이브러리 기반 컬렉션의 구현 안내 하는 확장된 예제입니다.  
  
## <a name="related-sections"></a>관련 단원  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 액티브 템플릿 라이브러리를 사용하여 프로그래밍하는 방법에 대한 개념 항목의 링크를 제공합니다.  
  
 [ATLCollections 샘플](../visual-cpp-samples.md)  
 사용을 보여 주는 샘플 `ICollectionOnSTLImpl` 및 `CComEnumOnSTL`, 및 사용자 지정 복사본 정책 클래스의 구현입니다.  
  
## <a name="see-also"></a>참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)

