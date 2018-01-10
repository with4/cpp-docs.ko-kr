---
title: "컴파일러 경고 (수준 4) C4718 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4718
dev_langs: C++
helpviewer_keywords: C4718
ms.assetid: 29507f8a-b024-42c1-a3b8-f35d1f2641f3
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 214c481f4ad77a7a67190cd7427e0cd5775ccc8c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4718"></a>컴파일러 경고(수준 4) C4718
'function call': 재귀 호출에 파생 작업이 없습니다. 삭제하고 있습니다.  
  
 함수가 재귀 호출을 포함하지만 그렇지 않은 경우 부수적인 효과가 없습니다. 이 함수에 대한 호출을 삭제하는 중입니다. 프로그램의 정확성에는 영향을 주지 않지만 동작에는 영향을 줍니다. 호출을 그대로 유지하면 런타임 스택 오버플로 예외가 발생할 수 있지만 호출을 삭제하면 이 가능성을 제거합니다.