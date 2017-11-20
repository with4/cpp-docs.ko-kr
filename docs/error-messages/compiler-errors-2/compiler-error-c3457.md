---
title: "컴파일러 오류 C3457 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3457
dev_langs: C++
helpviewer_keywords: C3457
ms.assetid: 5c1e366a-fa75-4cca-b9a3-86d4ebe4090e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d2550bdaa8d070b046ab9dbab6b21b691eed6f49
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3457"></a>컴파일러 오류 C3457
'attribute': 특성은 명명되지 않은 인수를 지원하지 않습니다.  
  
 CLR 사용자 지정 특성 또는 컴파일러 특성과 달리 소스 주석 특성은 명명된 인수만 지원합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3457을 생성합니다.  
  
```  
#include "SourceAnnotations.h"  
[vc_attributes::Post( 1 )] int f();   // C3457  
[vc_attributes::Post( Valid=vc_attributes::Yes )] int f2();   // OK  
```