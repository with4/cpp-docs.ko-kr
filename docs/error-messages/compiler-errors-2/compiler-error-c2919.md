---
title: 컴파일러 오류 C2919 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2919
dev_langs:
- C++
helpviewer_keywords:
- C2919
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5e2eb2a32f1a906814f5b347ba1ebf13eba71ff
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2919"></a>컴파일러 오류 C2919
'type': WinRT 형식의 게시된 표면에서는 연산자를 사용할 수 없습니다.  
  
 Windows 런타임 형식 시스템은 형식의 게시된 표면에서 연산자 멤버 함수를 지원하지 않습니다. 일부 언어에서 연산자 멤버 함수를 사용하지 않기 때문입니다. 동일한 클래스 또는 컴파일 단위의 C++ 코드에서 호출할 수 있는 private 또는 internal 연산자 멤버 함수를 만들 수 있습니다.  
  
 이 문제를 해결하려면 공용 인터페이스에서 연산자 멤버 함수를 제거하거나 명명된 멤버 함수로 변경합니다. 예를 들어 `operator==` 대신 멤버 함수 `Equals`의 이름을 지정합니다.