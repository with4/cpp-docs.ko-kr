---
title: "컴파일러 경고 (수준 1) C4274 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4274
dev_langs:
- C++
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: fbba1e6dde180e77afe7ed8960849ee8cc0fd108
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4274"></a>컴파일러 경고 (수준 1) C4274
\#ident 무시 됩니다. #pragma 주석 (exestr, 'string')에 대 한 설명서를 참조 하십시오.  
  
 `#ident` 개체 또는 실행 파일에 사용자 지정 문자열을 삽입는 지시문을 사용 하는 사용 되지 않습니다. 따라서 컴파일러 지시문을 무시합니다.  
  
> [!CAUTION]
>  경고 C4274를 사용 하 여 알려 고 [#pragma 주석 (exestr, 'string')](../../preprocessor/comment-c-cpp.md) 지시문입니다. 그러나이 사용 되지 않습니다 조언과 컴파일러의 이후 릴리스에서 수정 될 예정입니다. 사용 하는 경우는 `#pragma` 지시문 링커 도구 (LINK.exe)를 무시 주석 기록은 지시문에 의해 발생 하 고 경고 [LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)합니다. 대신는 `#ident` 파일 버전 리소스 문자열을 사용 하 여 응용 프로그램에서 지시문을 권장 합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   제거는 `#ident "` *문자열* `"` 지시문입니다.  
  
## <a name="see-also"></a>참고 항목  
 [주석 (C/c + +)](../../preprocessor/comment-c-cpp.md)   
 [링커 도구 경고 LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)   
 [리소스 파일 사용](../../windows/working-with-resource-files.md)
