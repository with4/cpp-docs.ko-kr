---
title: "컴파일러 오류 C3398 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3398
dev_langs:
- C++
helpviewer_keywords:
- C3398
ms.assetid: 26f8c8a4-526f-415b-8047-155c5cd4f180
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 54241a6e57bdfd8795d6f894a1410c1e6c90cf49
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3398"></a>컴파일러 오류 C3398
'operator': 'function_signature'에서 'function_pointer'로 변환할 수 없습니다. 소스 식은 함수 기호여야 합니다.  
  
 [/clr](../../cpp/clrcall.md) 으로 컴파일할 때 **__clrcall**호출 규칙을 지정하지 않는 경우 컴파일러가 각 함수에 대한 두 진입점(주소), 즉 기본 진입점 및 관리되는 진입점을 생성합니다.  
  
 기본적으로 컴파일러에서 기본 진입점을 반환하지만 경우에 따라 관리되는 진입점이 필요합니다(예: 주소를 `__clrcall` 함수 포인터로 할당하는 경우). 컴파일러가 할당에서 관리되는 진입점을 안정적으로 선택하려면 오른쪽이 함수 기호여야 합니다.
