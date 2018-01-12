---
title: "컴파일러 경고 (수준 4) C4611 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4611
dev_langs: C++
helpviewer_keywords: C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3020cf7d115b735141b81e9007ac7fd027ed8674
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4611"></a>컴파일러 경고(수준 4) C4611
'function' 및 c + + 개체 소멸 사이의 상호 작용이 이식 가능 하지 않습니다.  
  
 일부 플랫폼에서는 포함 하는 함수 **catch** 범위를 벗어날 때 소멸 c + + 개체 의미 체계를 지원 하지 않을 수 있습니다.  
  
 예기치 않은 동작을 방지 하려면 사용 하지 않도록 **catch** 생성자와 소멸자가 있는 함수에 있습니다.  
  
 이 경고는 한 번만 발생 참조 [pragma 경고](../../preprocessor/warning.md)합니다.