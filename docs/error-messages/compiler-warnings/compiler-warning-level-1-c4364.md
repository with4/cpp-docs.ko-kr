---
title: "컴파일러 경고 (수준 1) C4364 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4364
dev_langs: C++
helpviewer_keywords: C4364
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9d532ff9cc030c92543bec898f34daf3559531f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4364"></a>컴파일러 경고(수준 1) C4364
\#as_friend 특성 없이 location(line_number)에서 이전에 표시 하는 ' file' 어셈블리에 대 한 사용 하 여 as_friend 적용 되지 않습니다  
  
 A `#using` 지시문을 지정 된 메타 데이터 파일에 대해 반복 되지만 `as_friend` 한정자 첫 번째 일치 항목에서 사용 되지 않으면 컴파일러에서 두 번째 무시 `as_friend`합니다.  
  
 자세한 내용은 참조 [Friend 어셈블리 (c + +)](../../dotnet/friend-assemblies-cpp.md)합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 구성 요소를 만듭니다.  
  
```  
// C4364.cpp  
// compile with: /clr /LD  
ref class A {};  
```  
  
## <a name="example"></a>예  
 다음 샘플에서는 C4364 오류가 발생 합니다.  
  
```  
// C4364_b.cpp  
// compile with: /clr /W1 /c  
#using " C4364.dll"  
#using " C4364.dll" as_friend   // C4364  
```