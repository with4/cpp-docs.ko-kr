---
title: "링커 도구 경고 LNK4224 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4224
dev_langs:
- C++
helpviewer_keywords:
- LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 96399e0c66eb3cb719073b2318513cd680723d97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4224"></a>링커 도구 경고 LNK4224
옵션은 더 이상 지원 됩니다. 무시  
  
 잘못 됨, 사용 되지 않는 링커 옵션 지정과 무시.  
  
 예, LNK4224 /comment 지시문에 표시 되 면 발생할 수 있습니다. obj. /Comment 지시문을 통해 추가 된는 [주석 (C/c + +)](../../preprocessor/comment-c-cpp.md) pragma를 사용 되지 않는 exestr 옵션을 사용 합니다. Dumpbin을 사용 하 여 [/모든](../../build/reference/all.md) 링커 지시문.obj 파일에서 볼 수 있습니다.  
  
 가능 하면.obj에 대 한 소스를 수정 하 고 pragma를 제거 합니다. 이 경고를 무시 하면 있기.executable 컴파일하면 **/clr: pure** 예상 대로 실행 되지 것입니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 LNK4224가 발생 합니다.  
  
```  
// LNK4224.cpp  
// compile with: /c /Zi  
// post-build command: link LNK4224.obj /debug /debugtype:map  
int main () {  
   return 0;  
}  
```