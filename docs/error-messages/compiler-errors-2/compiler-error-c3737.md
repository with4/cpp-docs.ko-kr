---
title: "컴파일러 오류 C3737 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3737
dev_langs: C++
helpviewer_keywords: C3737
ms.assetid: ca2aeb23-2491-4ccb-8838-884abf7065c8
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0fc7a1314462c7a62bdece0b20c959e34ad39fb1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3737"></a>컴파일러 오류 C3737
'delegate': 대리자에서 명시적 호출 규칙을 사용할 수 없습니다  
  
 지정할 수 없습니다는 [호출 규칙](../../cpp/calling-conventions.md) 에 대 한는 `delegate`합니다.  
  
## <a name="example"></a>예  
다음 샘플에서는 C3737 오류가 생성 됩니다.  
  
```  
// C3737a.cpp  
// compile with: /clr  
delegate void __stdcall MyFunc();   // C3737  
// Try the following line instead.  
// delegate void MyFunc();  
  
int main() {  
}  
```  
