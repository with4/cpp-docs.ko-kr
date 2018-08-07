---
title: 컴파일러 경고 (수준 4) C4820 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4820
dev_langs:
- C++
helpviewer_keywords:
- C4820
ms.assetid: 17aa29f4-c287-49b8-bc43-8ed82ffed5ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea99ca177a90281ca02e44265f603045b72845f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33294221"
---
# <a name="compiler-warning-level-4-c4820"></a>컴파일러 경고(수준 4) C4820
'bytes'바이트 채움 문자가 construct 'member_name' 뒤에 추가되었습니다.  
  
 형식과 요소의 순서는 컴파일러에서 구조체의 끝에 안쪽 여백을 추가에 발생 합니다. 참조 [맞춤](../../cpp/align-cpp.md) 패딩 구조체에 대 한 자세한 내용은 합니다.  
  
 기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.  
  
 다음 샘플에서는 C4820 오류가 생성 됩니다.  
  
```  
// C4820.cpp  
// compile with: /W4 /c  
#pragma warning(default : 4820)   
  
// Delete the following 4 lines to resolve.  
__declspec(align(2)) struct MyStruct {  
   char a;  
   int i;   // C4820  
};  
  
// OK  
#pragma pack(1)  
__declspec(align(1)) struct MyStruct2 {  
   char a;  
   int i;  
};  
```