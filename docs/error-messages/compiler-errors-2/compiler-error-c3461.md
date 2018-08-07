---
title: 컴파일러 오류 C3461 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3461
dev_langs:
- C++
helpviewer_keywords:
- C3461
ms.assetid: bd66833a-545d-445a-bdfe-dee771a450a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a0b9349ed9450c6d74a9311d5b9265f57cc37b81
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33255983"
---
# <a name="compiler-error-c3461"></a>컴파일러 오류 C3461
'type': 관리되는 형식만 전달할 수 있습니다.  
  
 형식 전달은 CLR 형식에서만 발생할 수 있습니다.  참조 [클래스 및 구조체](../../windows/classes-and-structs-cpp-component-extensions.md) 자세한 정보에 대 한 합니다.  
  
 자세한 내용은 참조 [형식 전달 (C + + /cli CLI)](../../windows/type-forwarding-cpp-cli.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 구성 요소를 만듭니다.  
  
```  
// C3461.cpp  
// compile with: /clr /LD  
public ref class R {};  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3461을 생성합니다.  
  
```  
// C3461b.cpp  
// compile with: /clr /c  
#using "C3461.dll"  
class N {};  
[assembly:TypeForwardedTo(N::typeid)];   // C3461  
[assembly:TypeForwardedTo(R::typeid)];   // OK  
```