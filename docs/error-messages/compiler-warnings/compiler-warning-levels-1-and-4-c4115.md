---
title: 컴파일러 경고 (수준 1 및 4) C4115 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4115
dev_langs:
- C++
helpviewer_keywords:
- C4115
ms.assetid: f3f94e72-fc49-4d09-b3e7-23d68e61152f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2edfdc84ee38e20f7193d720eab0ccb58d30790b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33294195"
---
# <a name="compiler-warning-levels-1-and-4-c4115"></a>컴파일러 경고(수준 1 및 4) C4115
'type': 괄호 안에 명명된 형식 정의가 있습니다.  
  
 지정된 기호가 괄호 식 안에서 구조체, 공용 구조체 또는 열거 형식을 정의하는 데 사용되었습니다. 예상치 못한 정의의 범위가 발생할 수 있습니다.  
  
 C 함수 호출에서는 정의가 전역 범위입니다. C++ 호출에서는 정의의 범위가 호출되는 함수의 범위와 동일합니다.  
  
 이 경고는 괄호 식이 아닌 괄호 안의 선언자(예: 프로토타입)로 인해 발생할 수도 있습니다.  
  
 이는 ANSI 호환성(/Za)에서 컴파일된 C 프로그램 및 C++ 프로그램에서 수준 1 경고입니다. 그렇지 않으면 수준 3입니다.