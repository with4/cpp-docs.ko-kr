---
title: "컴파일러 경고 (수준 1) C4399 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4399
dev_langs: C++
helpviewer_keywords: C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eff01c29d423b0823b41bf63702cf42ee839a523
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4399"></a>컴파일러 경고(수준 1) C4399
'symbol': /clr으로 컴파일할 때 __declspec (dllimport)로 프로세스별 기호를 표시 하지 말아야: 순수  
  
 **/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않습니다.  
  
 순수 이미지에 네이티브 이미지 또는 기본 모드와 CLR 구문을 사용 하 여 이미지 데이터를 가져올 수 없습니다. 이 경고를 해결 하려면 사용 하 여 컴파일합니다. **/clr** (하지 **/clr: pure**) 또는 삭제 `__declspec(dllimport)`합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C4399 오류가 발생 합니다.  
  
```  
// C4399.cpp  
// compile with: /clr:pure /doc /W1 /c  
__declspec(dllimport) __declspec(process) extern const int i;   // C4399  
```