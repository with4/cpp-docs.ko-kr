---
title: "컴파일러 경고 (수준 4) C4710 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4710
dev_langs:
- C++
helpviewer_keywords:
- C4710
ms.assetid: 76381ec7-3fc1-4bee-9a0a-c2c8307b92e2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e0464d924c21a029a97a8f03d30f88127f3aea6a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4710"></a>컴파일러 경고(수준 4) C4710
'function': 함수를 인라이닝 하지 못했습니다.  
  
 인라인 확장에 대 한 지정된 된 함수를 선택 했지만 컴파일러 수행 하지 않은 인라인 처리 합니다.  
  
 인라이닝은 컴파일러의 판단에 따라 수행 됩니다. **인라인** 키워드 처럼는 **등록** 키워드, 컴파일러에 대 한 힌트로 사용 됩니다. 컴파일러는 휴리스틱을 사용 하 여 속도 컴파일할 경우에 코드 속도 향상을 위한 특정 함수를 인라인 할 또는 하는 코드를 더 작은 공간에 대해 컴파일할 때 특정 함수를 인라인 할 경우를 결정 합니다. 컴파일러에서는 인라인 매우 작은 기능 공간에 대해 컴파일할 때.  
  
 경우에 따라 컴파일러 인라인 처리 하지 않습니다는 특정 기능 기계적 이유로 합니다. 참조 [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) 컴파일러는 함수를 인라인 하지 않는 이유에 목록은 합니다.  
  
 기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.