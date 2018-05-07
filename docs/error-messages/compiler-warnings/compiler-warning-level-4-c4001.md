---
title: 컴파일러 경고 (수준 4) C4001 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4001
dev_langs:
- C++
helpviewer_keywords:
- C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc728fa5c66fb4b42c8fe4a785f36048ffbaed4e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4001"></a>컴파일러 경고 (수준 4) C4001
비표준 확장인 '한 줄으로 된 주석' 사용 했습니다.  

> [!NOTE] 
> 이 경고 한 줄 주석을 C99에서 표준 Visual Studio 2017 15.5 버전에서에서 제거 됩니다.
  
 한 줄 주석을 표준 c + +에서 및 C C99 부터는에서 표준입니다. 엄격한 ANSI 호환성 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), 한 줄으로 된 주석을 포함 하는 C 파일 비표준 확장이 사용으로 인해 4001 합니다. 한 줄 주석을 c + +에서 표준 되므로 Microsoft 확장명 (/Ze)를 사용 하 여 컴파일하면 C 파일을 한 줄 주석이 포함 된 C4001을 생성 하지 않습니다.  
  
## <a name="example"></a>예제  
 경고를 해제 하려면 주석 [#pragma warning(disable:4001)](../../preprocessor/warning.md)합니다.  
  
```  
// C4001.cpp  
// compile with: /W4 /Za /TC  
// #pragma warning(disable:4001)  
int main()  
{  
   // single-line comment in main  
   // C4001  
}  
```