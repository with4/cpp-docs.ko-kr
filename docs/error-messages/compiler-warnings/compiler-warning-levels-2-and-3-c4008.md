---
title: "컴파일러 경고 (수준 2 및 3) C4008 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4008
dev_langs:
- C++
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 0539a36dddf5bed1d7474f6456eb710bb0506ae4
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>컴파일러 경고(수준 2 및 3) C4008
'identifier': 'attribute' 특성이 무시됩니다.  
  
 컴파일러가 함수(수준 3 경고) 또는 데이터(수준 2 경고)에 대한 `__fastcall`, **static**또는 **inline** 특성을 무시했습니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  `__fastcall`데이터와 특성입니다.  
  
2.  **main** 함수가 있는 **static** 또는 **inline** 특성
