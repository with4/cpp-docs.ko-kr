---
title: "컴파일러 경고 (수준 1) C4399 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4399
dev_langs:
- C++
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 7d7584e318a42530a2a91fee4b428c92bfaf120c
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4399"></a>컴파일러 경고(수준 1) C4399
'symbol': /clr으로 컴파일될 때 __declspec (dllimport)로 프로세스별 기호를 표시 되어야 합니다: 순수  
  
 **/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않습니다.  
  
 순수 이미지에는 네이티브 이미지 또는 네이티브 및 CLR 구문을 사용 하 여 이미지에서 데이터를 가져올 수 있습니다. 이 경고를 해결 하려면 사용 하 여 컴파일합니다 **/clr** (하지 **/clr: pure**) 또는 삭제 `__declspec(dllimport)`.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4399 오류가 발생 합니다.  
  
```  
// C4399.cpp  
// compile with: /clr:pure /doc /W1 /c  
__declspec(dllimport) __declspec(process) extern const int i;   // C4399  
```
