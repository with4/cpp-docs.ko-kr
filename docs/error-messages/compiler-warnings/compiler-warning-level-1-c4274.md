---
title: "컴파일러 경고 (수준 1) C4274 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4274
dev_langs: C++
helpviewer_keywords: C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4519258a10937ad96528f34484a44d398a0cd0ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4274"></a>컴파일러 경고 (수준 1) C4274
\#ident 무시 됩니다. #pragma 주석 (exestr, 'string')에 대 한 설명서를 참조 하십시오.  
  
 `#ident` 개체 또는 실행 파일에서 사용자가 지정한 문자열을 삽입 하는 지시문은 사용 되지 않습니다. 따라서 컴파일러 지시문을 무시합니다.  
  
> [!CAUTION]
>  사용 하 라는 경고 C4274는 [#pragma 주석 (exestr, 'string')](../../preprocessor/comment-c-cpp.md) 지시문입니다. 그러나이 충고가 더 이상 컴파일러의 이후 릴리스에서 수정 될 예정입니다. 사용 하는 경우는 `#pragma` 지시문 링커 도구 (LINK.exe) 무시 주석 기록은 지시문에 의해 발생 하 고 경고 [LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)합니다. 대신는 `#ident` 파일 버전 리소스 문자열을 사용 하 여 응용 프로그램에서 지시문을 권장 합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   제거는 `#ident "` *문자열* `"` 지시문입니다.  
  
## <a name="see-also"></a>참고 항목  
 [주석 (C/c + +)](../../preprocessor/comment-c-cpp.md)   
 [링커 도구 경고 LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)   
 [리소스 파일 작업](../../windows/working-with-resource-files.md)