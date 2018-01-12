---
title: "컴파일러 오류 C3461 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3461
dev_langs: C++
helpviewer_keywords: C3461
ms.assetid: bd66833a-545d-445a-bdfe-dee771a450a4
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3a06d10bc8a66f1506458a5d095585826c0a6b03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3461"></a>컴파일러 오류 C3461
'type': 관리되는 형식만 전달할 수 있습니다.  
  
 형식 전달은 CLR 형식에서만 발생할 수 있습니다.  참조 [클래스 및 구조체](../../windows/classes-and-structs-cpp-component-extensions.md) 자세한 정보에 대 한 합니다.  
  
 자세한 내용은 참조 [형식 전달 (C + + /cli CLI)](../../windows/type-forwarding-cpp-cli.md)합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 구성 요소를 만듭니다.  
  
```  
// C3461.cpp  
// compile with: /clr /LD  
public ref class R {};  
```  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3461을 생성합니다.  
  
```  
// C3461b.cpp  
// compile with: /clr /c  
#using "C3461.dll"  
class N {};  
[assembly:TypeForwardedTo(N::typeid)];   // C3461  
[assembly:TypeForwardedTo(R::typeid)];   // OK  
```