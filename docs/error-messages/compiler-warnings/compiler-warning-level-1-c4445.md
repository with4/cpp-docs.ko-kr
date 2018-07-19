---
title: 컴파일러 경고 (수준 1) C4445 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4445
dev_langs:
- C++
helpviewer_keywords:
- C4445
ms.assetid: 535e92a0-ba08-4dfc-89b2-af2dcdd7caeb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: abd0d15113373f752bb861d73e48091687b2f0d2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274591"
---
# <a name="compiler-warning-level-1-c4445"></a>컴파일러 경고(수준 1) C4445
'function': WinRT 또는 관리되는 형식에서 가상 메서드는 private일 수 없습니다.  
  
 가상 함수가 private인 경우 파생된 형식에서 액세스할 수 없습니다. 이 오류를 해결하려면 가상 멤버 함수의 접근성을 보호됨이나 공용으로 변경합니다.