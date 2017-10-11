---
title: "컴파일러 오류 C3383 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3383
dev_langs:
- C++
helpviewer_keywords:
- C3383
ms.assetid: ceb7f725-f417-4dc3-8496-0f413bb76687
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2a97cd1348bc927b633e683bed80a6b907f88a58
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3383"></a>컴파일러 오류 C3383
/clr:safe를 지정하면 'operator new'를 사용할 수 없습니다.  
  
 **/clr:safe** 컴파일의 출력 파일은 형식이 안전한 파일이며 포인터가 지원되지 않습니다.  
  
 자세한 내용은 다음 항목을 참조하세요.  
  
-   [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [일반적인 Visual C++ 64비트 마이그레이션 문제](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3383을 생성합니다.  
  
```  
// C3383.cpp  
// compile with: /clr:safe  
int main() {  
   char* pCharArray = new char[256];  // C3383  
}  
```
