---
title: 컴파일러 경고 (수준 4) C4092 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4092
dev_langs:
- C++
helpviewer_keywords:
- C4092
ms.assetid: 396ae826-a892-4327-bd66-f4762376d72b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ca145addc16306d613817643e363ecd9c95069a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4092"></a>컴파일러 경고 (수준 4) C4092
sizeof '부호 없는 long' 반환  
  
 피연산자는 `sizeof` 연산자가 매우 큰 하므로 `sizeof` 서명 되지 않은 반환 **긴**합니다. 이 경고는 Microsoft 확장 발생 ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)). ANSI 호환성 (/Za)에서 결과 대신 잘립니다.