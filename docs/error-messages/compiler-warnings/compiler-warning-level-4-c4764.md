---
title: "컴파일러 경고 (수준 4) C4764 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4764
dev_langs: C++
helpviewer_keywords: C4764
ms.assetid: 7bd4296f-966b-484c-bf73-8dbc8e85b4a9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2d669fca9decf792501025b85d0ed15a8eec8e66
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4764"></a>컴파일러 경고(수준 4) C4764
16바이트를 초과하도록 catch 개체를 맞출 수 없습니다.  
  
 16보다 큰 맞춤을 지정했지만 일부 플랫폼에서는 함수에서 예외가 발생할 경우 스택이 16보다 크지 않은 맞춤을 강제로 적용합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C4764를 생성합니다.  
  
```  
// C4764.cpp  
// compile with: /W4 /EHsc  
// processor: x64 IPF  
#include <stdio.h>  
  
class A   
{  
public:  
    int x;  
};  
  
typedef __declspec(align(32)) A ALIGNEDA;  
  
int main()   
{  
    ALIGNEDA a;  
    try   
    {  
        a.x = 15;  
        throw a;  
    }  
    catch (ALIGNEDA b) // can’t align b to > 16 bytes  
    {  
        printf_s("%d\n", b.x);  
    }  
}   // C4764  
```