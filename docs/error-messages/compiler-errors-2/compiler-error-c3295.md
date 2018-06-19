---
title: 컴파일러 오류 C3295 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3295
dev_langs:
- C++
helpviewer_keywords:
- C3295
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25fd1a04e0be46943b4fd183b470b369f810a0d1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33253959"
---
# <a name="compiler-error-c3295"></a>컴파일러 오류 C3295
'#pragma pragma'는 전역 또는 네임스페이스 범위에서만 사용할 수 있습니다.  
  
 일부 pragma는 함수에 사용할 수 없습니다.  참조 [Pragma 지시문 및 __Pragma 키워드](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) 자세한 정보에 대 한 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3295를 생성합니다.  
  
```  
// C3295.cpp  
int main() {  
   #pragma managed   // C3295  
}  
```