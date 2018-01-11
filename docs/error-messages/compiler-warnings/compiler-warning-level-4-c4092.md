---
title: "컴파일러 경고 (수준 4) C4092 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4092
dev_langs: C++
helpviewer_keywords: C4092
ms.assetid: 396ae826-a892-4327-bd66-f4762376d72b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6eec21584ec56567b818f23e7dfcf5fb708369ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4092"></a>컴파일러 경고 (수준 4) C4092
sizeof '부호 없는 long' 반환  
  
 피연산자는 `sizeof` 연산자가 매우 큰 하므로 `sizeof` 서명 되지 않은 반환 **긴**합니다. 이 경고는 Microsoft 확장 발생 ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)). ANSI 호환성 (/Za)에서 결과 대신 잘립니다.