---
title: "컴파일러 경고 C4394 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4394
dev_langs: C++
helpviewer_keywords: C4394
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6ab51a4f818e8eb8a94150424124a5c96ebaf241
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4394"></a>컴파일러 경고 C4394
'function': appdomain 별 기호는 __declspec (dllexport)로 표시할 수 없습니다  
  
 로 표시 한 함수는 [appdomain](../../cpp/appdomain.md) `__declspec` 한정자에 대 한 MSIL (하지 네이티브), 및 내보내기 테이블에 컴파일됩니다 ([내보내기](../../windows/export.md) `__declspec` 한정자) 관리 되는 함수에 대 한 지원 되지 않습니다.  
  
 공용 액세스 가능성을 갖도록 관리되는 함수를 선언할 수 있습니다. 자세한 내용은 참조 [표시 유형 입력](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) 및 [멤버 표시 유형](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility)합니다.  
  
 C4394은 항상 오류로 실행 됩니다.  와 함께이 경고를 해제할 수 있습니다는 `#pragma warning` 또는 **/wd**; 참조 [경고](../../preprocessor/warning.md) 또는 [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, / we, /wo /Wv, /WX (경고 수준)](../../build/reference/compiler-option-warning-level.md)자세한 정보에 대 한 합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C4394 합니다.  
  
```  
// C4394.cpp  
// compile with: /clr /c  
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394  
__declspec(dllexport) int g2 = 0;   // OK  
```