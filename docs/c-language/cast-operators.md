---
title: "캐스트 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- cast operators
- type casts, operators
- operators [C++], cast
- type conversion, cast operators
ms.assetid: 43b90bbd-39ef-43e6-ae5d-e8a67a01de40
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8e607d3e1d02a985225f1ae41be66200ecf754ff
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="cast-operators"></a>캐스트 연산자
형식 캐스팅은 특정 상황에서의 개체 형식에 대한 명시적 변환을 위한 메서드를 제공합니다.  
  
## <a name="syntax"></a>구문  
 *cast-expression*:  
 *unary-expression*  
  
 **(**  *type-name*  **)**  *cast-expression*  
  
 형식 캐스팅이 만들어지면 컴파일러에서 *cast-expression*을 *type-name* 형식으로 처리합니다. 모든 스칼라 형식의 개체로 또는 다른 모든 스칼라 형식에서 변환하는 데 캐스트를 사용할 수 있습니다. [할당 변환](../c-language/assignment-conversions.md)에 나와 있는 대로 명시적 형식 캐스팅은 암시적 변환 결과를 확인하는 동일한 규칙으로 제한됩니다. 캐스팅에 대한 추가 제한은 특정 형식의 실제 크기 또는 표현에서 발생할 수 있습니다. 정수 계열 형식의 실제 크기에 대한 자세한 내용은 [기본 형식 저장](../c-language/storage-of-basic-types.md)을 참조하세요. 형식 캐스팅에 대한 자세한 내용은 [형식 캐스팅 변환](../c-language/type-cast-conversions.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [캐스트 연산자: ()](../cpp/cast-operator-parens.md)