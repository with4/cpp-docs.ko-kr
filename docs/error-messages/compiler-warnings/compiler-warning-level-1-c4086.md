---
title: "컴파일러 경고 (수준 1) C4086 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4086
dev_langs: C++
helpviewer_keywords: C4086
ms.assetid: 9248831b-22bf-47af-8684-bfadb17e94fc
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 120c8cf15cc4d4c320c422feffed908276c52d3d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4086"></a>컴파일러 경고(수준 1) C4086
pragma 매개 변수는 '1', '2', '4', '8' 또는 '16'이어야 합니다.  
  
 pragma 매개 변수에 필수 값(1, 2, 4, 8 또는 16)이 없습니다.  
  
## <a name="example"></a>예  
  
```  
// C4086.cpp  
// compile with: /W1 /LD  
#pragma pack( 3 ) // C4086  
```