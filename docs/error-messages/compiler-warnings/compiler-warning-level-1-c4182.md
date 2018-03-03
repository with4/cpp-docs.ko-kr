---
title: "컴파일러 경고 (수준 1) C4182 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4182
dev_langs:
- C++
helpviewer_keywords:
- C4182
ms.assetid: 8970f3c6-e2dd-407e-b2ec-964360eb8b43
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3ef78cebafcb07977611f92ad9f49a3d5b2c3dde
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4182"></a>컴파일러 경고(수준 1) C4182
\#포함 심층; 'number'은 중첩 수준 무한 재귀가 발생할 수 있습니다  
  
 중첩된 포함 파일의 수로 인해 힙의 공간이 부족합니다. 다른 포함 파일에 포함된 포함 파일이 중첩됩니다.  
  
 이 메시지는 정보 제공을 위해 제공되며 [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md)오류를 생성합니다.