---
title: "int 형식 | Microsoft Docs"
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
helpviewer_keywords:
- int data type
- type int
- portability [C++], type int
- signed integers
ms.assetid: 0067ce9a-281e-491a-ae63-632952981e13
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 921cd8a91ecc1fe3cc746c23a79928fef9142ecc
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="type-int"></a>int 형식
signed/unsigned `int` 항목의 크기는 특정 시스템의 표준 정수 크기입니다. 예를 들어, 16비트 운영 체제에서 `int` 형식은 보통 16비트 또는 2바이트입니다. 32비트 운영 체제에서 `int` 형식은 보통 32비트 또는 4바이트입니다. 따라서, 대상 환경에 따라 `int` 형식은 `short int` 또는 **long int** 형식과 동일하며 `unsigned int` 형식은 **unsigned short** 또는 `unsigned long` 형식과 동일합니다. 특별한 지정이 없는 한 `int` 형식은 모두 부호 있는 값을 표시합니다.  
  
 형식 지정자 `int` 및 `unsigned int`(또는 단순히 `unsigned`)는 C 언어의 특정한 기능(예: `enum` 형식)을 정의합니다. 이러한 경우 특정 구현에 대한 `int` 정의 및 unsigned int로 실제 저장소가 결정됩니다.  
  
 **Microsoft 전용**  
  
 부호 있는 정수는 2의 보수 형식으로 표시됩니다. 최상위 비트는 음수에 대해서는 부호 1을, 양수와 0에 대해서는 0을 가집니다. 값의 범위는 헤더 파일 LIMITS.H의 [C++ 정수 제한](../c-language/cpp-integer-limits.md)에 있습니다.  
  
 **Microsoft 전용 종료**  
  
> [!NOTE]
>  int 및 unsigned int 형식 지정자는 특정 컴퓨터가 해당 시스템에 가장 효율적인 방식으로 대한 정수 값을 처리하도록 하기 때문에 C 프로그램에서 널리 사용됩니다. 그러나 int 및 unsigned int 형식은 크기가 매우 다양하므로 특정 int 크기에 따라 프로그램이 다른 컴퓨터에 이식될 수 있습니다. 프로그램을 더욱 이식 가능하도록 하려면, 하드 코딩된 데이터 크기 대신 sizeof 연산자([sizeof 연산자](../c-language/sizeof-operator-c.md) 참조)를 가진 식을 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [기본 형식의 저장소](../c-language/storage-of-basic-types.md)
