---
title: "컴파일러 오류 C3295 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3295
dev_langs:
- C++
helpviewer_keywords:
- C3295
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 401eafa2cd0129931ca98b0289a60325ec69643a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3295"></a>컴파일러 오류 C3295
'#pragma pragma'는 전역 또는 네임스페이스 범위에서만 사용할 수 있습니다.  
  
 일부 pragma는 함수에 사용할 수 없습니다.  참조 [Pragma 지시문 및 __Pragma 키워드](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) 자세한 정보에 대 한 합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3295를 생성합니다.  
  
```  
// C3295.cpp  
int main() {  
   #pragma managed   // C3295  
}  
```