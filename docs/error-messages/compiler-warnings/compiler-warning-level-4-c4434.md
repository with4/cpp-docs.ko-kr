---
title: "컴파일러 경고 (수준 4) C4434 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4434
dev_langs: C++
helpviewer_keywords: C4434
ms.assetid: 24b8785e-353a-4c37-8bed-ed61001a871d
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a9499d145263c3bbb1bd5aac948c6be9e4db48d2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4434"></a>컴파일러 경고(수준 4) C4434
클래스 생성자를 private 액세스 가능성이; 있어야 합니다. private 액세스로 변경  
  
 C4434는 컴파일러는 정적 생성자의 액세스 가능성 변경 되었음을 나타냅니다. 정적 생성자는 공용 언어 런타임에 의해 호출 될 기능만 같이 private 액세스 가능성이 있어야 합니다. 자세한 내용은 참조 [정적 생성자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Static_constructors)합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 c4434 오류가 발생 합니다.  
  
```  
// C4434.cpp  
// compile with: /W4 /c /clr  
public ref struct R {  
   static R(){}   // C4434  
};  
```