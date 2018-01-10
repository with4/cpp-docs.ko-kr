---
title: "컴파일러 경고 (수준 1) C4276 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4276
dev_langs: C++
helpviewer_keywords: C4276
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: af9a32da86a0ea9e530af03a2175976d4cd9f091
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4276"></a>컴파일러 경고(수준 1) C4276
'function': 제공 된; 프로토타입이 없는 매개 변수를 가정합니다.  
  
 갖는 함수 주소를 가져올 때는 [__stdcall](../../cpp/stdcall.md) 호출 규칙을 부여 해야 프로토타입을 컴파일러는 함수의 데코 레이트 된 이름을 만들 수 있도록 합니다. 이후 *함수* 데코레이팅된 이름을 만들 때에 컴파일러에 프로토타입이 없으므로, 함수에 매개 변수가 없는 것으로 가정 합니다.