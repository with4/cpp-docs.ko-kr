---
title: "컴파일러 경고 (수준 1) C4103 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4103
dev_langs:
- C++
helpviewer_keywords:
- C4103
ms.assetid: 9021b514-375e-4d62-b261-ccb06f299e8e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 115c88a43f38065541fe925b023d61679c06be53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4103"></a>컴파일러 경고 (수준 1) C4103
'filename': 맞춤 헤더를 포함 한 후에 변경할 수 없는 경우 발생할 수 #pragma pack(pop)  
  
 압축 클래스의 레이아웃에 영향을 줍니다 및 일반적으로 헤더 파일에서 변경 내용을 압축을 하는 경우 문제가 있을 수 있습니다.  
  
 #Pragma를 사용 하 여 [팩](../../preprocessor/pack.md)(pop)이이 경고를 해결 하려면 헤더 파일을 종료 하기 전에.  
  
 다음 샘플에서는 C4103 오류가 생성 됩니다.  
  
```  
// C4103.h  
#pragma pack(push, 4)  
  
// defintions and declarations  
  
// uncomment the following line to resolve  
// #pragma pack(pop)  
```  
  
 그리고  
  
```  
// C4103.cpp  
// compile with: /LD /W1  
#include "c4103.h"   // C4103  
```