---
title: "컬렉션 및 열거자 인터페이스 (ATL) 디자인 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- enumerator interfaces
- collection interfaces
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8709274e1b95816dee01b4457993521dde5d5213
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>컬렉션 및 열거자 인터페이스에 대 한 디자인 원칙
각 유형의 인터페이스 뒤에 있는 다른 디자인 원칙 가지가 있습니다.  
  
-   컬렉션 인터페이스는 제공 *임의* 에 대 한 액세스는 *단일* 를 통해 컬렉션 항목에에서는 **항목** 메서드를 컬렉션에 있는 항목 수를 알 수 있습니다 통해는 **Count** 속성을 종종 클라이언트 항목을 추가 및 제거할 수 있습니다.  
  
-   열거자 인터페이스는 제공 *직렬* 에 대 한 액세스 *여러* 컬렉션에서 항목을 클라이언트 (중지 될 때까지 열거자 반환 컬렉션에 있는 항목 수를 검색 하도록 허용 하지 않습니다 항목의 경우), 추가 또는 제거 항목을 제공 하지 않습니다.  
  
 인터페이스의 각 유형에 컬렉션의 요소에 대 한 액세스를 제공 하는 다른 역할을 수행 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컬렉션 및 열거자](../atl/atl-collections-and-enumerators.md)

