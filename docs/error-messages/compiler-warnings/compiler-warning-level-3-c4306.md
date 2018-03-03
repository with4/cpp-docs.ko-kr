---
title: "컴파일러 경고 (수준 3) C4306 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4306
dev_langs:
- C++
helpviewer_keywords:
- C4306
ms.assetid: 5b2192d7-402d-4b6d-8619-08105e7dcac7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c341f968e8484228431c9ca870b7cdc5ae5bb6e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4306"></a>컴파일러 경고(수준 3) C4306
**'**   
 ***식별자* ': 변환할 '**   
 ***type1* 'to'**   
 ***유형 2* ' 더 큰**  
  
 식별자 형식이 큰 포인터로 캐스팅 합니다. 새로운 유형의 채워지지 않은 상위 비트가 0으로 채워진 됩니다.  
  
 이 경고는 의도 하지 않은 변환을 나타낼 수 있습니다. 결과 포인터는 유효 하지 않게 될 수 있습니다.