---
title: "컴파일러 경고 (수준 1) C4810 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4810
dev_langs: C++
helpviewer_keywords: C4810
ms.assetid: 39e2cae0-9c1c-4ac1-aaa0-5f661d06085b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 65c9c51a7672bea5d6aec81d8b1ee2363519e488
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4810"></a>컴파일러 경고(수준 1) C4810
pragma pack(show)의 값 == n  
  
 이 경고는 **pack** pragma의 [표시](../../preprocessor/pack.md) 옵션을 사용할 때 발생합니다. *n* 은 현재 팩 값입니다.  
  
 예를 들어 다음 코드는 C4810 경고가 pack pragma에서 작동하는 방식을 보여 줍니다.  
  
```  
// C4810.cpp  
// compile with: /W1 /LD  
// C4810 expected  
#pragma pack(show)  
#pragma pack(4)  
#pragma pack(show)  
```