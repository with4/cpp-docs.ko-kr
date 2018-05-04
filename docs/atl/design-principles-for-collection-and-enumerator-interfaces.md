---
title: 컬렉션 및 열거자 인터페이스 (ATL) 디자인 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enumerator interfaces
- collection interfaces
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 05649cce0e80af6f54327545cef7b663d69babf9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>컬렉션 및 열거자 인터페이스에 대 한 디자인 원칙
각 유형의 인터페이스 뒤에 있는 다른 디자인 원칙 가지가 있습니다.  
  
-   컬렉션 인터페이스는 제공 *임의* 에 대 한 액세스는 *단일* 를 통해 컬렉션 항목에에서는 **항목** 메서드를 컬렉션에 있는 항목 수를 알 수 있습니다 통해는 **Count** 속성을 종종 클라이언트 항목을 추가 및 제거할 수 있습니다.  
  
-   열거자 인터페이스는 제공 *직렬* 에 대 한 액세스 *여러* 컬렉션에서 항목을 클라이언트 (중지 될 때까지 열거자 반환 컬렉션에 있는 항목 수를 검색 하도록 허용 하지 않습니다 항목의 경우), 추가 또는 제거 항목을 제공 하지 않습니다.  
  
 인터페이스의 각 유형에 컬렉션의 요소에 대 한 액세스를 제공 하는 다른 역할을 수행 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컬렉션 및 열거자](../atl/atl-collections-and-enumerators.md)

