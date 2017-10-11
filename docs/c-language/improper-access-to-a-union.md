---
title: "공용 구조체에 대한 부적절한 액세스 | Microsoft Docs"
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
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 54eeffebcc20846666c6ebb6a2951f8d55a5b8c5
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="improper-access-to-a-union"></a>공용 구조체에 대한 부적절한 액세스
**ANSI 3.3.2.3** 다른 형식의 멤버를 사용하여 공용 구조체 개체의 멤버에 액세스합니다.  
  
 두 형식의 공용 구조체가 선언되고 값이 한 개 저장되지만 다른 형식으로 공용 구조체에 액세스하는 경우 결과를 신뢰할 수 없습니다.  
  
 예를 들어, **float** 및 `int`의 공용 구조체가 선언됩니다. **float** 값이 저장되지만 나중에 `int`로 값에 액세스합니다. 그러면 **float** 값의 내부 저장소에 따라 값이 결정됩니다. 정수 값은 신뢰할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 공용 구조체, 열거형 및 비트 필드](../c-language/structures-unions-enumerations-and-bit-fields.md)
