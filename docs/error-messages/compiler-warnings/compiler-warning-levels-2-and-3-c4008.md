---
title: 컴파일러 경고 (수준 2 및 3) C4008 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4008
dev_langs:
- C++
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4cdc88f222f9e5ce3829a63c131c955ce2abdd7d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33294260"
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>컴파일러 경고(수준 2 및 3) C4008
'identifier': 'attribute' 특성이 무시됩니다.  
  
 컴파일러가 함수(수준 3 경고) 또는 데이터(수준 2 경고)에 대한 `__fastcall`, **static**또는 **inline** 특성을 무시했습니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  데이터가 있는`__fastcall` 특성  
  
2.  **main** 함수가 있는 **static** 또는 **inline** 특성