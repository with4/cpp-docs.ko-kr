---
title: "유추 된 종속 파일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 410e52dd9ee9605f6e29b81491bda0f4883e1cf9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="inferred-dependents"></a>유추된 종속 파일
유추 된 종속 유추 규칙에서 파생 되 고 명시적 종속 파일 보다 먼저 계산 됩니다. 유추 된 종속 대상에 대하여 오래 이면 NMAKE 종속성에 대 한 명령 블록을 호출 합니다. 유추 된 종속 파일이 존재 하지 않거나 자체 종속 항목에 대하여 오래 된, 경우 NMAKE는 먼저 유추 된 종속 파일을 업데이트 합니다. 유추 된 종속 파일에 대 한 자세한 내용은 참조 [유추 규칙](../build/inference-rules.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [종속 파일](../build/dependents.md)