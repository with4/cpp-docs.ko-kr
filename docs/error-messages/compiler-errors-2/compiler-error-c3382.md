---
title: 컴파일러 오류 C3382 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3382
dev_langs:
- C++
helpviewer_keywords:
- C3382
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f8bcca58aecc3d5a5e7b621f45e102690c9f138c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3382"></a>컴파일러 오류 C3382
/clr:safe를 지정하면 'sizeof'를 사용할 수 없습니다.  
  
 **/clr:safe** 컴파일의 출력 파일은 형식 안전 파일이며 sizeof는 지원되지 않습니다. sizeof 연산자의 반환 값은 size_t이며 운영 체제에 따라 크기가 달라지기 때문입니다.  
  
 자세한 내용은 다음 항목을 참조하세요.  
  
-   [sizeof 연산자](../../cpp/sizeof-operator.md)  
  
-   [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [일반적인 Visual C++ 64비트 마이그레이션 문제](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3382를 생성합니다.  
  
```  
// C3382.cpp  
// compile with: /clr:safe  
int main() {  
   sizeof( char );   // C3382  
}  
```