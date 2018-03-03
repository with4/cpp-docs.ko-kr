---
title: "컴파일러 오류 C3457 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3457
dev_langs:
- C++
helpviewer_keywords:
- C3457
ms.assetid: 5c1e366a-fa75-4cca-b9a3-86d4ebe4090e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a85e746667371a625d137b0c21faec2172c1a382
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3457"></a>컴파일러 오류 C3457
'attribute': 특성은 명명되지 않은 인수를 지원하지 않습니다.  
  
 CLR 사용자 지정 특성 또는 컴파일러 특성과 달리 소스 주석 특성은 명명된 인수만 지원합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3457을 생성합니다.  
  
```  
#include "SourceAnnotations.h"  
[vc_attributes::Post( 1 )] int f();   // C3457  
[vc_attributes::Post( Valid=vc_attributes::Yes )] int f2();   // OK  
```