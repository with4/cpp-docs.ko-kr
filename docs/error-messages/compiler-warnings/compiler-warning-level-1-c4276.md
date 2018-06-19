---
title: 컴파일러 경고 (수준 1) C4276 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4276
dev_langs:
- C++
helpviewer_keywords:
- C4276
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: afedab27c2fb93075aa33053c12ec6973824f144
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277308"
---
# <a name="compiler-warning-level-1-c4276"></a>컴파일러 경고(수준 1) C4276
'function': 제공 된; 프로토타입이 없는 매개 변수를 가정합니다.  
  
 갖는 함수 주소를 가져올 때는 [__stdcall](../../cpp/stdcall.md) 호출 규칙을 부여 해야 프로토타입을 컴파일러는 함수의 데코 레이트 된 이름을 만들 수 있도록 합니다. 이후 *함수* 데코레이팅된 이름을 만들 때에 컴파일러에 프로토타입이 없으므로, 함수에 매개 변수가 없는 것으로 가정 합니다.