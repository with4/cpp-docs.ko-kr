---
title: 컴파일러 오류 C2834 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2834
dev_langs:
- C++
helpviewer_keywords:
- C2834
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4eb4fb992f9213c4a4b456f786fd8f81308cec12
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33244786"
---
# <a name="compiler-error-c2834"></a>컴파일러 오류 C2834
'operator 연산자' 전역으로 한정 되어야 합니다.  
  
 `new` 및 `delete` 연산자는 클래스에 연결 된 위치입니다. 범위 결정의 버전을 선택 하는 데 사용할 수 없습니다 `new` 또는 `delete` 다른 클래스에서 합니다. 여러 형식의 구현 하는 `new` 또는 `delete` 연산자를 추가 형식 매개 변수가 있는 연산자의 버전을 만듭니다.