---
title: "컴파일러 오류 C3398 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 66bd229369456da18d8bed60b25b6e6b07e03f27
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3398"></a>컴파일러 오류 C3398
'operator': 'function_signature'에서 'function_pointer'로 변환할 수 없습니다. 소스 식은 함수 기호여야 합니다.  
  
 경우는 [__clrcall](../../cpp/clrcall.md) 로 컴파일할 때 호출 규칙 지정 하지 않으면 **/clr**, 컴파일러에서는 두 진입점 (주소) 각 함수, 기본 진입점 및 관리 되는 진입점에 대 한 오류가 발생 합니다.  
  
 기본적으로 컴파일러에서 기본 진입점을 반환하지만 경우에 따라 관리되는 진입점이 필요합니다(예: 주소를 `__clrcall` 함수 포인터로 할당하는 경우). 컴파일러가 할당에서 관리되는 진입점을 안정적으로 선택하려면 오른쪽이 함수 기호여야 합니다.
