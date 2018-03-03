---
title: "컴파일러 경고 (수준 1) C4005 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4005
dev_langs:
- C++
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf0c5777cecf89bb0723b30c87dc4c856de0a016
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4005"></a>컴파일러 경고 (수준 1) C4005
'identifier': 매크로 재정의  
  
 매크로 식별자가 두 번 정의 되었습니다. 컴파일러는 두 번째 매크로 정의 사용 합니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  명령줄에 사용 하 여 코드에서 매크로 정의 `#define` 지시문입니다.  
  
2.  포함 파일에서 가져온 매크로입니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.  
  
1.  정의 중 하나를 제거 합니다.  
  
2.  사용 하 여 프로그램 [#undef](../../preprocessor/hash-undef-directive-c-cpp.md) 두 번째 정의 하기 전에 지시문입니다.  
  
 다음 샘플에서는 C4005 오류가 생성 됩니다.  
  
```  
// C4005.cpp  
// compile with: /W1 /EHsc  
#include <iostream>  
using namespace std;  
  
#define TEST "test1"  
#define TEST "test2"   // C4005 delete or rename to resolve the warning  
  
int main() {  
   cout << TEST << endl;  
}  
```