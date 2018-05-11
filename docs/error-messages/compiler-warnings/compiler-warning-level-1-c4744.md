---
title: 컴파일러 경고 (수준 1) C4744 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4744
dev_langs:
- C++
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a45207f85575c8047f673b415ce802dbac24318
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4744"></a>컴파일러 경고(수준 1) C4744
'var'의 'file1' 및 'file2'에서 형식이 다릅니다.: 'type1' 및 'type2'  
  
 외부 변수가 두 파일에 정의 된 또는 참조에 해당 파일에 서로 다른 형식이 있습니다.  를 해결 하려면 형식 정의 동일 하 게 하거나 파일 중 하나에 변수 이름을 변경 합니다.  
  
 /Gl 파일 컴파일되는 경우에 C4744 내보내집니다.  자세한 내용은 [/GL(전체 프로그램 최적화)](../../build/reference/gl-whole-program-optimization.md)을 참조하세요.  
  
> [!NOTE]
>  C + +에서 변수 이름을 형식 정보로 데코 레이트 된 때문에 일반적으로 C4744 C (하지 c + +) 파일에서 발생 합니다.  샘플 (아래) 이면 컴파일합니다도 c + + 링커 오류 LNK2019 얻게 됩니다.  
  
## <a name="example"></a>예제  
 이 샘플에는 첫 번째 정의 합니다.  
  
```  
// C4744.c  
// compile with: /c /GL  
int global;  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4744 오류가 발생 합니다.  
  
```  
// C4744b.c  
// compile with: C4744.c /GL /W1  
// C4744 expected  
#include <stdio.h>  
  
extern unsigned global;  
  
main()   
{  
    printf_s("%d\n", global);  
}  
```