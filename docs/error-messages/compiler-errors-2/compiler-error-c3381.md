---
title: "컴파일러 오류 C3381 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3381
dev_langs:
- C++
helpviewer_keywords:
- C3381
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af632ae602cacb5204f1fac1088bef8a6cd20168
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3381"></a>컴파일러 오류 C3381
'assembly': 어셈블리 액세스 지정자는 /clr 옵션으로 컴파일된 코드에서 사용할 수만  
  
 네이티브 형식을 어셈블리 외부에서 볼 수 있지만 네이티브 형식에 대 한 어셈블리 액세스를 지정할 수 있습니다는 **/clr** 컴파일입니다.  
  
 자세한 내용은 참조 [표시 유형 입력](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) 및 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3381 오류가 발생 합니다.  
  
```  
// C3381.cpp  
// compile with: /c  
public class A {};   // C3381  
```