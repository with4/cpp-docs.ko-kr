---
title: 컴파일러 오류 C3398 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3398
dev_langs:
- C++
helpviewer_keywords:
- C3398
ms.assetid: 26f8c8a4-526f-415b-8047-155c5cd4f180
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b870479977bfb49ff39d5a15fe19fc700ed66b8e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33255833"
---
# <a name="compiler-error-c3398"></a>컴파일러 오류 C3398
'operator': 'function_signature'에서 'function_pointer'로 변환할 수 없습니다. 소스 식은 함수 기호여야 합니다.  
  
 [/clr](../../cpp/clrcall.md) 으로 컴파일할 때 **__clrcall**호출 규칙을 지정하지 않는 경우 컴파일러가 각 함수에 대한 두 진입점(주소), 즉 기본 진입점 및 관리되는 진입점을 생성합니다.  
  
 기본적으로 컴파일러에서 기본 진입점을 반환하지만 경우에 따라 관리되는 진입점이 필요합니다(예: 주소를 `__clrcall` 함수 포인터로 할당하는 경우). 컴파일러가 할당에서 관리되는 진입점을 안정적으로 선택하려면 오른쪽이 함수 기호여야 합니다.