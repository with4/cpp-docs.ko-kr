---
title: 컴파일러 오류 C3862 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3862
dev_langs:
- C++
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25b0a344eaafedc2f7c0eb60141e3a07fd86c6af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3862"></a>컴파일러 오류 C3862
'function': /clr으로 관리 되지 않은 함수를 컴파일할 수 없습니다: pure 또는 /clr: safe  
  
 **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다.  
  
 사용한 컴파일을 **/clr: pure** 또는 **/clr: safe** 는 유일한 이미지 MSIL을 네이티브 (비관리) 코드를 사용 하 여 이미지를 생성 합니다.  따라서 사용할 수 없습니다는 `unmanaged` 에 pragma는 **/clr: pure** 또는 **/clr: safe** 컴파일 합니다.  
  
 자세한 내용은 참조 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 및 [관리, 관리 되지 않는](../../preprocessor/managed-unmanaged.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3862 오류가 생성 됩니다.  
  
```  
// C3862.cpp  
// compile with: /clr:pure /c  
#pragma unmanaged  
void f() {}   // C3862  
```