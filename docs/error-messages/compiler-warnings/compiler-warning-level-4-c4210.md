---
title: 컴파일러 경고 (수준 4) C4210 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4210
dev_langs:
- C++
helpviewer_keywords:
- C4210
ms.assetid: f8600adf-dfe2-4022-a37a-3d4997641dfd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1a376eb8bb9c5dffe5cfd4bc34c720c7e0acf41
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292489"
---
# <a name="compiler-warning-level-4-c4210"></a>컴파일러 경고(수준 4) C4210
비표준 확장이 사용 됨: 함수에서 파일 범위를 제공 합니다.  
  
 기본 Microsoft 확장 ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)), 함수 선언에는 파일 범위가 있습니다.  
  
```  
// C4210.c  
// compile with: /W4 /c  
void func1()  
{  
   extern int func2( double );   // C4210 expected  
}  
  
int main()  
{  
   func2( 4 );   //  /Ze passes 4 as type double  
}                //  /Za passes 4 as type int  
```  
  
 이 확장은 다른 컴파일러로 이식 되 코드를 방지할 수 있습니다.