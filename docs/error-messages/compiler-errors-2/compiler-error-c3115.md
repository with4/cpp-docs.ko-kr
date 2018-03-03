---
title: "컴파일러 오류 C3115 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3115
dev_langs:
- C++
helpviewer_keywords:
- C3115
ms.assetid: 51726145-9782-4ec9-84b9-286f366d9cbd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf60a87b73c497fd69998950519bf7479332e51b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3115"></a>컴파일러 오류 C3115
'attribute': 'c'이 특성은 사용할 수 없습니다  
  
 특성은 의도 하지 않은 구문에 적용 되었습니다.  참조 [용도별 특성](../../windows/attributes-by-usage.md) 자세한 정보에 대 한 합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3115 오류가 발생 합니다.  
  
```  
// C3115.cpp  
// compile with: /c  
#include <unknwn.h>  
[module(name="xx")];  
  
[object, helpstringdll(xx.dll), uuid("00000000-0000-0000-0000-000000000001")]   // C3115  
// try the following line instead  
// [object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI {  
   HRESULT xx();  
};  
```