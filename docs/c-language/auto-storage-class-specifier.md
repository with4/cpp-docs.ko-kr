---
title: "auto 저장소 클래스 지정자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 8e73f57e-aa92-4e41-91ea-5c8ad2a2b332
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 5e80f6057a26ba7655df0a04d75dcaec2c4856ed
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="auto-storage-class-specifier"></a>자동 저장소 클래스 지정자
**auto** 저장소 클래스 지정자는 로컬 수명을 가진 변수인 자동 변수를 선언합니다. **auto** 변수는 자신이 선언된 블록에서만 표시됩니다. [초기화](../c-language/initialization.md)에서 설명한 대로 **auto** 변수 선언에는 이니셜라이저를 포함할 수 있습니다. **auto** 저장소 클래스가 있는 변수는 자동으로 초기화되지 않으므로 이 변수를 선언할 때 명시적으로 초기화하거나 블록에 있는 문에서 이 변수에 초기 값을 할당해야 합니다. 초기화되지 않은 **auto** 변수의 값이 정의되지 않았습니다. 이니셜라이저가 제공될 경우 **auto** 또는 **register** 저장소 클래스의 지역 변수가 범위에 도달할 때마다 초기화됩니다.  
  
 외부 또는 **static** 항목의 주소를 사용하여 내부 **static** 변수(로컬 또는 블록 범위가 있는 정적 변수)를 초기화할 수 있지만 **auto** 항목 주소가 상수가 아니므로 다른 **auto** 항목의 주소를 사용하여 초기화할 수는 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [auto 키워드](../cpp/auto-keyword.md)
