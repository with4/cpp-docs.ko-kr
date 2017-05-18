---
title: "컴파일러 오류 C3862 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3862
dev_langs:
- C++
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 48dbae62c367616a437db0607d84fa89e8006021
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3862"></a>컴파일러 오류 C3862
'function': /clr을 사용한 관리 되는 함수를 컴파일할 수 없습니다: pure 또는 /clr: safe  
  
 **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않습니다.  
  
 로 컴파일 **/clr: pure** 또는 **/clr: safe** 는 유일한 이미지 MSIL을 네이티브 (비관리) 코드 없이 이미지를 생성 합니다.  따라서 사용할 수 없습니다는 `unmanaged` pragma에는 **/clr: pure** 또는 **/clr: safe** 컴파일.  
  
 자세한 내용은 참조 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 및 [관리 되는, 관리 되지 않는](../../preprocessor/managed-unmanaged.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3862 오류가 생성 됩니다.  
  
```  
// C3862.cpp  
// compile with: /clr:pure /c  
#pragma unmanaged  
void f() {}   // C3862  
```
