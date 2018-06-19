---
title: 컴파일러 오류 C2410 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2410
dev_langs:
- C++
helpviewer_keywords:
- C2410
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9c2a2df0941130c4f2416806a05ce0378373eb4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33226450"
---
# <a name="compiler-error-c2410"></a>컴파일러 오류 C2410
'identifier': '컨텍스트'의 멤버 이름이 모호  
  
 식별자가 둘 이상의 구조 또는이 컨텍스트에서 공용 구조체의 멤버가 있습니다.  
  
 오류를 발생 시킨 피연산자에서 구조체 또는 공용 구조체 지정자를 사용 합니다. 구조체 또는 공용 구조체 지정자는 형식 식별자 `struct` 또는 `union` (한 `typedef` 이름이 나 구조체 또는 참조 되는 공용 구조체와 동일한 형식의 변수). 지정자는 피연산자를 사용 하는 첫 번째 멤버 선택 연산자 (.)의 왼쪽된 피연산자 이어야 합니다.