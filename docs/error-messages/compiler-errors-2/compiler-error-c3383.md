---
title: 컴파일러 오류 C3383 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3383
dev_langs:
- C++
helpviewer_keywords:
- C3383
ms.assetid: ceb7f725-f417-4dc3-8496-0f413bb76687
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b54eda0e29a9876da83b9e3da384a39b9345d5d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33251162"
---
# <a name="compiler-error-c3383"></a>컴파일러 오류 C3383
/clr:safe를 지정하면 'operator new'를 사용할 수 없습니다.  
  
 **/clr:safe** 컴파일의 출력 파일은 형식이 안전한 파일이며 포인터가 지원되지 않습니다.  
  
 자세한 내용은 다음 항목을 참조하세요.  
  
-   [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
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