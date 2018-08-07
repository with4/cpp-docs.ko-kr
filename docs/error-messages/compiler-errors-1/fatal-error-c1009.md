---
title: 심각한 오류 C1009 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1009
dev_langs:
- C++
helpviewer_keywords:
- C1009
ms.assetid: dcc8383c-3362-4c47-9c26-25d2451ebd53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 665d868aeacbaf5c62bf59a4400baa2b31569972
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198731"
---
# <a name="fatal-error-c1009"></a>심각한 오류 C1009
컴파일러 한계: 매크로가 너무 많이 중첩  
  
 컴파일러는 동시에 너무 많은 매크로 확장 하 려 했습니다. 컴파일러의 한 제한은 256 수준의 중첩된 매크로입니다. 중첩 된 매크로 보다 간단한 매크로로 분할 합니다.